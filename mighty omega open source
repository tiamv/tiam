--// m1kecorp© paid hub source
--\\ Enjoy!
game.Players.LocalPlayer.Idled:Connect(function()
    game:GetService("VirtualUser"):CaptureController()
    game:GetService("VirtualUser"):ClickButton2(Vector2.new(0,0))
end)

local Library = {}

function Library:Window(winName,mainColor,hideBind)
    winName = winName or "brought to you by m1kecorp"
    mainColor = mainColor or Color3.fromRGB(104, 186, 227)
    hideBind = hideBind or Enum.KeyCode.RightAlt

    if _G.Library ~= nil then _G.Library:Destroy() end
    
    _G.UISettings = {
        UIBind = hideBind,
        UIConfig = {},
        ElementCache = {},
    }

    local function Tween(which,gui,UDimStuff,time)
        task.spawn(function()
            pcall(function()
                if which == "size" then
                    gui:TweenSize(UDimStuff,Enum.EasingDirection.Out,Enum.EasingStyle.Quad,time)
                elseif which == "pos" then
                    gui:TweenPosition(UDimStuff,Enum.EasingDirection.Out,Enum.EasingStyle.Quad,time)
                else
                    local TweenService = game:GetService("TweenService")
                    TweenService:Create(
                            gui,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                        UDimStuff
                    ):Play()
                end
            end)
        end)
    end

    local function UpdateFrameSize(scrollframe,listlayout)
        local cS = listlayout.AbsoluteContentSize

        game.TweenService:Create(scrollframe, TweenInfo.new(0.15, Enum.EasingStyle.Linear, Enum.EasingDirection.In), {
            CanvasSize = UDim2.new(0,cS.X,0,cS.Y)
        }):Play()
    end

    local function hidebindConfig()
        local uis = game:GetService("UserInputService")
        uis.InputBegan:Connect(function(input,chat)
            if chat then return end

            if input.KeyCode == hideBind then
                Tabs.ToggleVisiblity()
            end	
        end)
    end

    local function dragify(Frame)
    dragToggle = nil
    dragSpeed = .25 -- You can edit this.
    dragInput = nil
    dragStart = nil
    dragPos = nil
    
    function updateInput(input)
    Delta = input.Position - dragStart
    Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + Delta.X, startPos.Y.Scale, startPos.Y.Offset + Delta.Y)
    game:GetService("TweenService"):Create(Frame, TweenInfo.new(.25), {Position = Position}):Play()
    end
    
    Frame.InputBegan:Connect(function(input)
    if (input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch) then
    dragToggle = true
    dragStart = input.Position
    startPos = Frame.Position
    input.Changed:Connect(function()
    if (input.UserInputState == Enum.UserInputState.End) then
    dragToggle = false
    end
    end)
    end
    end)
    
    Frame.InputChanged:Connect(function(input)
    if (input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch) then
    dragInput = input
    end
    end)
    
    game:GetService("UserInputService").InputChanged:Connect(function(input)
    if (input == dragInput and dragToggle) then
    updateInput(input)
    end
    end)
    end

    local function Ripple(obj)
        task.spawn(
            function()
                local Mouse = game.Players.LocalPlayer:GetMouse()
                local Circle = Instance.new("ImageLabel")
                Circle.Name = "Circle"
                Circle.Parent = obj
                Circle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                Circle.BackgroundTransparency = 1.000
                Circle.ZIndex = 10
                Circle.Image = "rbxassetid://266543268"
                Circle.ImageColor3 = Color3.fromRGB(211, 211, 211)
                Circle.ImageTransparency = 0.6
                local NewX, NewY = Mouse.X - Circle.AbsolutePosition.X, Mouse.Y - Circle.AbsolutePosition.Y
                Circle.Position = UDim2.new(0, NewX, 0, NewY)
                local Size = 0
                if obj.AbsoluteSize.X > obj.AbsoluteSize.Y then
                    Size = obj.AbsoluteSize.X * 1
                elseif obj.AbsoluteSize.X < obj.AbsoluteSize.Y then
                    Size = obj.AbsoluteSize.Y * 1
                elseif obj.AbsoluteSize.X == obj.AbsoluteSize.Y then
                    Size = obj.AbsoluteSize.X * 1
                end
                Circle:TweenSizeAndPosition(
                    UDim2.new(0, Size, 0, Size),
                    UDim2.new(0.5, -Size / 2, 0.5, -Size / 2),
                    "Out",
                    "Quad",
                    0.2,
                    false
                )
                for i = 1, 15 do
                    Circle.ImageTransparency = Circle.ImageTransparency + 0.05
                    wait()
                end
                Circle:Destroy()
            end
        )
    end

    local FirstTab = false
    local UI = Instance.new("ScreenGui")
    local BG = Instance.new("Frame")
    local UICorner = Instance.new("UICorner")
    local elementFrame = Instance.new("Frame")
    local UICorner_2 = Instance.new("UICorner")
    local GlowFrame = Instance.new("ImageLabel")
    local GlowCorner = Instance.new("UICorner")
    local Color = Instance.new("UIStroke")
    local Color_3 = Instance.new("TextLabel")
    local stroke = Instance.new("Frame")
    local Color_4 = Instance.new("UIStroke")
    local GlowFrame_2 = Instance.new("ImageLabel")
    local GlowCorner_2 = Instance.new("UICorner")
    local tabH = Instance.new("ScrollingFrame")
    local UIListLayout_3 = Instance.new("UIListLayout")
    local seperator = Instance.new("Frame")

    function randomString()
        local length = math.random(10,20)
        local array = {}
        for i = 1, length do
            array[i] = string.char(math.random(32, 126))
        end
        return table.concat(array)
    end

    PARENT = nil
    if get_hidden_gui or gethui then
        local hiddenUI = get_hidden_gui or gethui
        local Main = Instance.new("ScreenGui")
        Main.Name = randomString()
        Main.Parent = hiddenUI()
        PARENT = Main
    elseif (not is_sirhurt_closure) and (syn and syn.protect_gui) then
        local Main = Instance.new("ScreenGui")
        Main.Name = randomString()
        syn.protect_gui(Main)
        Main.Parent = COREGUI
        PARENT = Main
    elseif COREGUI:FindFirstChild('RobloxGui') then
        PARENT = COREGUI.RobloxGui
    else
        local Main = Instance.new("ScreenGui")
        Main.Name = randomString()
        Main.Parent = COREGUI
        PARENT = Main
    end

    UI.Name = "UI"
    UI.Parent = PARENT
    UI.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
    UI.ResetOnSpawn = false
    _G.Library = PARENT

    BG.Name = "BG"
    BG.Parent = UI
    BG.BackgroundColor3 = Color3.fromRGB(27,27,27)
    BG.ClipsDescendants = true
    BG.Position = UDim2.new(0.380143136, 0, 0.367031574, 0)
    BG.Size = UDim2.new(0, 656, 0, 387)

    UICorner.Parent = BG

    elementFrame.Name = "elementFrame"
    elementFrame.Parent = BG
    elementFrame.BackgroundColor3 = Color3.fromRGB(31, 31, 31)
    elementFrame.Position = UDim2.new(0.298690677, 0, 0.148893297, 0)
    elementFrame.Size = UDim2.new(0, 446, 0, 309)

    UICorner_2.Parent = elementFrame

    GlowFrame.Name = "GlowTab"
    GlowFrame.Parent = elementFrame
    GlowFrame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    GlowFrame.BackgroundTransparency = 1.000
    GlowFrame.BorderSizePixel = 0
    GlowFrame.Position = UDim2.new(0, -15, 0, -15)
    GlowFrame.Size = UDim2.new(1, 30, 1, 30)
    GlowFrame.ZIndex = 0
    GlowFrame.Image = "rbxassetid://4996891970"
    GlowFrame.ImageColor3 = mainColor
    GlowFrame.ScaleType = Enum.ScaleType.Slice
    GlowFrame.SliceCenter = Rect.new(20, 20, 280, 280)
    GlowFrame.ImageTransparency = 0

    GlowCorner.Parent = GlowFrame

    Color.Color = mainColor
    Color.Name = "Color"
    Color.Parent = elementFrame
    Color.Thickness = 2
    Color.Transparency = 0.699999988079071

    Color_3.Name = "Color"
    Color_3.Parent = BG
    Color_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    Color_3.BackgroundTransparency = 1.000
    Color_3.BorderColor3 = Color3.fromRGB(27, 42, 53)
    Color_3.Position = UDim2.new(0.0326434411, 0, 0.0310933907, 0)
    Color_3.Size = UDim2.new(0, 630, 0, 27)
    Color_3.Font = Enum.Font.Gotham
    Color_3.Text = winName
    Color_3.TextColor3 = mainColor
    Color_3.TextScaled = true
    Color_3.TextSize = 14.000
    Color_3.TextWrapped = true

    stroke.Name = "stroke"
    stroke.Parent = BG
    stroke.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    stroke.Position = UDim2.new(0.0478682891, 0, 0.122643776, 0)
    stroke.Size = UDim2.new(0, 611, 0, 0)

    Color_4.Color = mainColor
    Color_4.Name = "Color"
    Color_4.Parent = stroke
    Color_4.Thickness = 0.699999988079071

    tabH.Name = "tabH"
    tabH.Parent = BG
    tabH.Active = true
    tabH.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    tabH.BackgroundTransparency = 1.000
    tabH.Position = UDim2.new(-0.000775280409, 0, 0.152454779, 0)
    tabH.Size = UDim2.new(0, 195, 0, 300)
    tabH.ScrollBarThickness = 2

    UIListLayout_3.Parent = tabH
    UIListLayout_3.HorizontalAlignment = Enum.HorizontalAlignment.Center
    UIListLayout_3.SortOrder = Enum.SortOrder.LayoutOrder
    UIListLayout_3.Padding = UDim.new(0, 9)

    tabH.ChildAdded:Connect(function()
        UpdateFrameSize(tabH,UIListLayout_3)
    end)
    
    tabH.ChildRemoved:Connect(function()
        UpdateFrameSize(tabH,UIListLayout_3)
    end)

    seperator.Name = "seperator"
    seperator.Parent = tabH
    seperator.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    seperator.BackgroundTransparency = 1.000
    seperator.Size = UDim2.new(0, 167, 0, 7)
    
    local Tabs = {}

    function Tabs.ToggleVisiblity()
        task.spawn(function()
            UI.Enabled = not UI.Enabled
        end)
    end

    function Tabs.Notify(config)
        local title = config.Title
        local text = config.Text

        task.spawn(function()
            game.StarterGui:SetCore("SendNotification", {
                Title = title;
                Text = text
            })
        end)
    end

    function Tabs.PromptDiscord(discCode)
        task.spawn(function()
            local http
        
            pcall(function()
                http = (syn and syn.request) or (http and http.request) or http_request or (fluxus and fluxus.request) or request
            end)
        
            if http then
                local function join()
                    http(
                        {
                            Url = "http://127.0.0.1:6463/rpc?v=1",
                            Method = "POST",
                            Headers = {
                                ["Content-Type"] = "application/json",
                                ["origin"] = "https://discord.com",
                            },
                            Body = game:GetService("HttpService"):JSONEncode(
                            {
                                ["args"] = {
                                    ["code"] = discCode,
                                },
                                ["cmd"] = "INVITE_BROWSER",
                                ["nonce"] = "."
                            })
                        })
                end
                
                join() 
            end
        end)
    end

    function Tabs.Destroy()
        task.spawn(function()
            UI:Destroy()
        end)
    end

    function Tabs:Tab(tabName)
        local tabButton = Instance.new("Frame")
        local GlowTab = Instance.new("ImageLabel")
        local button = Instance.new("TextButton")
        local UICorner_22 = Instance.new("UICorner")
        local Color_5 = Instance.new("UIStroke")
        local UICorner_23 = Instance.new("UICorner")
        local TabFrame = Instance.new("ScrollingFrame")
        local UIListLayout = Instance.new("UIListLayout")

        tabButton.Name = "tabButton"
        tabButton.Parent = tabH
        tabButton.BackgroundColor3 = mainColor
        tabButton.BackgroundTransparency = 1.000
        tabButton.Position = UDim2.new(0, 0, -0.0152113764, 0)
        tabButton.Size = UDim2.new(0, 167, 0, 24)

        GlowTab.Name = "GlowTab"
        GlowTab.Parent = tabButton
        GlowTab.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        GlowTab.BackgroundTransparency = 1.000
        GlowTab.BorderSizePixel = 0
        GlowTab.Position = UDim2.new(0, -15, 0, -15)
        GlowTab.Size = UDim2.new(1, 30, 1, 30)
        GlowTab.ZIndex = 0
        GlowTab.Image = "rbxassetid://4996891970"
        GlowTab.ImageColor3 = mainColor
        GlowTab.ScaleType = Enum.ScaleType.Slice
        GlowTab.SliceCenter = Rect.new(20, 20, 280, 280)
        GlowTab.ImageTransparency = 1

        button.Name = "button"
        button.Parent = tabButton
        button.BackgroundColor3 = Color3.fromRGB(52, 52, 52)
        button.BackgroundTransparency = 1.000
        button.Position = UDim2.new(0, 0, -0.0138549805, 0)
        button.Size = UDim2.new(0, 167, 0, 24)
        button.Font = Enum.Font.Gotham
        button.Text = tabName
        button.TextColor3 = Color3.fromRGB(255, 255, 255)
        button.TextScaled = false
        button.TextSize = 14.000
        button.TextWrapped = true

        UICorner_22.Parent = button

        Color_5.Color = mainColor
        Color_5.Name = "Color"
        Color_5.Parent = tabButton
        Color_5.Thickness = 2
        Color_5.Transparency = 1

        UICorner_23.Parent = tabButton

        TabFrame.Name = "TabFrame"
        TabFrame.Parent = elementFrame
        TabFrame.Active = true
        TabFrame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        TabFrame.BackgroundTransparency = 1.000
        TabFrame.Position = UDim2.new(0.0134529145, 0, 0.0377753302, 0)
        TabFrame.Size = UDim2.new(0, 440, 0, 289)
        TabFrame.ScrollBarThickness = 5
        TabFrame.Visible = false

    
        UIListLayout.Parent = TabFrame
        UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
        UIListLayout.Padding = UDim.new(0, 5)

        if not FirstTab then
            FirstTab = true
            Color_5.Transparency = 0.2
            TabFrame.Visible = true
            GlowTab.ImageTransparency = 0
            tabButton.BackgroundTransparency = 0
        end

        UpdateFrameSize(TabFrame,UIListLayout)

        TabFrame.ChildAdded:Connect(function()
            UpdateFrameSize(TabFrame,UIListLayout)
        end)

        TabFrame.ChildRemoved:Connect(function()
            UpdateFrameSize(TabFrame,UIListLayout)
        end)

        button.MouseButton1Click:Connect(function()
            if TabFrame.Visible == true then return end

            for _,v in pairs(tabH:GetChildren()) do
                if v:IsA("Frame") and v.Name ~= "seperator" then
                    pcall(function()
                        local stroke = v:FindFirstChildOfClass("UIStroke")
                        task.spawn(function()
                            Tween("Transparency",stroke,{Transparency = 1},.3)
                            Tween("ImageTransparency",v.GlowTab,{ImageTransparency = 1},.3)
                            Tween("BackgroundTransparency",v,{BackgroundTransparency = 1},.3)
                        end)
                    end)
                end
            end

            for _,v in pairs(elementFrame:GetChildren()) do
                if v:IsA("ScrollingFrame") then
                    v.Visible = false
                end
            end

            Tween("Transparency",Color_5,{Transparency = 0.2},.3)
            Tween("ImageTransparency",GlowTab,{ImageTransparency = 0},.3)
            Tween("BackgroundTransparency",tabButton,{BackgroundTransparency = 0},.3)
            TabFrame.Visible = true
        end)

        local Elements = {}

        function Elements:Button(buttonName,callback)
            buttonName = buttonName or "Button"
            callback = callback or function () end

            local Button = Instance.new("TextButton")
            local UICorner_3 = Instance.new("UICorner")

            Button.Name = "Button"
            Button.Parent = TabFrame
            Button.BackgroundColor3 = Color3.fromRGB(37,37,37)
            Button.ClipsDescendants = true
            Button.Size = UDim2.new(0, 424, 0, 24)
            Button.Font = Enum.Font.Gotham
            Button.TextColor3 = Color3.fromRGB(255, 255, 255)
            Button.TextScaled = false
            Button.TextSize = 14.000
            Button.TextWrapped = true
            Button.Text = buttonName
        
            UICorner_3.Parent = Button

            Button.MouseButton1Click:Connect(function()
                Ripple(Button)
                pcall(callback)
            end)

            UpdateFrameSize(TabFrame,UIListLayout)
        end

        function Elements:Toggle(toggleName,currentState,callback)
            toggleName = toggleName or "Toggle"
            currentState = currentState or false
            callback = callback or function () end

            local Toggle = Instance.new("Frame")
            local UICorner_4 = Instance.new("UICorner")
            local name = Instance.new("TextLabel")
            local ToggleBG = Instance.new("Frame")
            local UICorner_5 = Instance.new("UICorner")
            local Ball = Instance.new("Frame")
            local UICorner_6 = Instance.new("UICorner")
            local hitbox = Instance.new("TextButton")
            local UICorner_7 = Instance.new("UICorner")

            Toggle.Name = "Toggle"
            Toggle.Parent = TabFrame
            Toggle.BackgroundColor3 = Color3.fromRGB(37,37,37)
            Toggle.ClipsDescendants = true
            Toggle.Size = UDim2.new(0, 424, 0, 24)

            UICorner_4.Parent = Toggle

            name.Name = "name"
            name.Parent = Toggle
            name.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
            name.BackgroundTransparency = 1.000
            name.Position = UDim2.new(0.0154420389, 0, 0, 0)
            name.Size = UDim2.new(0, 246, 0, 24)
            name.Font = Enum.Font.Gotham
            name.Text = toggleName..":"
            name.TextColor3 = Color3.fromRGB(255, 255, 255)
            name.TextScaled = false
            name.TextSize = 14.000
            name.TextWrapped = true
            name.TextXAlignment = Enum.TextXAlignment.Left

            ToggleBG.Name = "ToggleBG"
            ToggleBG.Parent = Toggle
            ToggleBG.BackgroundColor3 = Color3.fromRGB(26, 26, 26)
            ToggleBG.Position = UDim2.new(0.883972287, 0, 0.125, 0)
            ToggleBG.Size = UDim2.new(0, 41, 0, 18)

            UICorner_5.Parent = ToggleBG

            Ball.Name = "Ball"
            Ball.Parent = ToggleBG
            Ball.BackgroundColor3 = Color3.fromRGB(67, 67, 67)
            Ball.Position = UDim2.new(-0.00882184505, 0, 0, 0)
            Ball.Size = UDim2.new(0, 18, 0, 18)

            UICorner_6.CornerRadius = UDim.new(16, 16)
            UICorner_6.Parent = Ball

            hitbox.Name = "hitbox"
            hitbox.Parent = Toggle
            hitbox.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
            hitbox.BackgroundTransparency = 0.990
            hitbox.Size = UDim2.new(0, 424, 0, 24)
            hitbox.Font = Enum.Font.Gotham
            hitbox.Text = ""
            hitbox.TextColor3 = Color3.fromRGB(0, 0, 0)
            hitbox.TextSize = 14.000

            UICorner_7.Parent = hitbox

            local state = currentState
            local toggleDebounce = false

            if state then
                task.spawn(function()
                    toggleDebounce = true
                    Tween("pos",Ball,UDim2.new(0.552, 0,0, 0),.3)
                    Tween("BackgroundColor",Ball,{BackgroundColor3 = mainColor},.3)
                    task.wait(.3)
                    toggleDebounce = false
                end)
            end

            pcall(callback,state)

            local function ToggleOn()
                Ripple(Toggle)
                state = true
                task.spawn(function()
                    toggleDebounce = true
                    Tween("pos",Ball,UDim2.new(0.552, 0,0, 0),.3)
                    task.delay(0.01,function()
                        repeat task.wait() until Ball.BackgroundColor3 ~= nil
                        Tween("BackgroundColor",Ball,{BackgroundColor3 = mainColor},.3)
                    end)
                    task.wait(.3)
                    toggleDebounce = false
                end)

                pcall(callback,state)
            end

            local function ToggleOff()
                Ripple(Toggle)
                state = false

                task.spawn(function()
                    toggleDebounce = true
                    Tween("pos",Ball,UDim2.new(-0.00882184505, 0, 0, 0),.3)
                    Tween("BackgroundColor",Ball,{BackgroundColor3 = Color3.fromRGB(67, 67, 67)},.3)
                    task.wait(.3)
                    toggleDebounce = false
                end)

                pcall(callback,state)
            end

            hitbox.MouseButton1Click:Connect(function()
                if toggleDebounce then return end
                if state then
                    ToggleOff()
                    return
                end

                ToggleOn()
            end)

            local toggleFunc = {}

            function toggleFunc:GetState()
                return state
            end

            function toggleFunc:SetState(desiredState)
                if desiredState then
                    ToggleOn()
                else
                    ToggleOff()
                end
            end
            
            function toggleFunc:LoadConfig(data)
                if data.Name == toggleName and data.Type == "Toggle" then
                    toggleFunc:SetState(data.Value)
                end
            end
            
            local info = {Name = toggleName,Type ="Toggle",Value = state,Element = toggleFunc}
            
            function toggleFunc:SaveConfig()
                for i,v in pairs(_G.UISettings.ElementCache) do
                    if v.Name == info.Name and v.Type == info.Type then
			v["Value"] = state
                    end
                end
            end
            
            table.insert(_G.UISettings.ElementCache,info)
            
            UpdateFrameSize(TabFrame,UIListLayout)

            return toggleFunc
        end

        function Elements:Slider(sliderName,config,callback)
            sliderName = sliderName or "Slider"
            local def = tonumber(config.def) or 50
            local min = tonumber(config.min) or 0
            local max = tonumber(config.max) or 100
            callback = callback or function() end

            local Slider = Instance.new("Frame")
            local UICorner_8 = Instance.new("UICorner")
            local name_2 = Instance.new("TextLabel")
            local SliderBG = Instance.new("Frame")
            local SliderBGButton = Instance.new("TextButton")
            local UICorner_9 = Instance.new("UICorner")
            local Color_2 = Instance.new("Frame")
            local UICorner_10 = Instance.new("UICorner")
            local amount = Instance.new("TextLabel")

            Slider.Name = "Slider"
            Slider.Parent = TabFrame
            Slider.BackgroundColor3 = Color3.fromRGB(37,37,37)
            Slider.ClipsDescendants = true
            Slider.Size = UDim2.new(0, 424, 0, 24)

            UICorner_8.Parent = Slider

            name_2.Name = "name"
            name_2.Parent = Slider
            name_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
            name_2.BackgroundTransparency = 1.000
            name_2.Position = UDim2.new(0.0154420389, 0, 0, 0)
            name_2.Size = UDim2.new(0, 150, 0, 24)
            name_2.Font = Enum.Font.Gotham
            name_2.Text = sliderName..":"
            name_2.TextColor3 = Color3.fromRGB(255, 255, 255)
            name_2.TextScaled = false
            name_2.TextSize = 14.000
            name_2.TextWrapped = true
            name_2.TextXAlignment = Enum.TextXAlignment.Left

            SliderBG.Name = "SliderBG"
            SliderBG.Parent = Slider
            SliderBG.BackgroundColor3 = Color3.fromRGB(26, 26, 26)
            SliderBG.Position = UDim2.new(0.537450969, 0, 0.25, 0)
            SliderBG.Size = UDim2.new(0, 187, 0, 14)
            SliderBG.ClipsDescendants = true

            SliderBGButton.Name = "SliderBG"
            SliderBGButton.Parent = Slider
            SliderBGButton.BackgroundColor3 = Color3.fromRGB(26, 26, 26)
            SliderBGButton.Position = UDim2.new(0.537450969, 0, 0.25, 0)
            SliderBGButton.Size = UDim2.new(0, 187, 0, 14)
            SliderBGButton.BackgroundTransparency = 0.99
            SliderBGButton.Text = ""

            UICorner_9.Parent = SliderBG

            Color_2.Name = "Color"
            Color_2.Parent = SliderBG
            Color_2.BackgroundColor3 = mainColor
            Color_2.Size = UDim2.new(0, 187, 0, 18)

            UICorner_10.CornerRadius = UDim.new(16, 16)
            UICorner_10.Parent = Color_2

            amount.Name = "amount"
            amount.Parent = Slider
            amount.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
            amount.BackgroundTransparency = 1.000
            amount.Position = UDim2.new(0.370521128, 0, 0.125, 0)
            amount.Size = UDim2.new(0, 68, 0, 21)
            amount.Font = Enum.Font.Gotham
            amount.Text = "56"
            amount.TextColor3 = Color3.fromRGB(255, 255, 255)
            amount.TextScaled = false
            amount.TextSize = 14.000
            amount.TextWrapped = true

            if def > max then 
                def = max
            elseif min < 0 then
                min = 0
            end

            local SliderDef = math.clamp(def, min, max)
            local DefaultScale =  (SliderDef - min) / (max - min)
            local mouse = game.Players.LocalPlayer:GetMouse()
            local uis = game:GetService("UserInputService")
            local SValue;
            local SB = SliderBGButton
            local SV = amount
            local SF = Color_2
            local NormalSizeX = 187
            local NormalSizeY = 14

            SF.Size = UDim2.fromScale(DefaultScale,1)
            SV.Text = tostring(def)
            Value = def
            pcall(callback,Value)

            SB.MouseButton1Down:Connect(function()
                SValue = math.floor((((tonumber(max) - tonumber(min)) / NormalSizeX) * SF.AbsoluteSize.X) + tonumber(min)) or 0
            
            
                SF.Size = UDim2.new(0, math.clamp(mouse.X - SF.AbsolutePosition.X, 0, NormalSizeX), 0, NormalSizeY)
                moveconnection = mouse.Move:Connect(function()
                    SValue = math.floor((((tonumber(max) - tonumber(min)) / NormalSizeX) * SF.AbsoluteSize.X) + tonumber(min))
                    SV.Text = SValue
            
                    pcall(callback,SValue)
            
                    SF.Size = UDim2.new(0, math.clamp(mouse.X - SF.AbsolutePosition.X, 0, NormalSizeX), 0,NormalSizeY)
                end)
            
                releaseconnection = uis.InputEnded:Connect(function(Mouse)
                    if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
                        SValue = math.floor((((tonumber(max) - tonumber(min)) / NormalSizeX) * SF.AbsoluteSize.X) + tonumber(min))
            
                        pcall(callback,SValue)
            
                        SF.Size = UDim2.new(0, math.clamp(mouse.X - SF.AbsolutePosition.X, 0, NormalSizeX), 0, NormalSizeY)
                        moveconnection:Disconnect()
                        releaseconnection:Disconnect()
                    end
                end)
            end)

            local sliderFunc = {}

            function sliderFunc:GetValue()
                return Value
            end

            function sliderFunc:SetValue(desiredValue)
                if tonumber(desiredValue) and desiredValue <= max and desiredValue >= min then
                    local SliderDef = math.clamp(tonumber(desiredValue), min, max)
                    local DefaultScale =  (SliderDef - min) / (max - min)
                    Tween("size",SF,UDim2.fromScale(DefaultScale,1),.3)
                    SV.Text = tostring(desiredValue)
                    Value = desiredValue
                    pcall(callback,Value)
                end
            end

            function sliderFunc:LoadConfig(data)
                if data.Name == sliderName and data.Type == "Slider" then
                    sliderFunc:SetValue(data.Value)
                end
            end
            
            local info = {Name = sliderName,Type ="Slider",Value = SValue,Element = sliderFunc}
            
            function sliderFunc:SaveConfig()
                for i,v in pairs(_G.UISettings.ElementCache) do
                    if v.Name == info.Name and v.Type == info.Type then
                        v["Value"] = SValue or def
                    end
                end
            end
            
            table.insert(_G.UISettings.ElementCache,info)
            
            UpdateFrameSize(TabFrame,UIListLayout)
            
            return sliderFunc
        end

        function Elements:Label(text)
            text = text or ""

            local Label = Instance.new("TextLabel")
            local UICorner_11 = Instance.new("UICorner")

            Label.Name = "Label"
            Label.Parent = TabFrame
            Label.BackgroundColor3 = Color3.fromRGB(37,37,37)
            Label.Size = UDim2.new(0, 424, 0, 24)
            Label.Font = Enum.Font.Gotham
            Label.TextColor3 = Color3.fromRGB(255, 255, 255)
            Label.TextScaled = false
            Label.TextSize = 14.000
            Label.TextWrapped = true
            Label.Text = text

            UICorner_11.Parent = Label

            local labelFunc = {}

            function labelFunc:SetText(txt)
                if typeof(txt) == "string" then
                    Label.Text = txt
                end
            end

            function labelFunc:GetText()
                return Label.Text
            end

            UpdateFrameSize(TabFrame,UIListLayout)

            return labelFunc
        end

        function Elements:Textbox(textboxName,callback)
            local Textbox = Instance.new("Frame")
            local UICorner_12 = Instance.new("UICorner")
            local name_3 = Instance.new("TextLabel")
            local box = Instance.new("Frame")
            local UICorner_13 = Instance.new("UICorner")
            local input = Instance.new("TextBox")

            Textbox.Name = "Textbox"
            Textbox.Parent = TabFrame
            Textbox.BackgroundColor3 = Color3.fromRGB(37,37,37)
            Textbox.ClipsDescendants = true
            Textbox.Size = UDim2.new(0, 424, 0, 24)

            UICorner_12.Parent = Textbox

            name_3.Name = "name"
            name_3.Parent = Textbox
            name_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
            name_3.BackgroundTransparency = 1.000
            name_3.Position = UDim2.new(0.0154420389, 0, 0, 0)
            name_3.Size = UDim2.new(0, 194, 0, 24)
            name_3.Font = Enum.Font.Gotham
            name_3.Text = textboxName..":"
            name_3.TextColor3 = Color3.fromRGB(255, 255, 255)
            name_3.TextScaled = false
            name_3.TextSize = 14.000
            name_3.TextWrapped = true
            name_3.TextXAlignment = Enum.TextXAlignment.Left

            box.Name = "box"
            box.Parent = Textbox
            box.BackgroundColor3 = Color3.fromRGB(26, 26, 26)
            box.BorderColor3 = Color3.fromRGB(27, 42, 53)
            box.Position = UDim2.new(0.537450969, 0, 0.125, 0)
            box.Size = UDim2.new(0, 187, 0, 18)

            UICorner_13.Parent = box

            input.Name = "input"
            input.Parent = box
            input.BackgroundColor3 = Color3.fromRGB(37,37,37)
            input.BackgroundTransparency = 1.000
            input.BorderSizePixel = 0
            input.Size = UDim2.new(0, 187, 0, 18)
            input.Font = Enum.Font.Gotham
            input.Text = ""
            input.TextColor3 = Color3.fromRGB(255, 255, 255)
            input.TextScaled = false
            input.TextSize = 14.000
            input.TextWrapped = true

            input.FocusLost:Connect(function()
                local myText = input.Text
                pcall(callback,myText)
            end)

            local textboxFunc = {}

            function textboxFunc:GetText()
                local myText = input.Text
                return myText
            end

            function textboxFunc:SetText(txt)
                if typeof(txt) == "string" then
                    input.Text = txt
                    local myText = input.Text
                    pcall(callback,myText)
                end
            end
            
            function textboxFunc:LoadConfig(data)
                if data.Name == textboxName and data.Type == "Textbox" then
                    textboxFunc:SetText(data.Value)
                end
            end

            local info = {Name = textboxName,Type ="Textbox",Value = input.Text,Element = textboxFunc}
            
            function textboxFunc:SaveConfig()
                for i,v in pairs(_G.UISettings.ElementCache) do
                    if v.Name == info.Name and v.Type == info.Type then
                        v["Value"] = input.Text
                    end
                end
            end
            
            table.insert(_G.UISettings.ElementCache,info)
            
            UpdateFrameSize(TabFrame,UIListLayout)

            return textboxFunc
        end

        function Elements:Bind(bindName,keycode,callback)
            bindName = bindName or "Bind"
            keycode = keycode or Enum.KeyCode.E
            callback = callback or function () end

            local keyName = tostring(keycode):split(".")[3]

            local Keybind = Instance.new("Frame")
            local UICorner_15 = Instance.new("UICorner")
            local name_4 = Instance.new("TextLabel")
            local ToggleBG_2 = Instance.new("Frame")
            local UICorner_16 = Instance.new("UICorner")
            local key = Instance.new("TextLabel")
            local hitbox_3 = Instance.new("TextButton")
            local UICorner_17 = Instance.new("UICorner")

            Keybind.Name = "Keybind"
            Keybind.Parent = TabFrame
            Keybind.BackgroundColor3 = Color3.fromRGB(37,37,37)
            Keybind.ClipsDescendants = true
            Keybind.Size = UDim2.new(0, 424, 0, 24)

            UICorner_15.Parent = Keybind

            name_4.Name = "name"
            name_4.Parent = Keybind
            name_4.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
            name_4.BackgroundTransparency = 1.000
            name_4.Position = UDim2.new(0.0154420389, 0, 0, 0)
            name_4.Size = UDim2.new(0, 246, 0, 24)
            name_4.Font = Enum.Font.Gotham
            name_4.Text = bindName..":"
            name_4.TextColor3 = Color3.fromRGB(255, 255, 255)
            name_4.TextScaled = false
            name_4.TextSize = 14.000
            name_4.TextWrapped = true
            name_4.TextXAlignment = Enum.TextXAlignment.Left

            ToggleBG_2.Name = "ToggleBG"
            ToggleBG_2.Parent = Keybind
            ToggleBG_2.BackgroundColor3 = Color3.fromRGB(26, 26, 26)
            ToggleBG_2.Position = UDim2.new(0.728031218, 0, 0.125, 0)
            ToggleBG_2.Size = UDim2.new(0, 106, 0, 18)

            UICorner_16.Parent = ToggleBG_2

            key.Name = "key"
            key.Parent = ToggleBG_2
            key.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
            key.BackgroundTransparency = 1.000
            key.Position = UDim2.new(-0.00994582381, 0, 0, 0)
            key.Size = UDim2.new(0, 106, 0, 18)
            key.Font = Enum.Font.Gotham
            key.Text = keyName
            key.TextColor3 = Color3.fromRGB(255, 255, 255)
            key.TextScaled = false
            key.TextSize = 14.000
            key.TextWrapped = true

            hitbox_3.Name = "hitbox"
            hitbox_3.Parent = Keybind
            hitbox_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
            hitbox_3.BackgroundTransparency = 0.990
            hitbox_3.Size = UDim2.new(0, 424, 0, 24)
            hitbox_3.Font = Enum.Font.Gotham
            hitbox_3.Text = ""
            hitbox_3.TextColor3 = Color3.fromRGB(0, 0, 0)
            hitbox_3.TextSize = 14.000

            UICorner_17.Parent = hitbox_3

            local WhitelistedType = {
                [Enum.UserInputType.MouseButton1] = "Mouse1";
                [Enum.UserInputType.MouseButton2] = "Mouse2";
                [Enum.UserInputType.MouseButton3] = "Mouse3";
            };
            local UIS = game:GetService("UserInputService")
            local Binding = false

            hitbox_3.MouseButton1Click:Connect(function()
                local Connection;
                Binding = true
            
                key.Text = ". . .";
            
                Connection = UIS.InputBegan:Connect(function(i,chat)
                    if chat then return end
                    
                    if UI == nil or UI.Parent == nil then
                        Connection:Disconnect()
                        return
                    end

                    if WhitelistedType[i.UserInputType] then
                        key.Text = WhitelistedType[i.UserInputType];
                        keycode = i.UserInputType
                    elseif i.KeyCode ~= Enum.KeyCode.Unknown then
                        keycode = i.KeyCode
                        keyName = tostring(keycode):split(".")[3]
                        key.Text = keyName;
                    else
                        warn("Exception: " .. i.UserInputType .. " " .. i.KeyCode);
                    end;
            

                    Connection:Disconnect();
                end)
            end)

            local Connection2;

            Connection2 = UIS.InputBegan:Connect(function(i,chat)
                if chat then return end
                
                if UI == nil or UI.Parent == nil then
                    Connection2:Disconnect()
                    return
                end
                
                if Binding then
                    Binding = false
                    return;
                end
            
                if (keycode == i.UserInputType or keycode == i.KeyCode) then
                    pcall(callback,keycode)
                end;
            end);

            local bindFunc = {}

            function bindFunc:GetBind()
                return keycode
            end

            function bindFunc:SetBind(EnumK)
                if tostring(EnumK):find("Enum.KeyCode.") then
                    keycode = EnumK
                    keyName = tostring(keycode):split(".")[3]
                    key.Text = keyName
                end
            end
            
            function bindFunc:LoadConfig(data)
                if data.Name == bindName and data.Type == "Bind" then
                    bindFunc:SetBind(data.Value)
                end
            end

            local info = {Name = bindName,Type ="Bind",Value = keycode,Element = bindFunc}
            
            function bindFunc:SaveConfig(data)
                for i,v in pairs(_G.UISettings.ElementCache) do
                    if v.Name == info.Name and v.Type == info.Type then
                        v["Value"] = keycode
                    end
                end
            end

            table.insert(_G.UISettings.ElementCache,info)
            
            UpdateFrameSize(TabFrame,UIListLayout)

            return bindFunc
        end

        function Elements:Dropdown(dropName,list,callback)
            dropName = dropName or "Dropdown"
            list = list or {}
            callback = callback or function () end

            local Dropdown = Instance.new("Frame")
            local UICorner_18 = Instance.new("UICorner")
            local name_5 = Instance.new("TextLabel")
            local hitbox_4 = Instance.new("TextButton")
            local UICorner_19 = Instance.new("UICorner")
            local DropdownList = Instance.new("ScrollingFrame")
            local UIListLayout_2 = Instance.new("UIListLayout")
            local UICorner_20 = Instance.new("UICorner")
            local ImageLabel = Instance.new("ImageLabel")

            Dropdown.Name = "Dropdown"
            Dropdown.Parent = TabFrame
            Dropdown.BackgroundColor3 = Color3.fromRGB(37,37,37)
            Dropdown.Size = UDim2.new(0, 424, 0, 24)
            Dropdown.ClipsDescendants = true

            UICorner_18.Parent = Dropdown

            name_5.Name = "name"
            name_5.Parent = Dropdown
            name_5.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
            name_5.BackgroundTransparency = 1.000
            name_5.Position = UDim2.new(0.0154420389, 0, 0, 0)
            name_5.Size = UDim2.new(0, 246, 0, 24)
            name_5.Font = Enum.Font.Gotham
            name_5.Text = dropName..":"
            name_5.TextColor3 = Color3.fromRGB(255, 255, 255)
            name_5.TextScaled = false
            name_5.TextSize = 14.000
            name_5.TextWrapped = true
            name_5.TextXAlignment = Enum.TextXAlignment.Left

            hitbox_4.Name = "hitbox"
            hitbox_4.Parent = Dropdown
            hitbox_4.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
            hitbox_4.BackgroundTransparency = 0.990
            hitbox_4.Size = UDim2.new(0, 424, 0, 24)
            hitbox_4.Font = Enum.Font.Gotham
            hitbox_4.Text = ""
            hitbox_4.TextColor3 = Color3.fromRGB(0, 0, 0)
            hitbox_4.TextSize = 14.000

            UICorner_19.Parent = hitbox_4

            DropdownList.Name = "DropdownList"
            DropdownList.Parent = TabFrame
            DropdownList.Active = true
            DropdownList.BackgroundColor3 = Color3.fromRGB(42, 42, 42)
            DropdownList.Position = UDim2.new(0, 0, 0.975056946, 0)
            DropdownList.Size = UDim2.new(0, 424, 0, 0)
            DropdownList.ScrollBarImageTransparency = 1
            DropdownList.BorderSizePixel = 0
            DropdownList.Visible = false
            DropdownList.ZIndex = true

            UIListLayout_2.Parent = DropdownList
            UIListLayout_2.SortOrder = Enum.SortOrder.LayoutOrder

            UpdateFrameSize(DropdownList,UIListLayout_2)

            DropdownList.ChildAdded:Connect(function()
                UpdateFrameSize(DropdownList,UIListLayout_2)
            end)

            DropdownList.ChildRemoved:Connect(function()
                UpdateFrameSize(DropdownList,UIListLayout_2)
            end)

            DropdownList:GetPropertyChangedSignal("Size"):Connect(function()
                UpdateFrameSize(TabFrame,UIListLayout)
            end)
            
            UICorner_20.CornerRadius = UDim.new(0, 16)
            UICorner_20.Parent = DropdownList

            ImageLabel.Parent = Dropdown
            ImageLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
            ImageLabel.BackgroundTransparency = 1.000
            ImageLabel.Position = UDim2.new(0.9, 0, 0, 0)
            ImageLabel.Size = UDim2.new(0, 25, 0, 25)
            ImageLabel.Image = "rbxassetid://3926305904"
            ImageLabel.ImageRectOffset = Vector2.new(44, 404)
            ImageLabel.ImageRectSize = Vector2.new(36, 36)
            ImageLabel.ZIndex = 2

            local opened = false
            local dropDebounce = false

            local function ToggleDropdown()
                if dropDebounce then return end

                Ripple(Dropdown)

                if not opened then
                    task.spawn(function()
                        dropDebounce = true
                        DropdownList.Visible = true
                        Tween("size",DropdownList,UDim2.new(0, 424,0, 98),.15)
                        Tween("rotation",ImageLabel,{Rotation = 180},.3)
                        task.wait(.3)
                        DropdownList.ScrollBarImageTransparency = 0
                        opened = true
                        dropDebounce = false
                        UpdateFrameSize(TabFrame,UIListLayout)
                    end)
                elseif opened then
                    task.spawn(function()
                        dropDebounce = true
                        DropdownList.ScrollBarImageTransparency = 1
                        DropdownList.CanvasPosition = Vector2.new(0,0)
                        Tween("size",DropdownList,UDim2.new(0, 424, 0, 0),.15)
                        Tween("rotation",ImageLabel,{Rotation = 0},.3)
                        task.wait(.3)
                        DropdownList.Visible = false
                        opened = false
                        dropDebounce = false
                        UpdateFrameSize(TabFrame,UIListLayout)
                    end)
                end
            end

            local function CreateItem(newItem,index)
                if typeof(newItem) == "Instance" then
                    newItem = newItem.Name
                end

                local item = Instance.new("TextButton")
                local UICorner_21 = Instance.new("UICorner")

                item.Name = "item"
                item.Parent = DropdownList
                item.BackgroundColor3 = Color3.fromRGB(37,37,37)
                item.ClipsDescendants = true
                item.Size = UDim2.new(0, 410, 0, 24)
                item.Font = Enum.Font.Gotham
                item.TextColor3 = Color3.fromRGB(255, 255, 255)
                item.TextScaled = false
                item.TextSize = 14.000
                item.TextWrapped = true
                item.Text = tostring(newItem)

                UICorner_21.Parent = item

                item.MouseButton1Click:Connect(function()
                    name_5.Text = dropName..": "..item.Text
                    pcall(callback,item.Text,index)
                    ToggleDropdown()
                end)
            end


            local function AddItems(listTB)
                local InstanceTable = {}
                local CurrentList = listTB

                for i,v in pairs(listTB) do
                    CreateItem(v,i)
                    if typeof(v) == "Instance" then
                        table.insert(InstanceTable,i,v)
                    end
                end

                if #InstanceTable > 0 then
                    return CurrentList,InstanceTable
                end

                return CurrentList
            end

            local function RemoveAllItems()
                for i,v in pairs(DropdownList:GetChildren()) do
                    if v:IsA("TextButton") then
                        v:Destroy()
                    end
                end
            end

            local CurrentList,InstanceTable = AddItems(list)

            hitbox_4.MouseButton1Click:Connect(function()
                ToggleDropdown()
            end)

            local dropdownFunc = {}

            function dropdownFunc:SetOptions(newList)
                RemoveAllItems()
                CurrentList,InstanceTable = AddItems(newList)
            end

            function dropdownFunc:SetChoice(ch)
                if table.find(CurrentList,ch) then
            local index = table.find(CurrentList,ch)
                    name_5.Text = dropName..": "..ch
                    pcall(callback,ch,index)
                end
            end

        function dropdownFunc:GetChoice()
        local DDChoice = name_5.Text:split(": ")[2]

        if DDChoice ~= nil then
            return DDChoice
        else
            return ""
        end
            end

            function dropdownFunc:GetOptions()
                return CurrentList,InstanceTable
            end

        function dropdownFunc:LoadConfig(data)
                if data.Name == dropName and data.Type == "Dropdown" then
                    dropdownFunc:SetChoice(data.Value)
                end
            end

            local info = {Name = dropName,Type ="Dropdown",Value = dropdownFunc:GetChoice(),Element = dropdownFunc}
            
            function dropdownFunc:SaveConfig(data)
                for i,v in pairs(_G.UISettings.ElementCache) do
                    if v.Name == info.Name and v.Type == info.Type then
                        v["Value"] = dropdownFunc:GetChoice()
                    end
                end
            end

            table.insert(_G.UISettings.ElementCache,info)
            
            UpdateFrameSize(TabFrame,UIListLayout)

            return dropdownFunc
        end

        return Elements
    end

    dragify(BG)
    
    return Tabs
end 

local library = Library
local plr = game.Players.LocalPlayer
local char = plr.Character
local hum = char.Humanoid
local http
pcall(function()
http = (syn and syn.request) or (http and http.request) or http_request or (fluxus and fluxus.request) or request
end)

getgenv().speed = 100

local function SimulateClick(button,cmd)
    pcall(function()
        local string = {
            ha = "MouseButton1Click",
            ez = "MouseButton1Down",
            la = "Activated",
        }
        for i,v in pairs(string) do
            for i,v in pairs(getconnections(button[v])) do
                v[cmd]()
            end
        end
    end)
end

local function Tween(target)
    local speed = getgenv().speed
    local info = TweenInfo.new((target.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude / speed, Enum.EasingStyle.Linear)
    local Tween
    local _,err = pcall(function()
        Tween = game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart, info, {CFrame = target}):Play()
    end);
    
    if Tween ~= nil then repeat task.wait() until (target.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= .1 or game.Players.LocalPlayer.Character.Humanoid.Health <= 0 end
end;

--// GAME FUNCTIONS \\--


local function Tatakai(name)    
    local win = library:Window(name,Color3.fromRGB(90, 113, 150))
    win.PromptDiscord("y7H2qGmNKd")
    
    local main = win:Tab("Main")
    local training = win:Tab("Training")
    local misc = win:Tab("Misc")
    
    local RW
    local AutoRoadwork
    local Items
    local CurrentItem
    local autojobs
    local broomjobactive = false
    local broomjobpart = nil
    local SelectedJob = nil
    local JobBoard = nil
    local Mouse, Backup = game.Players.LocalPlayer:GetMouse();
    local ABItems
    local AutoDeposit
    local AntiStaff
    local AutoPB
    local MinStamValue = 10
    local RegenToValue = 100
    local RegenStamValue = false
    local CurrentlyRegening = false
    local NoCoolDownValue = false
    local NoCooldownSpeedValue = 1
    local NoCDRegenValue = false
    local NoCDRegen = false
    local AutoEatValue = false
    local AutoEatSelected = nil
    local AutoEatPercentage = 10
    local AutoEXPValue = false
    local AutoEXPSelected = nil
    local AutoMangoValue = false
    local TrainValue = false
    local SelectedTool = nil
    local PerfectBlockRange = 10
    local PBRun = 9
    local AutoMeditate = false
    local Trainer
    local SpecialTrainer
    local AutoPullups
    local JobPickedUp = nil
    local AutoBags
    local BagMacro
    local AutoReroll = false
    local DesiredRarity = nil
    local AutoBuyTraining
    local AutoBuyFood
    local AutoBuyEXP
    local baseplate
    local JobFuncs = {
        Briefcase = function()
            local Quest = plr.Character:FindFirstChild("Quest")
            local Briefcase = workspace.Quests.QuestLocations.Briefcase:FindFirstChild(tostring(Quest.Location.Value))
            if JobPickedUp == nil then
               task.wait(15) 
            else
                repeat task.wait() until (tick() - JobPickedUp) >= 15
            end
            plr.Character.HumanoidRootPart.CFrame = Briefcase.Case.CFrame
            task.wait()
            fireproximityprompt(Briefcase.ProximityPrompt)
            task.wait()
        end,
        
        Cat = function()
            local Quest = plr.Character:FindFirstChild("Quest")
            local Cat = workspace.Quests.QuestLocations.Cat:FindFirstChild(tostring(Quest.Location.Value))
            if JobPickedUp == nil then
               task.wait(15) 
            else
                repeat task.wait() until (tick() - JobPickedUp) >= 15
            end
            plr.Character.HumanoidRootPart.CFrame = Cat.CFrame
            task.wait()
            fireproximityprompt(Cat.ProximityPrompt)
            task.wait()
        end,
        
        Delivery = function()
            local Quest = plr.Character:FindFirstChild("Quest")
            local Delivery = workspace.Quests.QuestLocations.Delivery:FindFirstChild(tostring(Quest.Location.Value))
            if JobPickedUp == nil then
               task.wait(15) 
            else
                repeat task.wait() until (tick() - JobPickedUp) >= 15
            end
            plr.Character.HumanoidRootPart.CFrame = Delivery.CFrame
            task.wait()
            firetouchinterest(plr.Character.HumanoidRootPart,Delivery,0)
            task.wait()
            firetouchinterest(plr.Character.HumanoidRootPart,Delivery,1)
        end,
        
        Poster = function()
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(Vector3.new(0,-499,0))
            task.wait(2)
            -- repeat 
            --     task.wait()
            --     for i,v in pairs(workspace.Quests.Misc.Posters:GetChildren()) do
            --         if plr.Character:FindFirstChild("Quest") then
            --             if v.Decal.Transparency == 1 then
            --               repeat task.wait()
            --               plr.Character.HumanoidRootPart.CFrame = v.CFrame
            --               task.wait(0.5)
            --               fireproximityprompt(v.ProximityPrompt)
            --               task.wait(0.5)
            --               until v.Decal.Transparency == 0 or plr.Character:FindFirstChild("Quest") == nil
            --                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = jobbaseplate.CFrame + Vector3.new(0,10,0)
            --                 task.wait(1.5)
            --             end
            --         end
            --     end
            -- until plr.Character:FindFirstChild("Quest") == nil or autojobs == false
        end,
        
        Graffiti = function()
            repeat 
                task.wait()
                for i,v in pairs(workspace.Quests.Misc.Graffiti:GetChildren()) do
                    if plr.Character:FindFirstChild("Quest") and v:FindFirstChild("Decal") then
                        if v.Decal.Transparency == 0 then
                           repeat task.wait()
                           plr.Character.HumanoidRootPart.CFrame = v.CFrame
                           task.wait(0.1)
                           fireproximityprompt(v.ProximityPrompt)
                           task.wait(0.1)
                           until v.Decal.Transparency == 1 or plr.Character:FindFirstChild("Quest") == nil
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = jobbaseplate.CFrame + Vector3.new(0,10,0)
                             task.wait(1.5)
                        end
                    end
                end
            until plr.Character:FindFirstChild("Quest") == nil or autojobs == false
            task.wait(1)
        end,
    }

    local ClansRarities = {
        ["Godly"] = {},
        ["Mythical"] = {},
        ["Legendary"] = {},
        ["Rare"] = {"Senkō"},
        ["Common"] = {"Bakufū"},
        ["Uncommon"] = {},
    }
    
    local ClanColors = {
        ["Godly"] = Color3.fromRGB(255,255,255),
        ["Mythical"] = Color3.fromRGB(145, 73, 217),
        ["Legendary"] = Color3.fromRGB(61, 182, 182),
        ["Rare"] = Color3.fromRGB(255, 0, 0),
        ["Common"] = Color3.fromRGB(233, 155, 0),
        ["Uncommon"] = Color3.fromRGB(66, 198, 0),
    }
    
    local function GetAllClans()
        pcall(function()
            for i,v in pairs(game:GetService("Players").LocalPlayer.PlayerGui.MainGui.NEWSHOPFRAME["NEW-SHOP"].Main.Chances.Clans:GetChildren()) do
                if v:IsA("TextLabel") and v.Name ~= "Seperator" then
                    for rarity,color in pairs(ClanColors) do
                        if v.TextColor3 == color or v:FindFirstChild("UIGradient") then
                            if v.Name:find("Senk") == nil and v.Name:find("Bakuf") == nil and v:FindFirstChild("UIGradient") == nil then
                                table.insert(ClansRarities[rarity],v.Name)
                            elseif v:FindFirstChild("UIGradient") and table.find(ClansRarities["Godly"],v.Name) == nil then
                                table.insert(ClansRarities["Godly"],v.Name)
                            end
                        end
                    end
                end
            end
        end)
    end
    pcall(function()
    GetAllClans()
    end)
    
    local function IsWantedClan(c)
        if ClansRarities[DesiredRarity:split("+")[1]] == nil then print("FALSE TRUE") return true end
        local Rarity = DesiredRarity:split("+")[1]
        local CurrentClanRarity = nil
        local MaxNum = nil
        local ClanNum = nil
        local RarityRanking = {
            [1] = "Godly",
            [2] = "Mythical",
            [3] = "Legendary",
            [4] = "Rare",
            [5] = "Common",
            [6] = "Uncommon",
        }
        
        for i,v in pairs(ClansRarities) do
            if table.find(v,c) then
               CurrentClanRarity = i 
            end
        end
        
        for i,v in pairs(RarityRanking) do
            if CurrentClanRarity == v then
               ClanNum = i 
            end
            
            if Rarity == v then
                MaxNum = i
            end
        end
    
        if ClanNum <= MaxNum then
           return true 
        end
        
        return false
    end
    
    

    local function GetItems(query)
        local dump = {}
        
        for i,v in pairs(game:GetService("Workspace").Items:GetChildren()) do
            local Item = v:FindFirstChildOfClass("Model")
            if query ~= nil then if Item.Name:find(query) then table.insert(dump,Item) end end
            
            if query == nil then
               table.insert(dump,Item) 
            end
        end
        
        if #dump == 1 and query ~= nil then
           return dump[1]
        end
        
        return dump
    end
    
    local function GetTrainers(query)
        local dump = {}
        
        for i,Item in pairs(game:GetService("Workspace").Trainers:GetChildren()) do
            if query ~= nil then if Item.Name:find(query) then return Item end end
            
            table.insert(dump,Item)
        end
        
        return dump
    end
    
    local function GetSpecialTrainer(query)
        local dump = {}
        
        for i,Item in pairs(game:GetService("Workspace").SpecialTrainers:GetChildren()) do
            if query ~= nil then if Item.Name:find(query) then return Item end end
            
            table.insert(dump,Item)
        end
        
        return dump
    end
    
    local function ClosestPullups()
        local PU,bestdist = nil,nil
        
        for i,v in pairs(workspace.TrainingStations:GetChildren()) do
            local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Main.Position).Magnitude
            
            if distance <= 100 then
               if bestdist == nil and PU == nil or distance < bestdist then
                  PU = v
                  bestdist = distance
               end
            end
        end
        
        return PU
    end
    
    local function IsStaff(v)
        local wantedroles = {"Mods","Admin","Devs","Ciro","Owner/Head Dev"}
    
        if table.find(wantedroles,v:GetRoleInGroup(6738632)) and AntiStaff then
            plr:Kick(v.Name.."/"..v.DisplayName.." | "..v:GetRoleInGroup(6738632))
            return
        elseif table.find(wantedroles,v:GetRoleInGroup(6738632)) and not AntiStaff then
            win.Notify({
                Title = "Staff Joined!",
                Text = v.Name.."/"..v.DisplayName.." | "..v:GetRoleInGroup(6738632),
            })
        end
    end
    
     local cglove
        local oglove
        
        pcall(function()
        if GetItems("Gloves")[1].Head.CFrame == CFrame.new(-2515.36035, -32.9301071, -2185.9397, 0, 1, -0, -1, 0, 0, 0, 0, 1) then
           oglove = GetItems("Gloves")[1]
           cglove = GetItems("Gloves")[2]
        else
            oglove = GetItems("Gloves")[2]
           cglove = GetItems("Gloves")[1]
        end
	   end)
        
        local function GetMacroableBag()
            local bags = {}
            
            for i,v in pairs(workspace["Punching Bags"]:GetChildren()) do
                if v.CFrame == CFrame.new(-2246.57056, 22.8852634, -2967.98169, 0, 0, -1, 0, 1, 0, 1, 0, 0) then return v end
                table.insert(bags,v.HumanoidRootPart.CFrame * CFrame.new(0,0, -3))
            end
            
            return bags
        end
        
        local function GetClosestGlove()
           local CiroGlove = CFrame.new(-2252.96191, 20.8684731, -2981.34741, -0.985489786, 1.992841e-09, 0.169734687, 2.82447621e-09, 1, 4.65816186e-09, -0.169734687, 5.06998221e-09, -0.985489786)
           local OtherGlove = CFrame.new(-2511.62134, -35.1100082, -2190.42041, -0.0128363743, -5.88145852e-08, 0.999917626, 1.31337954e-08, 1, 5.89880358e-08, -0.999917626, 1.38899061e-08, -0.0128363743)
           local CiroGloveDist = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - CiroGlove.Position).Magnitude
           local OtherGloveDist = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - OtherGlove.Position).Magnitude
           
           if CiroGloveDist < OtherGloveDist then
              return CiroGlove,cglove,"Ciro"
           else
               return OtherGlove,oglove,"Other"
           end
        end

        function PathFind(destin)
            -- SERVICES
            local PFS = game:GetService("PathfindingService")
            
            -- PATH OBJECT
            local path = PFS:CreatePath()
            local hum = game.Players.LocalPlayer.Character.Humanoid
            
            local currentPosition = destin
            local success, errorMsg = pcall(function()
            	path:ComputeAsync(game.Players.LocalPlayer.Character.Torso.Position, currentPosition.Position)
            end)
            
            if success and path.Status == Enum.PathStatus.Success then
            	local waypoints = path:GetWaypoints()
            	
            	for _, waypoint in pairs(waypoints) do
            	    if AutoBags == false then return end
            		if waypoint.Action == Enum.PathWaypointAction.Jump and hum.Jump == false then
            			hum.Jump = true
            			wait()
            			hum.Jump = false
            		end
            		
            		hum:MoveTo(waypoint.Position)
            		hum.MoveToFinished:Wait()
            	end
            	return true
            elseif path.Status == Enum.PathStatus.NoPath then
            	print("No possible path")
            	return nil
            else
            	warn("Failed to compute path: ", errorMsg)
            	return nil
            end
        end
        
        local DoubleBagLocations = {
            CFrame.new(-2502.60522, -35.1100159, -2201.4895, 0.697274685, -3.03720142e-08, -0.716804028, 4.21842294e-09, 1, -3.82679417e-08, 0.716804028, 2.36594833e-08, 0.697274685),
            CFrame.new(-2495.94897, -35.1100082, -2201.2417, 0.79014641, -6.81489171e-11, -0.612918139, 2.72285074e-08, 1, 3.49905775e-08, 0.612918139, -4.43365238e-08, 0.79014641),
            CFrame.new(-2489.47144, -35.1100082, -2200.52148, 0.862319887, 7.66863266e-08, -0.506363928, -1.53960489e-08, 1, 1.25226165e-07, 0.506363928, -1.00189006e-07, 0.862319887),
            CFrame.new(-2516.74902, -35.1100082, -2214.73975, 0.711256325, 5.54889112e-08, -0.702932775, 1.70680767e-08, 1, 9.62093267e-08, 0.702932775, -8.04271991e-08, 0.711256325),
            CFrame.new(-2555.80493, -35.1100082, -2217.39917, -0.631979525, -1.45295198e-08, 0.774985075, -4.09972334e-10, 1, 1.84138074e-08, -0.774985075, 1.13194263e-08, -0.631979525),
            CFrame.new(-2555.1355, -35.1100082, -2178.27856, -0.822276056, 2.92397839e-08, -0.569088876, 8.19409252e-08, 1, -6.70163729e-08, 0.569088876, -1.01737626e-07, -0.822276056),
        }
        
        local function GetBagPosition(v)
           local ClosestGlove,GloveBuy,GloveType = GetClosestGlove()
           
           if GloveType == "Other" then
               
              for i,cf in pairs(DoubleBagLocations) do
                 --print((cf.Position - v.HumanoidRootPart.Position).Magnitude)
                 
                 if (cf.Position - v.HumanoidRootPart.Position).Magnitude <= 5 then
                    game.StarterGui:SetCore("SendNotification", {
                    Title = "Tatakai Auto Bags";
                    Text = "Double Bag Mode!";
                    Duration = "300";
                    })
                    return cf 
                 end
              end
           end
           
           return (v.HumanoidRootPart.CFrame * CFrame.new(0,0,-3)) 
        end
        
        local function BagShit(chosenBag)
            local GB = game.Players.LocalPlayer.Backpack:FindFirstChild("Gloves")
            local GC = game.Players.LocalPlayer.Character:FindFirstChild("Gloves")
            
            if GB == nil and GC == nil then
                game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
               if BagMacro and (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - GetMacroableBag().HumanoidRootPart.Position).Magnitude <= 7 then
                   local gloveloc,glovebuy = GetClosestGlove()
                   
                   fireproximityprompt(glovebuy.Head.ProximityPrompt)
                   task.wait()
               else
                   local gloveloc,glovebuy = GetClosestGlove()
                   
                  local GlovePath = PathFind(gloveloc)
                  if GlovePath ~= true then return end
                   
                   fireproximityprompt(glovebuy.Head.ProximityPrompt)
                   task.wait()
               end
               if game.Players.LocalPlayer.Character.Humanoid.Health <= 35 then
                  repeat task.wait() until game.Players.LocalPlayer.Character.Humanoid.Health >= game.Players.LocalPlayer.Character.Humanoid.MaxHealth 
               end
            elseif GB ~= nil and GC == nil then
                GB.Parent = game.Players.LocalPlayer.Character
                task.wait()
            elseif GB == nil and GC ~= nil then
                local BagPath = PathFind(GetBagPosition(chosenBag))
                if BagPath ~= true then return end
                GC:Activate()
                task.wait(0.5)
                game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
                task.wait()
                game.Players.LocalPlayer.Backpack:FindFirstChild("Combat").Parent = game.Players.LocalPlayer.Character
                task.wait()
                
                repeat
                    task.wait()
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("LeftGloves") ~= nil then
                        game:GetService("Players").LocalPlayer.Character.Combat:Activate()
                        task.wait(0.1)
                    end
                until game:GetService("Players").LocalPlayer.Character:FindFirstChild("LeftGloves") == nil or AutoBags == false
            end
        end
    
    pcall(function()
    Items = GetItems()
    Trainer = GetTrainers()
    SpecialTrainer = GetSpecialTrainer()
    RW = GetItems("Roadwork")
    end)

    training:Dropdown("Training",{
		"200 KG Dumbbell",
		"100 KG Dumbbell",
		"50 KG Dumbbell",
		"20 KG Dumbbell",
		"Pushup Training",
		"Handstand Pushup Training",
		"One-Hand Pushup Training",
        "Situp Training",
        "Burpee Training",
        "Squat Training",
        "Jumping Rope",
        "Meditate",
        "",
	},function(Value)
	    SelectedTool = Value
	end)
	
    training:Slider("Min Stam %",{def=10,max=100,min=0},function(Value)
        MinStamValue = Value
    end)
    
    training:Slider("Regen to %",{def=100,max=100,min=0},function(Value)
        RegenToValue = Value
    end)

    training:Toggle("Regen Stam | On/Off",false,function(Value)
        RegenStamValue = Value
        
        while task.wait() and RegenStamValue do
        pcall(function()
        if RegenStamValue == true then
        local Percentage = (plr.Stamina.Value / plr.Stamina.MaxValue) * 100
        if Percentage <= MinStamValue then
        repeat task.wait() print("Regening Stam") local Percentage = (plr.Stamina.Value / plr.Stamina.MaxValue) * 100 CurrentlyRegening = true until Percentage >= RegenToValue or RegenStamValue == false
        CurrentlyRegening = false
        end
        end
        end)
        end
    end)
    
    training:Toggle("Auto Pullups",false,function(Value)
        AutoPullups = Value
        
        while task.wait() and AutoPullups do
            local Pullup = ClosestPullups()
        
            if (Pullup.Main.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 5 then
                if game.Players.LocalPlayer.Character:FindFirstChild("Pullup") then
                    local vim = game:GetService("VirtualInputManager")
                    vim:SendMouseButtonEvent(0, 500, 0, true, game, 1)
                	vim:SendMouseButtonEvent(0, 500, 0, false, game, 1)
                	task.wait(0.5)
                else
                    fireproximityprompt(Pullup.Main.ProximityPrompt)
                end
            else
               game.Players.LocalPlayer.Character.Humanoid:MoveTo(Pullup.Main.Position) 
            end
        end
    end)
    
    training:Toggle("Auto Bags",false,function(Value)
        AutoBags = Value
        
        if AutoBags == false then return end

        local Mouse = game.Players.LocalPlayer:GetMouse()
        local chosenBag = nil
        local bagesps = {}
        
        local function turnoffbagesp()
            for i,v in pairs(bagesps) do
               game.Debris:AddItem(v,0.01) 
            end
        end
        local bagespfunc = Instance.new("BindableFunction")
        bagespfunc.OnInvoke = turnoffbagesp
        
        game.StarterGui:SetCore("SendNotification", {
            Title = "Tatakai Auto Bags";
            Text = "Hover and Click over the bag you want to use!";
            Duration = "300";
        })
        
        local startedfunc = tick()
        
        while chosenBag == nil and task.wait() do
           if tostring(Mouse.Target) == "HumanoidRootPart" and Mouse.Target.Parent.Name == "Punching Bag" and game:GetService("UserInputService"):IsMouseButtonPressed(Enum.UserInputType.MouseButton1) then
              chosenBag = Mouse.Target.Parent
                game.StarterGui:SetCore("SendNotification", {
                    Title = "Tatakai Auto Bags";
                    Text = "Highlighted Selected Bag! Press OK to turn off";
                    Duration = math.huge;
                    Button1 = "OK";
                    Callback = bagespfunc
                })
            
                local bagesp = Instance.new("BoxHandleAdornment",game.CoreGui)
                bagesp.Color3 = Color3.fromRGB(242,243,243)
                bagesp.Transparency = 0.3
                bagesp.Size = chosenBag.HumanoidRootPart.Size
                bagesp.ZIndex = 10
                bagesp.Adornee = chosenBag.HumanoidRootPart
                bagesp.AlwaysOnTop = true
                bagesp.Visible = true
                
                bagesps[#bagesps+1] = bagesp
                break
           elseif (tick() - startedfunc) >= 20 then
               game.StarterGui:SetCore("SendNotification", {
                Title = "Tatakai Auto Bags";
                Text = "Bag Selection Timed out!";
                Duration = "300";
                })
                break
           end
        end

        while task.wait() and AutoBags do
          BagShit(chosenBag)
        end
    end)
    
    training:Toggle("Bag Macro",false,function(Value)
        BagMacro = Value
    end)
    
    local MultiTool = false
    workspace.DescendantAdded:Connect(function()
    	pcall(function()
    	    if MultiTool then
    		    game.Players.LocalPlayer.Character.Humanoid.Training:Destroy()
    		end
    	end)
    end)
    
    local nocdcounter = training:Label("NoCD Speed: 0 trainings per second")
    training:Label("(nocd only works for dumbbells and meditate)")
    
    training:Toggle("NoCD Mode | On/Off",false,function(Value)
        NoCoolDownValue = Value
        
        while task.wait() and NoCoolDownValue do
    	wait(NoCooldownSpeedValue/10)
    	local Success, Error = pcall(function()
    	if TrainValue == true then
    	if NoCoolDownValue == true then
    	if SelectedTool ~= nil then
    	if plr.Backpack:FindFirstChild(SelectedTool) then plr.Backpack[SelectedTool].Parent = plr.Character end
    	if CurrentlyRegening == false then
    	char.Humanoid:EquipTool(char[SelectedTool])
    	end 
    	end
    	end
    	end
    	end)
    	end
    end)
        
    training:Toggle("NoCD Regen | On/Off",false,function(Value)
        NoCDRegenValue = Value
        
        if NoCDRegenValue then
            while task.wait(2.7) and NoCDRegenValue do
        		if NoCDRegenValue == true then
            		NoCDRegen = true
            		task.wait(1.1)
            		NoCDRegen = false
        	    end
            end
	    end
    end)
    
    local rigged = {}
    local NoCdTick = 0
    local LastNoCDTick = tick()
    
    local MultiTool = false
    workspace.DescendantAdded:Connect(function()
    	pcall(function()
    	    if MultiTool then
    		    game.Players.LocalPlayer.Character.Humanoid.Training:Destroy()
    		end
    	end)
    end)
    
    training:Toggle("MultiTool Mode | HAVE REGEN ON",false,function(Value)
        MultiTool = Value
    end)
    
    training:Toggle("Training | On/Off",false,function(Value)
        TrainValue = Value
        
        if TrainValue then
            trainconnection = game:GetService"RunService".RenderStepped:Connect(function()
        	if rigged[SelectedTool] ~= true and SelectedTool ~= nil then
        	    if SelectedTool == "Meditate" or SelectedTool:find("Dumbbell") then
                if plr.Backpack:FindFirstChild(SelectedTool) then
                   rigged[SelectedTool] = true
                   
                   if plr.Backpack[SelectedTool]:FindFirstChild("LocalScript") then
                      plr.Backpack[SelectedTool]:FindFirstChild("LocalScript"):Destroy() 
                   end
                   plr.Backpack[SelectedTool].KeyEvent.OnClientInvoke = function(Key)
                		if TrainValue ~= true then return end
                		
                		NoCdTick = NoCdTick + 1

                        if (tick() - LastNoCDTick) >= 1 then
                            AfterTick = NoCdTick
                            LastNoCDTick = tick();
                            NoCdTick = 0
                        end
                        
                        nocdcounter:SetText("NoCD Speed: "..AfterTick.." trainings per second")
                        
                        if CurrentlyRegening == false then
                		local Percentage = (plr.Stamina.Value / plr.Stamina.MaxValue) * 100
                		if Percentage >= MinStamValue then
                    	if NoCDRegen == true then
                    	repeat wait() until NoCDRegen == false
                    	end
                    		return Key
                    		end
                    	end
                   end
                else
                    rigged[SelectedTool] = true
                    
                    if char[SelectedTool]:FindFirstChild("LocalScript") then
                      char[SelectedTool]:FindFirstChild("LocalScript"):Destroy() 
                   end
                    
        	        char[SelectedTool].KeyEvent.OnClientInvoke = function(Key)
                		if TrainValue ~= true then return end
                		NoCdTick = NoCdTick + 1

                        if (tick() - LastNoCDTick) >= 1 then
                            AfterTick = NoCdTick
                            LastNoCDTick = tick();
                            NoCdTick = 0
                        end
                        
                        nocdcounter:SetText("NoCD Speed: "..AfterTick.." trainings per second")
                        
                		if CurrentlyRegening == false then
                		local Percentage = (plr.Stamina.Value / plr.Stamina.MaxValue) * 100
                		if Percentage >= MinStamValue then
                    	if NoCDRegen == true then
                    	repeat wait() until NoCDRegen == false
                    	end
                    		return Key
                    		end
                    	end
                   end
                end
                end
            end
        	
        	if not TrainValue then trainconnection:Disconnect() return end
        	if TrainValue == true then
        	if SelectedTool ~= nil then
        	if SelectedTool == "Meditate" or SelectedTool:find("Dumbbell") then return end
        	if CurrentlyRegening == false then
        	local Percentage = (plr.Stamina.Value / plr.Stamina.MaxValue) * 100
        	if Percentage >= MinStamValue then
        	if not char:FindFirstChild(SelectedTool) and plr.Backpack:FindFirstChild(SelectedTool) then plr.Backpack:FindFirstChild(SelectedTool).Parent = char end
        	char:FindFirstChild(SelectedTool):Activate()
        	elseif Percentage <= MinStamValue then
        	if char:FindFirstChild(SelectedTool) then char:FindFirstChild(SelectedTool).Parent = plr.Backpack end
        	end 
        	end
        	end
        	end
            end)
	    end
    end)
    
    training:Button("TP to SafeSpot",function()
        if baseplate == nil then
           baseplate = Instance.new("Part")
            baseplate.Parent = workspace
            baseplate.Size = Vector3.new(100,5,100) 
            baseplate.Anchored = true
            baseplate.Position = game.Players.LocalPlayer.Character.HumanoidRootPart.Position + Vector3.new(math.random(100,1000),-300,math.random(100,1000))
        end
        task.wait(1)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = baseplate.CFrame + Vector3.new(0,10,0)
    end)
    
    training:Toggle("Auto Buy While Training",false,function(Value)
        AutoBuyTraining = Value
        
        while task.wait() and AutoBuyTraining do
             if TrainValue or AutoPullups or AutoMeditate then
                if AutoBuyFood ~= nil then
                   if game.Players.LocalPlayer.Character:FindFirstChild(AutoBuyFood) == nil and game.Players.LocalPlayer.Backpack:FindFirstChild(AutoBuyFood) == nil then 
                       local Food = GetItems(AutoBuyFood)
                       
                       local meh = tick()
                       repeat
                           task.wait(0.1)
                           fireproximityprompt(Food.Head.ProximityPrompt)
                       until (tick() - meh) >= 7
                      
                   end
                end
                
                if AutoBuyEXP ~= nil then
                   if game.Players.LocalPlayer.Character:FindFirstChild(AutoBuyEXP) == nil and game.Players.LocalPlayer.Backpack:FindFirstChild(AutoBuyEXP) == nil then
                        local EXP = GetItems(AutoBuyEXP)
                     
                       local meh = tick()
                       repeat
                           task.wait(0.1)
                           fireproximityprompt(EXP.Head.ProximityPrompt)
                           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = EXP.Head.CFrame
                       until (tick() - meh) >= 7 or AutoBuyTraining == false
                   end 
                end
            end
        end
    end)
    
    training:Dropdown("Auto Buy Food",{"Ramen","Burger"},function(Value)
        AutoBuyFood = Value
    end)
    
    training:Dropdown("Auto Buy EXP",{"Chicken","Chocolate Shake","Protein Shake"},function(Value)
        AutoBuyEXP = Value
    end)
    
    training:Dropdown("Auto Eat",{"Ramen","Burger"},function(Value)
        AutoEatSelected = Value
    end)

    training:Slider("AutoEat %",{def=100,max=100,min=0},function(Value)
        AutoEatPercentage = Value
    end)
    
    local eatingrn = false
    
    training:Toggle("Auto Eat | On/Off",false,function(Value)
        AutoEatValue = Value
        
        while task.wait() and AutoEatValue do
    	pcall(function()
    	if AutoEatValue == true then
    	if AutoEatSelected ~= nil then
    	local HungerCheck = (plr.PlayerGui.MainGui.StatusFrame.Hunger.Bar.AbsoluteSize.X/plr.PlayerGui.MainGui.StatusFrame.Hunger.AbsoluteSize.X * 100)
    	if HungerCheck <= AutoEatPercentage and not eatingrn then
    	plr.Backpack[AutoEatSelected].Parent = char
    	char:FindFirstChild(AutoEatSelected):Activate()
    	eatingrn = true
    	task.wait(10)
    	eatingrn = false
    	end
    	end
    	end
    	end)
    	end
    end)

    training:Dropdown("Auto EXP",{"Chicken","Chocolate Shake","Protein Shake"},function(Value)
        AutoEXPSelected = Value
    end)
    
    training:Toggle("Auto EXP | On\Off",false,function(Value)
        AutoEXPValue = Value
        
        while task.wait() and AutoEXPValue do
    	pcall(function()
    	if AutoEXPValue == true then
    	if AutoEXPSelected ~= nil then
    	if not plr:FindFirstChild("XPBoost") and not char:FindFirstChild(AutoEXPSelected) then
    	if plr.Backpack:FindFirstChild(AutoEXPSelected) then
    	plr.Backpack[AutoEXPSelected].Parent = char
    	char:FindFirstChild(AutoEXPSelected):Activate()
	    task.wait(10)
    	end
    	end
    	end
    	end
    	end)
    	end
    end)
    
    training:Toggle("Auto Mango | On/Off",false,function(Value)
        AutoMangoValue = Value
        
        while task.wait() and AutoMangoValue do
    	pcall(function()
    	if AutoMangoValue == true then
    	if not plr:FindFirstChild("EnergyBoost") and not char:FindFirstChild("Mango Shake") then
    	if plr.Backpack:FindFirstChild("Mango Shake") then
    	plr.Backpack["Mango Shake"].Parent = char
    	char:FindFirstChild("Mango Shake"):Activate()
	    task.wait(10)
    	end
    	end
    	end
    	end)
    	end
    end)
    
    
    
    -- main:Toggle("Auto Job(RISKY)",false,function(Value)
    --     autojobs = Value
        
    --     if autojobs then
    --       task.spawn(function()
    --           while task.wait() and autojobs do
    --               pcall(function()
    --               if game.Players.LocalPlayer.Character.HumanoidRootPart.Anchored then
    --                  for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
    --                   pcall(function()
    --                       v.Anchored = false
    --                   end)
    --                 end
    --               end
    --               end)
    --           end
    --       end)
    --     end
        
    --     while task.wait() and autojobs do
    --         pcall(function()
    --             local QuestCD = plr.Character:FindFirstChild("QuestCD")
    --             local Quest = plr.Character:FindFirstChild("Quest")
                
    --             game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = jobbaseplate.CFrame + Vector3.new(0,10,0)
                
    --             if QuestCD then QuestCD:Destroy() end
    --             if Quest and autojobs then
    --                 if JobFuncs[Quest.PlayerQuest.Value] then
    --                     JobFuncs[Quest.PlayerQuest.Value]()
    --                 end
    --             else
    --                 if autojobs ~= true then return end
    --                 SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.MainGui.PhoneFrame.Jobs,"Function")
    --                 task.wait()
    --                 JobPickedUp = tick()
    --             end
    --         end)
    --     end
    -- end)
    
    misc:Toggle("Auto Deposit",false,function(Value)
        AutoDeposit = Value
        
        while AutoDeposit and task.wait() do
            pcall(function()
                local cashtxt = game:GetService("Players").LocalPlayer.PlayerGui.MainGui.Cash.Text
                
                if cashtxt ~= "$0" then
                    local depamt = cashtxt:split("$")[2]
                    
                    if depamt:find(",") then
                       depamt = depamt:gsub(",","")
                    end
                    
                    local args = {
                        [1] = "Deposit",
                        [2] = tonumber(depamt)
                    }
                    
                    game:GetService("ReplicatedStorage"):WaitForChild("Bank"):InvokeServer(unpack(args))
                end
            end)
        end
    end)
    
    -- main:Toggle("Auto Roadwork",false,function(Value)
    --     AutoRoadwork = Value

    --     while task.wait() and AutoRoadwork do
    --         if plr.Backpack:FindFirstChild("Roadwork") or plr.Character:FindFirstChild("Roadwork") then
    --             pcall(function()
    --                 plr.Backpack:FindFirstChild("Roadwork").Parent = plr.Character
    --             end)
    --             task.wait()
    --             plr.Character:FindFirstChild("Roadwork"):Activate()
    --             task.wait()
                
    --             for i,v in pairs(game:GetService("Workspace").Roadwork:GetChildren()) do
    --                 repeat
    --                     game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
    --                     task.wait()
    --                     firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart,v,0)
    --                     task.wait()
    --                     firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart,v,1)
    --                 until v.Marker.Enabled == false
    --             end
    --         elseif plr.Backpack:FindFirstChild("Roadwork") == nil and plr.Character:FindFirstChild("Roadwork") == nil then
    --             game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = RW.Head.CFrame
    --             task.wait()
    --             fireproximityprompt(RW.Head.ProximityPrompt)
    --             task.wait()
    --         end
    --     end
    -- end)
    
    
    
    misc:Toggle("Auto Reroll",false,function(Value)
        AutoReroll = Value
        
        while task.wait() and AutoReroll do
          if DesiredRarity ~= nil then
              local Clan = tostring(game:GetService("Players").LocalPlayer.PlayerGui.MainGui.StatusFrame.ClanName.Text:split(" ")[2])
              if Clan ~= nil then
                  if IsWantedClan(Clan) then
                      return print(Clan,"Is",DesiredRarity)
                  else
                      game:GetService("ReplicatedStorage"):WaitForChild("Reroll"):FireServer("BP")
                      task.wait(0.5)
                  end
              end
          end
        end
    end)
    
    misc:Dropdown("Desired Rarity",{"Godly+","Mythical+","Legendary+","Rare+","Common+","Uncommon+",""},function(Value)
        DesiredRarity = Value
    end)
    
    local Collectibles = {
        AncientBooks = true,
        SamuraiBooks = true,
        EasterEggs = true,
    }
    
    misc:Toggle("Farm Collectibles",false,function(Value)
        FarmCollect = Value
        local function FarmCollectibles()
           if Collectibles["AncientBooks"] then
              local total = game:GetService("ReplicatedStorage").AncientBooks:GetChildren()
              
              for i,v in pairs(total) do
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
                 task.wait(0.1)
              end
           end
           
           if Collectibles["SamuraiBooks"] then
               local total = game:GetService("ReplicatedStorage").AncientSamuraiBooks:GetChildren()
              
              for i,v in pairs(total) do
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
                 task.wait(0.1)
              end
           end
           
           if Collectibles["EasterEggs"] then
               local total = game:GetService("ReplicatedStorage").EasterEggs:GetChildren()
              
              for i,v in pairs(total) do
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
                 task.wait(0.1)
              end
           end
        end
        
        while FarmCollect and task.wait() do
            FarmCollectibles()
        end
    end)
    
    misc:Dropdown("Farm Collectible Option",{"AncientBooks","SamuraiBooks","EasterEggs","Books","Egg","All",""},function(Value)
        if Value == "All" then
           Collectibles = {
                AncientBooks = true,
                SamuraiBooks = true,
                EasterEggs = true,
            } 
        elseif Value == "Books" then
            Collectibles = {
                AncientBooks = true,
                SamuraiBooks = true,
                EasterEggs = false,
            }
        elseif Value == "Egg" then
            Collectibles = {
                AncientBooks = false,
                SamuraiBooks = false,
                EasterEggs = true,
            }
        else
            Collectibles = {
                AncientBooks = false,
                SamuraiBooks = false,
                EasterEggs = false,
            }
            
            Collectibles[Value] = true
        end
    end)
    
    misc:Dropdown("Trainer",Trainer,function(x)
        local Trainer
        for i,v in pairs(game:GetService("Workspace").Trainers:GetChildren()) do
            if v.Name == x then
                Trainer = v
            end
        end
        
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Trainer.Head.CFrame
    end)
    
    misc:Dropdown("SpecialTrainer",SpecialTrainer,function(x)
        local SpecialTrainer
        for i,v in pairs(game:GetService("Workspace").SpecialTrainers:GetChildren()) do
            if v.Name == x then
                SpecialTrainer = v
            end
        end
        
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = SpecialTrainer.Head.CFrame
    end)
    
    misc:Dropdown("Items",Items,function(x)
        for i,v in pairs(Items) do
            if v.Name == x then
               CurrentItem = v
            end
        end
    end)
    
    misc:Button("Teleport To Item",function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CurrentItem.Head.CFrame
    end)
    
    misc:Toggle("Auto Buy Item",false,function(Value)
        ABItems = Value
        
        while task.wait() and ABItems do
            pcall(function()
                fireproximityprompt(CurrentItem.Head.ProximityPrompt)
            end)
        end
    end)
    
    misc:Toggle("Anchored",false,function(Value)
        plr.Character.HumanoidRootPart.Anchored = Value
    end)
    
    misc:Toggle("Anti Staff",false,function(Value)
        AntiStaff = Value
        
        if AntiStaff then
            for i,v in pairs(game.Players:GetPlayers()) do
                IsStaff(v)
            end
        end
    end)
    
    misc:Textbox("Deposit",function(txt)
        if tonumber(txt) then
            local args = {
                [1] = "Deposit",
                [2] = tonumber(txt)
            }
            
            game:GetService("ReplicatedStorage"):WaitForChild("Bank"):InvokeServer(unpack(args))
        end
    end)
    
    misc:Textbox("Withdraw",function(txt)
        if tonumber(txt) then
             local args = {
                [1] = "Withdraw",
                [2] = tonumber(txt)
            }
            
            game:GetService("ReplicatedStorage"):WaitForChild("Bank"):InvokeServer(unpack(args))
        end
    end)
    
    misc:Button("Low GFX",function()
        pcall(function()
            for i,v in pairs(game:GetService("Workspace").Map:GetDescendants()) do
                pcall(function()
                    if not v:IsA("Model") and not v:IsA("SpotLight") and not v:IsA("Weld") and not v:IsA("Folder") and not v:IsA("SurfaceLight") and not v:IsA("SpecialMesh") and not v:IsA("Attachment") and not v:IsA("Beam") then
                        if v:IsA("Texture") or v:IsA("Decal") then
                            v:Destroy()
                        elseif v.Transparency ~= nil and v.Material ~= nil then
                            v.Transparency = 0
                            v.Material = Enum.Material.Plastic
                        end
                    elseif v:IsA("SpotLight") or v:IsA("SurfaceLight") or v:IsA("SpecialMesh") or v:IsA("Beam") then
                        v:Destroy()
                    end
                end)
            end
            
            pcall(function()
                game:GetService("Lighting").SunRays:Destroy()
                game:GetService("Lighting").Blur:Destroy()
                game:GetService("Lighting").Bloom:Destroy()
                game:GetService("Lighting").ColorCorrection:Destroy()
                game:GetService("Lighting")["Afternoon Sky"]:Destroy()
                game:GetService("Lighting").DepthOfField:Destroy()
                game:GetService("Lighting")["low_color_correction"]:Destroy()
                game:GetService("Lighting").Map:Destroy()
                game:GetService("Lighting").Atmosphere:Destroy()
            end)
            wait(1)
        end)
    end)
    
    misc:Button("Respawn",function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(Vector3.new(0,-499,0))
    end)
    
    misc:Button("Rejoin",function()
        pcall(function()
            if #game:GetService("Players"):GetPlayers() <= 1 then
                Plr:Kick("\nRejoining...")
                wait()
                game:GetService("TeleportService"):Teleport(game.PlaceId, Plr)
            else
                game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId, game.JobId, Plr)
            end
        end)
    end)
    
    misc:Button("Serverhop to Lowest Server",function(Value)
        local Http = game:GetService("HttpService")
        local TPS = game:GetService("TeleportService")
        local Api = "https://games.roblox.com/v1/games/"

        local _place = game.PlaceId
        local _servers = Api.._place.."/servers/Public?sortOrder=Asc&limit=100"
        function ListServers(cursor)
        local Raw = game:HttpGet(_servers .. ((cursor and "&cursor="..cursor) or ""))
        return Http:JSONDecode(Raw)
        end

        local Server, Next; repeat
        local Servers = ListServers(Next)
        Server = Servers.data[1]
        Next = Servers.nextPageCursor
        until Server

        TPS:TeleportToPlaceInstance(_place,Server.id,game.Players.LocalPlayer)
    end)
    
    
    return win
end

local function MO(name)
	local LibraryColor = Color3.fromRGB(73, 135, 74)
	local win = library:Window(name .. " (touch grass)", LibraryColor)
	win.PromptDiscord("y7H2qGmNKd")

	local main = win:Tab("Training")
	local notify = win:Tab("Notify")
	local autocook = win:Tab("Auto Cook")
	local misc = win:Tab("Misc")
	local risky = win:Tab("Risky")
	risky:Label("-- ANYTHING IN THIS TAB WAS SUGGESTED BY SOMEONE --")
	risky:Label("-- AND IS CONSIDERED RISKY USE AT YOUR OWN RISK --")

	local panicdelay = 0.5
	local panicdashdelay = 3
	local CurrentRegening = false
	local panicangle = math.random(35, 90)
	local VIM = game:GetService("VirtualInputManager")
	local panicdashdebounce = false
	local ministam = 20
	local regenstamina
	local regentoamt = 100
	local autopanic
	local UIS = game:GetService("UserInputService")
	local Mouse = game.Players.LocalPlayer:GetMouse()
	local holdclick
	local CurrentGanker = nil
	local currentlyviewing = nil
	local macroruin
	local OPsData = nil
	pcall(function()
		OPsData = readfile("/m1keincorporated/MOoppositions.json")
	end)
	local OPSNotifier = false
	local SleepNotifier
	local alreadynotifieduser = nil
	local macroruindebounce = false
	local NoFoodNotify
	local LogOnNoFood
	local webhookUrl
	local camera = workspace.CurrentCamera
	local rs = game:GetService("RunService")
	local ESP
	local wanted = { "Owner", "Associates.", "Mod", "Trial Mod", "sircroc!" }
	local WhitelistedStats = {
		"Durability",
		"UpperBodyMuscle",
		"RunningSpeed",
		"Fat",
		"StrikingPower",
		"StrikingSpeed",
		"LowerBodyMuscle",
		"Height",
		"Stamina",
	}
	local oldVolume = nil
	local CurrentlyPlaying = {}
	local copnotifier
	local staffnotifier
	local disableOnStaff
	local flownotifier = false
	local flowconnection = nil
	local sfnotifier = false
	local sfconnection = nil
	local acknowledged = false
	local acook = false
	local SelectedFood = ""
	local abn
	local TotalServings = 1
	local absbox
	local autotrain
	local traintype
	local trainspeed
	local isrunning = false
	local startPunching = false
	local currentcombo
	local m2already = false
	local strikepower
	local durability
	local DuraTool = ""
	local AutoWalkAfterPushedBack
	local ft
	local st
	local taketurns = false
	local durainprogress = false
	local stopAtHP = 20
	local SkillXP = false
	local AutoStop = false
	local LogOnNotEnoughMoney = false
	local WalkBackWhenFar = false
	local FatigueToStop = 65
	local LogOnFatigued = false
	local autosleepLog, autosleepRes, autosleepwalk = false, false, false
	local AutoSleepPaths = {
		["Noi"] = {
			["IsInsideDist"] = 90,

			["Sequence"] = {
				CFrame.new(
					-563.773621,
					47.9251785,
					-239.531036,
					-0.023773279,
					2.32641151e-09,
					-0.999717355,
					-4.37537873e-09,
					1,
					2.43111575e-09,
					0.999717355,
					4.43193793e-09,
					-0.023773279
				), -- NOI INSIDE
				CFrame.new(
					-491.393372,
					47.1251755,
					-334.181793,
					0.707333982,
					5.5018571e-08,
					0.706879497,
					2.09656843e-08,
					1,
					-9.8812194e-08,
					-0.706879497,
					8.47134345e-08,
					0.707333982
				), --midpoint1
				CFrame.new(
					-637.209961,
					47.125164,
					-446.7258,
					0.0272168536,
					7.69836674e-08,
					0.999629557,
					6.81569645e-09,
					1,
					-7.71977682e-08,
					-0.999629557,
					8.91425156e-09,
					0.0272168536
				), --HospitalLoaded
			},
		},

		["Karate"] = {
			["IsInsideDist"] = 90,

			["Sequence"] = {
				CFrame.new(
					-664.119202,
					47.6938782,
					-611.250977,
					-0.00150513474,
					-8.3909228e-08,
					0.999998868,
					1.02445374e-09,
					1,
					8.39108623e-08,
					-0.999998868,
					1.15074972e-09,
					-0.00150513474
				), -- karate inside
				CFrame.new(
					-725.983948,
					47.7645721,
					-574.489563,
					-0.999990106,
					-5.69174006e-08,
					0.00445292145,
					-5.67966332e-08,
					1,
					2.7247351e-08,
					-0.00445292145,
					2.69941687e-08,
					-0.999990106
				), --midpoint1
				CFrame.new(
					-726.560303,
					46.7939758,
					-458.533325,
					-0.896284282,
					-4.07478096e-09,
					0.443480015,
					-3.75909188e-08,
					1,
					-6.6783997e-08,
					-0.443480015,
					-7.65282664e-08,
					-0.896284282
				), --HospitalLoaded
			},
		},
	}
	local trainingsTodo = {}
	local sleepanims = {
		"rbxassetid://5110906576",
		"rbxassetid://4959794246",
		"rbxassetid://5110983609",
		"rbxassetid://4959795216",
		"rbxassetid://4959793113",
		"rbxassetid://5110953707",
		"rbxassetid://5110982040",
		"rbxassetid://5110919996",
	}
	local trainingtoggles = {}
	local disabledFeaturesRunning = false
	local ESPDistance = 10000
	local strikespeed = false
	local rhythmcheckdebounce = false
	local autoeat = false
	local stopAEinCombat = false
	local FillUp
	local EatAt
	local autosupplement = false
	local selectedsupplement = nil
	local machines = false
	local treadselect = nil
	local machinetype = nil
	local CurrentRegening = false
	local ping = "@everyone"
	local statcheck = false
	local RhythmToggle = false
	local RunToPercent = 50
	local PunchStartPercent = 55
	local PunchEndPercent = 20
	local Roadwork = false
	local RWCanSprint = false
	local CPRangeTilNext = 7
	local PointRangeTilNext = 6
	local LastMachine = nil
	local spuseM2 = false
	local ssuseM2 = false
	local autostarve = false
	local staminabelowpercent = 20
	local ASisrunning = false
	local PFS = game:GetService("PathfindingService")
	local HRP = game.Players.LocalPlayer.Character:WaitForChild("HumanoidRootPart")
	local pathStatus = Enum.PathStatus
	local player = game.Players.LocalPlayer
	local autobuyitem = false
	local itemselected = nil
	local StopInCombat = false
	local StopKnocked = false
	local autosprintcombat = false
	local holdingW = false
	local began, ended = nil, nil
	shared.currentPoint = nil
	local MOfoods = {
		"Donut",
		"Coffee",
		"Bagel",
		"EZ Taco",
		"Omelette",
		"Hotdog",
		"Pancakes",
		"Tofu Beef Soup",
		"Pie",
		"Tokito Sake",
		"Hamburger",
		"Chicken Fries",
		"Ramen",
		"Chicken",
		"Curry",
		"Steak",
		"Steak Fried Rice",
		"Braised Potatoes",
		"Sunny side up egg",
		"Onigiri",
		"Marinade Lobster",
	}
	local recipes = {
		["Steak"] = {
			["Seasoning"] = 1,
			["Raw Beef"] = 1,
		},
		["Chicken"] = {
			["Seasoning"] = 1,
			["Raw Chicken"] = 1,
		},
		["Sunny Side up Egg"] = {
			["Egg"] = 1,
		},
		["Onigri"] = {
			["Rice"] = 2,
			["Seasoning"] = 1,
			["Seaweed"] = 1,
			["Soy Sauce"] = 1,
		},
		["Omelette"] = {
			["Egg"] = 2,
			["Seasoning"] = 1,
		},
		["Braised Potato"] = {
			["Potato"] = 2,
			["Soy Sauce"] = 1,
			["Onion"] = 1,
			["Seasoning"] = 1,
		},
		["Steak Fried Rice"] = {
			["Rice"] = 1,
			["Egg"] = 2,
			["Onion"] = 1,
			["Carrot"] = 1,
			["Raw Beef"] = 1,
			["Tomato"] = 1,
			["Seasoning"] = 1,
			["Spice"] = 1,
		},
		["Curry"] = {
			["Spice"] = 1,
			["Potato"] = 1,
			["Carrot"] = 1,
			["Raw Beef"] = 1,
			["Rice"] = 2,
			["Onion"] = 1,
		},
		["Marinade Lobster"] = {
			["Seasoning"] = 1,
			["Raw Lobster"] = 1,
			["Spice"] = 1,
		},
	}

	local function CheckForFood()
		if SelectedFood == nil then
			return false
		end
		for i, v in pairs(recipes[SelectedFood]) do
			if game.Players.LocalPlayer.Backpack:FindFirstChild(i) == nil then
				return false
			end
			if game.Players.LocalPlayer.Backpack:FindFirstChild(i).Quantity.Value < v then
				return false
			end
		end
		return true
	end

	local function GetItemTable()
		local tbl = {}

		for i, v in pairs(workspace:GetChildren()) do
			if v:FindFirstChild("Shopnoid") then
				local foodname = v.Name:split(":")[1]
				if table.find(MOfoods, foodname) then
					table.insert(tbl, v)
				end
			end
		end

		return tbl
	end

	local ItemTable = GetItemTable()

	local function round(n)
		return math.floor(n) * 1
	end

	local function GetPan()
		local bestdistance, pan = nil, nil
		local paninstances = {
			workspace,
			game:GetService("Workspace").Apartment2,
			game:GetService("Workspace").HOMRA,
			game:GetService("Workspace").Apartment4,
			game:GetService("Workspace").Apartment1,
			game:GetService("Workspace")["Street House"],
			game:GetService("Workspace")["Organisation Building"],
		}

		for _, instance in pairs(paninstances) do
			for i, v in pairs(instance:GetChildren()) do
				if v.Name == "Stove" or v:FindFirstChild("Stove") then
					if v:FindFirstChild("Stove") then
						v = v:FindFirstChild("Stove")
					end

					local distance = (
						v.PanModel.FoodP.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position
					).Magnitude

					if bestdistance == nil and distance <= 5 then
						bestdistance = distance
						pan = v.PanModel
					elseif bestdistance ~= nil and distance <= 5 then
						if bestdistance > distance and distance <= 5 then
							bestdistance = distance
							pan = v.PanModel
						end
					end
				end
			end
		end
		return pan
	end

	local function playsound(id)
		local sound = Instance.new("Sound", game.CoreGui)
		sound.SoundId = "rbxassetid://" .. id
		sound.Volume = 10
		sound.Looped = true
		sound:Play()
		return sound
	end

	local function createPath(point)
		local currentPath = PFS:FindPathAsync(HRP.Position, point)
		local pathExists = false

		if currentPath.Status == pathStatus.Success then
			pathExists = true

			spawn(function()
				while pathExists and task.wait() and Roadwork and shared.currentPoint ~= nil do
					player.Character.Humanoid.WalkToPoint = shared.currentPoint
				end
			end)

			for i, v in pairs(currentPath:GetWaypoints()) do
				if Roadwork == false then
					shared.currentPoint = nil
					break
				end
				repeat
					task.wait()
					shared.currentPoint = v.Position
					print((HRP.Position - v.Position).Magnitude)
				until (HRP.Position - v.Position).Magnitude < CPRangeTilNext or Roadwork == false
			end
		elseif currentPath.Status ~= pathStatus.Success or shared.currentPoint == nil then
			pathExists = false
		end
	end

	local function WalkTo(point)
		pcall(function()
			local currentPath = PFS:FindPathAsync(HRP.Position, point)
			local pathExists = false

			if currentPath.Status == pathStatus.Success then
				pathExists = true

				spawn(function()
					while pathExists and task.wait() and shared.currentPoint ~= nil do
						player.Character.Humanoid.WalkToPoint = shared.currentPoint
					end
				end)

				for i, v in pairs(currentPath:GetWaypoints()) do
					repeat
						task.wait()
						shared.currentPoint = v.Position
					until (HRP.Position - v.Position).Magnitude < 5
				end
			elseif currentPath.Status ~= pathStatus.Success or shared.currentPoint == nil then
				pathExists = false
			end
		end)
	end

	local function Callback(answer)
		acknowledged = true
		UserSettings():GetService("UserGameSettings").MasterVolume = oldVolume
		oldVolume = nil
		for i, v in pairs(CurrentlyPlaying) do
			v:Stop()
			game.Debris:AddItem(v, 0.01)
		end
		CurrentlyPlaying = {}
		task.delay(1, function()
			acknowledged = false
		end)

		if answer == "OMG FLOW" and game:GetService("Workspace"):FindFirstChild("XinFolder") then
			local QuestMarker = Instance.new("BillboardGui")
			local ImageLabel = Instance.new("ImageLabel")

			QuestMarker.Name = "ESP"
			QuestMarker.Parent = game:GetService("Workspace").XinFolder:FindFirstChildOfClass("Model").HumanoidRootPart
			QuestMarker.AlwaysOnTop = true
			QuestMarker.Size = UDim2.new(0, 50, 0, 50)

			ImageLabel.Parent = QuestMarker
			ImageLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			ImageLabel.BackgroundTransparency = 1.000
			ImageLabel.Size = UDim2.new(1, 0, 1, 0)
			ImageLabel.Image = "rbxassetid://2334137638"
			ImageLabel.ImageColor3 = Color3.fromRGB(255, 85, 0)
		elseif answer == "LIGHTWORK" and game:GetService("Workspace"):FindFirstChild("AokiFolder") then
			local QuestMarker = Instance.new("BillboardGui")
			local ImageLabel = Instance.new("ImageLabel")

			QuestMarker.Name = "ESP"
			QuestMarker.Parent = game:GetService("Workspace").AokiFolder:FindFirstChildOfClass("Model").HumanoidRootPart
			QuestMarker.AlwaysOnTop = true
			QuestMarker.Size = UDim2.new(0, 50, 0, 50)

			ImageLabel.Parent = QuestMarker
			ImageLabel.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
			ImageLabel.BackgroundTransparency = 1.000
			ImageLabel.Size = UDim2.new(1, 0, 1, 0)
			ImageLabel.Image = "rbxassetid://2334137638"
			ImageLabel.ImageColor3 = Color3.fromRGB(255, 85, 0)
		end
	end
	local Bindable = Instance.new("BindableFunction")
	Bindable.OnInvoke = Callback

	local function GetSkill()
		local lol = game:GetService("Players").LocalPlayer.PlayerGui.BackpackGUI.Frame

		for i, v in pairs(lol:GetChildren()) do
			if v.ClassName == "ImageLabel" then
				print("ing")
				if tostring(v.ImageColor3) == "0.419608, 0.32549, 0.137255" then
					if game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool") then
						if game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool"):FindFirstChild("Skill") then
							return game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool"), v
						end
					end
				elseif tostring(v.ImageColor3) == "0.211765, 0.211765, 0.211765" then
					if game.Players.LocalPlayer.Backpack:FindFirstChild(v.ToolName.Text) then
						if
							game.Players.LocalPlayer.Backpack:FindFirstChild(v.ToolName.Text):FindFirstChild("Skill")
						then
							return game.Players.LocalPlayer.Backpack:FindFirstChild(v.ToolName.Text), v
						end
					end
				end
			end
		end

		return nil, nil
	end

	local function disableAllTraining()
		for i, v in pairs(trainingtoggles) do
			if v:GetState() == true then
				table.insert(trainingsTodo, v)
				v:SetState(false)
			end
		end
	end

	local function Notifier(v)
		if v ~= nil then
			if v:IsInGroup(15987464) and copnotifier or v:IsInGroup(7677568) and copnotifier then
				if oldVolume == nil then
					oldVolume = UserSettings():GetService("UserGameSettings").MasterVolume
				end
				local level = 10 / 10
				UserSettings():GetService("UserGameSettings").MasterVolume = level
				CurrentlyPlaying[#CurrentlyPlaying + 1] = playsound(9117261160)

				game.StarterGui:SetCore("SendNotification", {
					Title = "WEEE WOOO (Cop)",
					Text = v.Name,
					Duration = math.huge,
					Button1 = "STOPP",
					Callback = Bindable,
				})
			end

			if table.find(wanted, v:GetRoleInGroup(4800422)) and staffnotifier then
				if disableOnStaff then
					disableAllTraining()
				end

				if oldVolume == nil then
					oldVolume = UserSettings():GetService("UserGameSettings").MasterVolume
				end
				local level = 10 / 10
				UserSettings():GetService("UserGameSettings").MasterVolume = level
				CurrentlyPlaying[#CurrentlyPlaying + 1] = playsound(9114284125)

				game.StarterGui:SetCore("SendNotification", {
					Title = "THE OPS! (STAFF)",
					Text = v.Name,
					Duration = math.huge,
					Button1 = "smhh",
					Callback = Bindable,
				})
				if oldVolume == nil then
					oldVolume = UserSettings():GetService("UserGameSettings").MasterVolume
				end
				local level = 10 / 10
				UserSettings():GetService("UserGameSettings").MasterVolume = level
				CurrentlyPlaying[#CurrentlyPlaying + 1] = playsound(9114284125)

				game.StarterGui:SetCore("SendNotification", {
					Title = "THE OPS! (STAFF)",
					Text = v.Name,
					Duration = math.huge,
					Button1 = "smhh",
					Callback = Bindable,
				})
			end
		else
			if game:GetService("Workspace"):FindFirstChild("XinFolder") and flownotifier then
				if oldVolume == nil then
					oldVolume = UserSettings():GetService("UserGameSettings").MasterVolume
				end
				local level = 10 / 10
				UserSettings():GetService("UserGameSettings").MasterVolume = level
				CurrentlyPlaying[#CurrentlyPlaying + 1] = playsound(9125673453)

				game.StarterGui:SetCore("SendNotification", {
					Title = "Flow NPC SPAWNED",
					Text = "LUKE XIN",
					Duration = math.huge,
					Button1 = "OMG FLOW",
					Callback = Bindable,
				})
			end

			if game:GetService("Workspace"):FindFirstChild("AokiFolder") and sfnotifier then
				if oldVolume == nil then
					oldVolume = UserSettings():GetService("UserGameSettings").MasterVolume
				end
				local level = 10 / 10
				UserSettings():GetService("UserGameSettings").MasterVolume = level
				CurrentlyPlaying[#CurrentlyPlaying + 1] = playsound(9125673453)

				game.StarterGui:SetCore("SendNotification", {
					Title = "SF NPC SPAWNED",
					Text = "STREET FIGHTER",
					Duration = math.huge,
					Button1 = "LIGHTWORK",
					Callback = Bindable,
				})
			end
		end
	end

	game:GetService("Workspace").Live.DescendantAdded:Connect(function(child)
		if child.Name == "Attacking" and child.Parent ~= game.Players.LocalPlayer.Character and macroruin then
			if
				(child.Parent.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
				<= 5
			then
				CurrentGanker = plrList:FindFirstChild(child.Parent.Name).User.Txt.Text
					.. " ["
					.. child.Parent.Name
					.. "]"
			end
		end
	end)

	if getgenv().spectateList == nil then
		getgenv().spectateList = true

		task.spawn(function()
			local gankedLists = {}
                        local plrList = game:GetService("Players").LocalPlayer.PlayerGui.PlayerList.Main.SF.Holder

			while spectateList and task.wait() do
				pcall(function()
					if game.Players.LocalPlayer.PlayerGui:FindFirstChild("PlayerList") ~= nil then
						plrList = game:GetService("Players").LocalPlayer.PlayerGui.PlayerList.Main.SF.Holder

						if gankedLists[plrList] ~= true then
							gankedLists[plrList] = true
							repeat
								task.wait()
							until game:IsLoaded() and game.Players.LocalPlayer.Character ~= nil
							repeat
								task.wait()
							until game.Players.LocalPlayer.Character:FindFirstChild("HumanoidRootPart")

							for i, v in pairs(plrList:GetChildren()) do
								if v:IsA("ImageButton") and v.Name ~= game.Players.LocalPlayer.Name then
									v.User.Activated:Connect(function()
										if currentlyviewing ~= nil then
											if currentlyviewing:FindFirstChild("Player") ~= nil then
												if currentlyviewing == v then
													currentlyviewing.Player.Title.TextColor3 = Color3.fromRGB(255, 255, 255)
													workspace.CurrentCamera.CameraSubject =
														game.Players.LocalPlayer.Character:WaitForChild("Humanoid")
													currentlyviewing = nil
													return
												end
												currentlyviewing.Player.Title.TextColor3 = Color3.fromRGB(255, 255, 255)
											elseif currentlyviewing:FindFirstChild("Player") == nil then
												workspace.CurrentCamera.CameraSubject =
													game.Players.LocalPlayer.Character:WaitForChild("Humanoid")
												currentlyviewing = nil
											end
										end

										local viewplr = workspace.Live:FindFirstChild(v.Name)
										if viewplr == nil then
											return
										end
										if viewplr:FindFirstChild("Humanoid") ~= nil then
											workspace.CurrentCamera.CameraSubject = viewplr:WaitForChild("Humanoid")
											v.Player.Title.TextColor3 = LibraryColor
											currentlyviewing = v
											task.spawn(function()
												while (currentlyviewing == v) and task.wait(0.5) do
													local viewplr = workspace.Live:FindFirstChild(v.Name)
													if viewplr == nil then
														workspace.CurrentCamera.CameraSubject =
															game.Players.LocalPlayer.Character:WaitForChild("Humanoid")
														currentlyviewing = nil
														break
													end
												end
											end)
										end
									end)
								end
							end

							plrList.ChildAdded:Connect(function(v)
								if v:IsA("ImageButton") then
									v.User.Activated:Connect(function()
										if currentlyviewing ~= nil then
											if currentlyviewing:FindFirstChild("Player") ~= nil then
												if currentlyviewing == v then
													currentlyviewing.Player.Title.TextColor3 = Color3.fromRGB(255, 255, 255)
													workspace.CurrentCamera.CameraSubject =
														game.Players.LocalPlayer.Character:WaitForChild("Humanoid")
													currentlyviewing = nil
													return
												end
												currentlyviewing.Player.Title.TextColor3 = Color3.fromRGB(255, 255, 255)
											elseif currentlyviewing:FindFirstChild("Player") == nil then
												workspace.CurrentCamera.CameraSubject =
													game.Players.LocalPlayer.Character:WaitForChild("Humanoid")
												currentlyviewing = nil
											end
										end

										local viewplr = workspace.Live:FindFirstChild(v.Name)
										if viewplr == nil then
											return
										end
										if viewplr:FindFirstChild("Humanoid") ~= nil then
											workspace.CurrentCamera.CameraSubject = viewplr:WaitForChild("Humanoid")
											v.Player.Title.TextColor3 = LibraryColor
											currentlyviewing = v
											task.spawn(function()
												while (currentlyviewing == v) and task.wait(0.5) do
													local viewplr = workspace.Live:FindFirstChild(v.Name)
													if viewplr == nil then
														workspace.CurrentCamera.CameraSubject =
															game.Players.LocalPlayer.Character:WaitForChild("Humanoid")
														currentlyviewing = nil
														break
													end
												end
											end)
										end
									end)
								end
							end)
						end
					end
				end)
			end
		end)
	end

	function round(p8, p9)
		if not p9 then
			return math.floor(p8 + 0.5)
		end
		local v15 = math.floor(p8 * 10 ^ p9 + 0.5) / 10 ^ p9
		local v16 = string.len(v15)
		local v17 = string.sub(v15, v16, v16)
		local v18 = v16 - 1
		if string.sub(v15, v18, v18) == "." then
			v15 = v15 .. "0"
		end
		return v15
	end

    if typeof(getgc) ~= "nil" then
        local StatViewerLabels = nil
        local SC = win:Tab("Stat Check")

        shared.StatUpdate = function(v)
            if statcheck ~= true then
                return
            end
            local StatTable = v

            if StatViewerLabels == nil then
                StatViewerLabels = {}

                for i, v in pairs(StatTable) do
                    if table.find(WhitelistedStats, i) ~= nil then
                        if typeof(v) == "table" then
                            StatViewerLabels[i] = SC:Label(i .. " - " .. round(v[1], 3))
                        else
                            StatViewerLabels[i] = SC:Label(i .. " - " .. round(v, 3))
                        end
                    end
                end
            else
                for i, v in pairs(StatTable) do
                    if table.find(WhitelistedStats, i) ~= nil then
                        if typeof(v) == "table" then
                            StatViewerLabels[i]:SetText(i .. " - " .. round(v[1], 3))
                        else
                            StatViewerLabels[i]:SetText(i .. " - " .. round(v, 3))
                        end
                    end
                end
            end
        end

        local function StatTable()
            local ls = getsenv(game.Players.LocalPlayer.Backpack.LocalS)

            for i, v in pairs(ls) do
                if typeof(v) == "function" then
                    for i, v in pairs(debug.getupvalues(v)) do
                        if typeof(v) == "table" then
                            if v["Height"] ~= nil then
                                return v
                            end
                        end
                    end
                end
            end
        end

        SC:Toggle("Auto Stat Check", false, function(Value)
            statcheck = Value

            if statcheck then
                shared.StatUpdate(StatTable())
            end
        end)
        local RefreshConstant

        SC:Toggle("Refresh Constantly", false, function(Value)
            RefreshConstant = Value

            while RefreshConstant and task.wait(0.05) do
                shared.StatUpdate(StatTable())
            end
        end)

        if shared.StatConfigured == nil then
            task.spawn(function()
                shared.StatConfigured = true

                local updateDebounce = false
                game:GetService("ReplicatedStorage").Events.UpdateStats.OnClientEvent:Connect(function(x)
                    if updateDebounce or statcheck ~= true then
                        return
                    end

                    if table.find(WhitelistedStats, x) then
                        updateDebounce = true
                        pcall(function()
                            shared.StatUpdate(StatTable())
                        end)
                        task.wait(0.1)
                        updateDebounce = false
                    end
                end)
            end)
        end
    end

	local function GetBed()
		local bestdistance, bed = nil, nil
		local apartmentBed = false

		for _, v in pairs(game:GetService("Workspace"):GetChildren()) do
			if apartmentBed then
				break
			end
			if v.Name:find("Bed") then
				if not v:FindFirstChild("OccupiedBy") then
					local distance = (v.Matress.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude

					if bestdistance == nil then
						bestdistance = distance
						bed = v
					elseif bestdistance ~= nil then
						if bestdistance > distance then
							bestdistance = distance
							bed = v
						end
					end
				end
			elseif v.Name:find("Apartment") then
				for _, v in pairs(v:GetChildren()) do
					if v.Name == "Bed" then
						local distance = (
							v.Matress.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position
						).Magnitude
						local Owner = v.Owner.Value

						if
							Owner == tostring(game.Players.LocalPlayer.UserId)
							and distance <= v.ClickDetector.MaxActivationDistance
						then
							bed = v
							apartmentBed = true
							break
						end
					end
				end
			end
		end

		return bed
	end

	local function GetMachineType(v)
		if v:FindFirstChild("Screen") then
			return "Treadmill"
		elseif v:FindFirstChildOfClass("MeshPart") and v:FindFirstChild("Barbell") then
			return "Bench"
		elseif not v:FindFirstChildOfClass("MeshPart") and v:FindFirstChild("Barbell") then
			return "Squat"
		else
			return "nil"
		end
	end

	local function ClosestMachine()
		local bestdistance, machine = nil, nil
		local machineinstances =
			{ workspace.Naniwa, workspace["Organisation Building"], workspace, workspace:GetChildren()[1436] }

		for _, instance in pairs(machineinstances) do
			for i, v in pairs(instance:GetChildren()) do
				if GetMachineType(v) == machinetype and v.Name == "Machine" then
					if v:FindFirstChild("Machine") then
						v = v:FindFirstChild("Machine")
					end
					local distance = (v.Base.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
					local MaxActivationDist = v.ClickDetector.MaxActivationDistance

					if distance <= MaxActivationDist then
						if bestdistance == nil and machine == nil then
							bestdistance = distance
							machine = v
						elseif bestdistance > distance then
							bestdistance = distance
							machine = v
						end
					end
				end
			end
		end

		return machine
	end

	local function GetSSBuy()
		local bestdistance, ss = nil, nil
		local ssinstances = {
			workspace,
			workspace.kUREtRAINER,
		}

		for _, instance in pairs(ssinstances) do
			for i, v in pairs(instance:GetChildren()) do
				if v.Name:find("Strike Speed Training") or v:FindFirstChild("Strike Speed Training: $180") then
					if v:FindFirstChild("Strike Speed Training: $180") then
						v = v:FindFirstChild("Strike Speed Training: $180")
					end
					local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Head.Position).Magnitude
					local MaxActivationDist = v.ClickDetector.MaxActivationDistance

					if distance <= MaxActivationDist then
						if bestdistance == nil and ss == nil then
							bestdistance = distance
							ss = v
						elseif bestdistance > distance then
							bestdistance = distance
							ss = v
						end
					end
				end
			end
		end

		return ss
	end

	local function ChargeRhythm(combatTool)
		if not RhythmToggle then
			return
		end

		if
			game.Players.LocalPlayer.Character.HumanoidRootPart.RhythmUI.Enabled == false
			and combatTool.Parent == game.Players.LocalPlayer.Character
		then
			VIM:SendKeyEvent(true, "R", false, game)
			task.wait(0.1)
		elseif
			game.Players.LocalPlayer.Character.HumanoidRootPart.RhythmUI.Enabled == true
			and combatTool.Parent == game.Players.LocalPlayer.Character
			and game.Players.LocalPlayer.Character.Rhythm.Value ~= 100
			and not rhythmcheckdebounce
		then
			rhythmcheckdebounce = true
			task.spawn(function()
				local oldRhythm = game.Players.LocalPlayer.Character.Rhythm.Value
				task.wait(0.1)
				if game.Players.LocalPlayer.Character.Rhythm.Value < oldRhythm then
					VIM:SendKeyEvent(true, "R", false, game)
					task.wait(0.1)
					oldRhythm = game.Players.LocalPlayer.Character.Rhythm.Value
					repeat
						task.wait()
					until game.Players.LocalPlayer.Character.Rhythm.Value == 100
						or game.Players.LocalPlayer.Character.Rhythm.Value < oldRhythm
						or combatTool.Parent ~= game.Players.LocalPlayer.Character
				else
					repeat
						task.wait()
					until game.Players.LocalPlayer.Character.Rhythm.Value == 100
						or game.Players.LocalPlayer.Character.Rhythm.Value < oldRhythm
						or combatTool.Parent ~= game.Players.LocalPlayer.Character
				end
				rhythmcheckdebounce = false
			end)
		end
	end

	local function IsSleeping()
		for i, v in pairs(game.Players.LocalPlayer.Character.Humanoid:GetPlayingAnimationTracks()) do
			if table.find(sleepanims, v.Animation.AnimationId) then
				return true
			end
		end
		return false
	end

	local function WalkTo(point)
		local currentPath = PFS:FindPathAsync(HRP.Position, point)
		local pathExists = false

		if currentPath.Status == pathStatus.Success then
			pathExists = true

			spawn(function()
				while pathExists and task.wait() and shared.currentPoint ~= nil do
					player.Character.Humanoid.WalkToPoint = shared.currentPoint
				end
			end)

			for i, v in pairs(currentPath:GetWaypoints()) do
				repeat
					task.wait()
					shared.currentPoint = v.Position
					if broomjobpart ~= nil then
						if broomjobpart.Transparency == 1 then
							shared.currentPoint = nil
							break
						end
					end
				until (HRP.Position - v.Position).Magnitude < 5
			end
		elseif currentPath.Status ~= pathStatus.Success or shared.currentPoint == nil then
			pathExists = false
		end

		shared.currentPoint = nil
	end

	local function BestBroomSpot()
		local bestspot, bestdistance = nil, nil

		for i, v in pairs(game:GetService("Workspace").Jobs.BroomClean[JobBoard]:GetChildren()) do
			if v.Name:find("Part") and v.Transparency ~= 1 and v.Name ~= "Part9" then
				local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Position).Magnitude

				if bestspot == nil and bestdistance == nil then
					bestspot = v
					bestdistance = distance
				else
					if bestdistance > distance then
						bestspot = v
						bestdistance = distance
					end
				end
			end
		end

		return bestspot
	end

	local function webhook(title, desc, important)
		pcall(function()
			local url = webhookUrl --webhook
			print("webhook?")
			if url == "" then
				return
			end

			local data

			data = {
				["content"] = ping .. " My Brother In Christ!",
				["username"] = "Umar",
				["avatar_url"] = "https://cdn.discordapp.com/avatars/1049015626401853470/a005397b0d5b99c735729b43aa0fa09f.webp?size=80",
				["embeds"] = {
					{
						["author"] = {
							["name"] = "Mighty Omega | " .. title,
							["icon_url"] = "https://cdn.discordapp.com/emojis/1011105474327887954.webp?size=96&quality=lossless",
						},
						["description"] = desc,
						["color"] = 110335,
					},
				},
			}

			local porn = game:GetService("HttpService"):JSONEncode(data)

			local headers = { ["content-type"] = "application/json" }
			request = http_request or request or HttpPost or syn.request or http.request
			local sex = { Url = url, Body = porn, Method = "POST", Headers = headers }
			warn("Sending webhook notification...")
			request(sex)
		end)
	end

	local function sleepWalk(point)
		task.spawn(function()
			shared.AllowSprinting = false

			while task.wait(0.1) and autosleepwalk do
				pcall(function()
					local actionscript = getsenv(game:GetService("Players").LocalPlayer.Backpack.LocalS)
					local StamPercent = (
						game.Players.LocalPlayer.Character.CurrentStamina.Value
						/ game.Players.LocalPlayer.Character.MaxStamina.Value
					) * 100
					local LowStam = ministam

					if isrunning == false and StamPercent >= 100 and shared.AllowSprinting then
						actionscript.runPrompt()
						isrunning = true
						task.wait(1)
					elseif isrunning == true and shared.AllowSprinting then
						repeat
							StamPercent = (
								game.Players.LocalPlayer.Character.CurrentStamina.Value
								/ game.Players.LocalPlayer.Character.MaxStamina.Value
							) * 100
							task.wait()
						until StamPercent <= LowStam
							or StamPercent == 100
							or autosleepwalk == false
							or shared.AllowSprinting == false

						actionscript.stopSprint()
						isrunning = false
					elseif isrunning == true and shared.AllowSprinting == false then
						actionscript.stopSprint()
						isrunning = false
					end
				end)
			end

			shared.AllowSprinting = false
		end)

		local plr = game.Players.LocalPlayer
		local char = plr.Character
		local hum = char.Humanoid
		local PFS = game:GetService("PathfindingService")
		local HRP = char.HumanoidRootPart
		local pathStatus = Enum.PathStatus

		local currentPath
		local ran = pcall(function()
			currentPath = PFS:FindPathAsync(HRP.Position, point)
		end)

		if not ran then
			currentPath = PFS:FindPathAsync(HRP.Position, point.Position)
		end
		local pathExists = false

		if currentPath.Status == pathStatus.Success then
			pathExists = true
			_G.OngoingPath = true

			task.spawn(function()
				while pathExists and task.wait() and _G.currentPoint ~= nil and _G.OngoingPath and autosleepwalk do
					local x, y = pcall(function()
						if (HRP.Position - _G.currentPoint).Magnitude > 5 then
							hum.WalkToPoint = _G.currentPoint
						end
					end)
					if not x then
						warn(y)
					end
				end
			end)

			local lastbroken, LBinit, NotMoving = false, false, false
			local oldhumanpos, lastupdate = nil, nil
			local jumpDebounce = false
			local useOldMethod, TimesBroken, verifiedMoving = false, 0, false

			for i, v in pairs(currentPath:GetWaypoints()) do
				if _G.OngoingPath ~= true then
					return
				end

				if v.Action == Enum.PathWaypointAction.Jump and not jumpDebounce then
					jumpDebounce = true
					task.spawn(function()
						hum:ChangeState(Enum.HumanoidStateType.Jumping)
						task.wait(0.7)
						jumpDebounce = false
					end)
				end

				local part = Instance.new("Part")
				part.Shape = "Ball"
				part.Material = "Neon"
				part.Size = Vector3.new(0.6, 0.6, 0.6)
				part.Position = v.Position + Vector3.new(0, 6, 0)
				part.Anchored = true
				part.CanCollide = false
				part.Parent = game.Workspace

				local oldpos = HRP.Position
				local updatedelay = false

				if lastupdate == nil then
					lastupdate = tick()
				else
					if (tick() - lastupdate) >= 2 then
						lastupdate = tick()
						oldhumanpos = HRP.Position
					end
				end

				if NotMoving and lastbroken and TimesBroken >= 3 then
					useOldMethod = true
				end

				if useOldMethod then
					if autosleepwalk == false then
						game.Debris:AddItem(part, 0.01)
						return
					end
					shared.AllowSprinting = true
					useOldMethod = true
					hum:MoveTo(v.Position)
					hum.MoveToFinished:Wait()
					game.Debris:AddItem(part, 0.01)
				else
					repeat
						task.wait()
						if autosleepwalk == false then
							game.Debris:AddItem(part, 0.01)
							return
						end
						_G.currentPoint = v.Position
						if verifiedMoving then
							shared.AllowSprinting = true
						end

						if
							(HRP.Position - v.Position).Magnitude > 5
							and (HRP.Position - part.Position).Magnitude > 4
						then
							if oldpos ~= HRP.Position and not lastbroken and not updatedelay then
								task.spawn(function()
									updatedelay = true
									oldpos = HRP.Position
									task.delay(1, function()
										updatedelay = false
									end)
								end)
							elseif oldpos == HRP.Position and not lastbroken then
								oldpos = HRP.Position
								lastbroken = true
								print("not moving last broke on")
								verifiedMoving = false
								NotMoving = true
								break
							elseif oldpos == HRP.Position and lastbroken and not LBinit then
								LBinit = true
								task.spawn(function()
									shared.AllowSprinting = false
									task.wait(1)
									if oldpos == HRP.Position and not jumpDebounce then
										print("same spot")
										if TimesBroken <= 0 then
											jumpDebounce = true
											task.spawn(function()
												hum:ChangeState(Enum.HumanoidStateType.Jumping)
												task.wait(0.7)
												jumpDebounce = false
											end)
										else
											print("still happening after jump")
										end
									end

									oldpos = HRP.Position
									lastbroken = false
									LBinit = false
									TimesBroken = TimesBroken + 1
								end)
							end
						elseif oldhumanpos ~= nil then
							if (HRP.Position - oldhumanpos).Magnitude <= 0.05 and not jumpDebounce then
								jumpDebounce = true
								task.spawn(function()
									hum:ChangeState(Enum.HumanoidStateType.Jumping)
									task.wait(0.7)
									jumpDebounce = false
								end)
								oldhumanpos = nil
								print("NOT MOVING")
								NotMoving = true
								break
							end
						end
						if (HRP.Position - oldpos).Magnitude > 1 then
							verifiedMoving = true
						end
					until (HRP.Position - v.Position).Magnitude < PointRangeTilNext
						or (HRP.Position - part.Position).Magnitude < 5
						or _G.OngoingPath ~= true
						or autosleepwalk == false
					game.Debris:AddItem(part, 0.01)
				end
			end

			_G.OngoingPath = false
			return true
		elseif currentPath.Status ~= pathStatus.Success or _G.currentPoint == nil then
			pathExists = false

			if currentPath.Status ~= pathStatus.Success then
				return nil
			else
				return true
			end
		end
	end

	local function ASworkaround()
		local newSequence

		for i, v in pairs(AutoSleepPaths) do
			local InsidePos = v["Sequence"][1]
			local MinimumDist = v["IsInsideDist"]
			local IsCorrectPlace = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - InsidePos.Position).Magnitude
				<= MinimumDist

			if IsCorrectPlace then
				newSequence = v["Sequence"]
			end
		end

		if not newSequence then
			return false
		end

		autosleepwalk = true

		for i, v in pairs(newSequence) do
			local result = sleepWalk(v.Position)
			if result ~= true then
				autosleepwalk = false
				return false
			else
				print("Completed Step ", i)
			end
		end

		return true
	end

	local function maintenancechecks()
		if AutoStop then
			local Fatigue = tonumber(
				game.Players.LocalPlayer.PlayerGui.MainGui.Utility.BodyFatigue.Text:split(" ")[3]:split("%")[1]
			)
			if Fatigue >= FatigueToStop then
				if #trainingsTodo > 0 then
					trainingsTodo = {}
				end
				disableAllTraining()
				if macroruin then
					webhook("Macro Notifier", "Max Fatigue Reached!")
				end

				if LogOnFatigued then
					if macroruin then
						webhook("Macro Notifier", "Logging. Fatigue full")
						task.wait(3)
					end

					repeat
						task.wait()
					until game.Players.LocalPlayer.PlayerGui.MainGui.Utility.CombatTag.Visible == false
					game:shutdown()
					return
				elseif autosleepRes or autosleepLog then
					autosleepwalk = true
					local GUI = game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("TreadmillMachineGUI")
						or game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("BarbellMachineGUI")
						or game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("SquatMachineGUI")

					if game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool") then
						game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
					end

					if GUI then
						task.spawn(function()
							SimulateClick(GUI.Frame.Close, "Function")
						end)
						task.wait(1)
					end

					local sleepWalkBack = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame

					if macroruin then
						webhook("Auto Sleep", "Starting Pathfinding to a bed")
						task.wait()
					end

					_G.currentPoint = nil
					_G.OngoingPath = false

					local UnoccupiedBed = GetBed()
					local IsCloseEnough = (
						UnoccupiedBed.Matress.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position
					).Magnitude <= UnoccupiedBed.ClickDetector.MaxActivationDistance

					if not IsCloseEnough then
						local sleepResult, err = sleepWalk(UnoccupiedBed:FindFirstChild("Matress").CFrame)

						if sleepResult ~= true then
							local workaroundResult = ASworkaround()
							if workaroundResult ~= true then
								return webhook(
									"Auto Sleep",
									"Sleep walk was unsuccessful(most likely unsupported place)"
								)
							else
								UnoccupiedBed = GetBed()
								sleepResult = sleepWalk(UnoccupiedBed:FindFirstChild("Matress").CFrame)
								if sleepResult ~= true then
									return webhook("Auto Sleep", "Sleep walk workaround was unsuccessful")
								end
							end
						end
					end

					autosleepwalk = false

					repeat
						task.wait()
						if UnoccupiedBed:FindFirstChild("OccupiedBy") == nil then
							fireclickdetector(UnoccupiedBed.ClickDetector)
							task.wait(1)
							if UnoccupiedBed:FindFirstChild("OccupiedBy") then
								if
									UnoccupiedBed:FindFirstChild("OccupiedBy").Value
									== game.Players.LocalPlayer.Character
								then
									break
								end
							end
						else
							if UnoccupiedBed.OccupiedBy.Value ~= game.Players.LocalPlayer.Character then
								UnoccupiedBed = GetBed()
							else
								break
							end

							local sleepResult, err = sleepWalk(UnoccupiedBed:FindFirstChild("Blanket").CFrame)

							if sleepResult ~= true then
								return webhook("Auto Sleep", "Sleep walk was unsuccessful: " .. err)
							end
						end
					until IsSleeping()

					if macroruin then
						webhook("Auto Sleep", "Successfully reached bed, sleeping fatigue off")
						task.wait()
					end

					repeat
						local Fatigue = tonumber(
							game.Players.LocalPlayer.PlayerGui.MainGui.Utility.BodyFatigue.Text
								:split(" ")[3]
								:split("%")[1]
						)
						task.wait()
					until Fatigue <= 0

					if autosleepLog then
						if macroruin then
							webhook("Auto Sleep", "Logging. Fatigue 0%")
							task.wait(3)
						end

						repeat
							task.wait()
						until game.Players.LocalPlayer.PlayerGui.MainGui.Utility.CombatTag.Visible == false
						game:shutdown()
						return
					elseif autosleepRes then
						fireclickdetector(UnoccupiedBed.ClickDetector)
						task.wait(1)

						autosleepwalk = true

						if macroruin then
							webhook("Auto Sleep", "0% Fatigue! heading towards last spot")
						end

						if not UnoccupiedBed.Parent.Name:find("Apartment") then
							local trainWalk, err = sleepWalk(sleepWalkBack)

							if trainWalk ~= true then
								autosleepwalk = false
								return webhook("Auto Sleep", "Pathfinding after sleeping was unsuccessful: " .. err)
							end

							local distancefromSpot = (
								sleepWalkBack.Position
								- game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.Position
							).Magnitude

							if distancefromSpot <= 1 then
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =
									CFrame.new(sleepWalkBack.Position)
								task.wait(0.3)
								game:GetService("TweenService")
									:Create(
										game.Players.LocalPlayer.Character.HumanoidRootPart,
										TweenInfo.new(0.3),
										{ ["CFrame"] = sleepWalkBack }
									)
									:Play()
								task.wait(0.3)
							elseif distancefromSpot <= 10 and distancefromSpot > 1 then
								game.Players.LocalPlayer.Character.Humanoid:MoveTo(sleepWalkBack.Position)
								game.Players.LocalPlayer.Character.Humanoid.MoveToFinished:Wait()
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =
									CFrame.new(sleepWalkBack.Position)
								task.wait(0.3)
								game:GetService("TweenService")
									:Create(
										game.Players.LocalPlayer.Character.HumanoidRootPart,
										TweenInfo.new(0.3),
										{ ["CFrame"] = sleepWalkBack }
									)
									:Play()
								task.wait(0.3)
							end
						end

						autosleepwalk = false

						for i, v in pairs(trainingsTodo) do
							v:SetState(true)
						end

						trainingsTodo = {}
						if macroruin then
							webhook("Macro Notifier", "Successfully resumed training after sleeping")
						end
					end
				end
			end
		end

		if LogOnNotEnoughMoney and machines then
			local Money =
				tonumber(game:GetService("Players").LocalPlayer.PlayerGui.MainGui.Utility.Money.Text:split("$")[2])

			if Money ~= nil then
				if Money < 65 then
					if macroruin then
						webhook("Macro Notifier", "Not Enough Money to Continue Machines")
						task.wait(3)
					end

					repeat
						task.wait()
					until game.Players.LocalPlayer.PlayerGui.MainGui.Utility.CombatTag.Visible == false
					game:shutdown()
				end
			end
		end

		if autoeat then
			local hungerpercent = (
				game:GetService("Players").LocalPlayer.PlayerGui.MainGui.Utility.StomachBar.BarF.Bar.AbsoluteSize.X
				/ game:GetService("Players").LocalPlayer.PlayerGui.MainGui.Utility.StomachBar.BarF.AbsoluteSize.X
			) * 100
			local foodfound

			if hungerpercent <= EatAt then
				foodfound = false
				for i, v in pairs(MOfoods) do
					if foodfound == false then
						if game.Players.LocalPlayer.Backpack:FindFirstChild(v) then
							foodfound = true
						end
					end

					if game.Players.LocalPlayer.Backpack:FindFirstChild(v) and autoeat and hungerpercent < FillUp then
						local function AutoEat()
							if stopAEinCombat then
								if game.Players.LocalPlayer.PlayerGui.MainGui.Utility.CombatTag.Visible == true then
									return
								end
							end
							repeat
								hungerpercent = (
									game:GetService("Players").LocalPlayer.PlayerGui.MainGui.Utility.StomachBar.BarF.Bar.AbsoluteSize.X
									/ game:GetService("Players").LocalPlayer.PlayerGui.MainGui.Utility.StomachBar.BarF.AbsoluteSize.X
								) * 100
								if
									game.Players.LocalPlayer.Backpack:FindFirstChild(v) == nil
									and game.Players.LocalPlayer.Character:FindFirstChild(v) == nil
								then
									break
								end

								if hungerpercent < FillUp or autoeat ~= false then
									local food = game.Players.LocalPlayer.Backpack:FindFirstChild(v)
										or game.Players.LocalPlayer.Character:FindFirstChild(v)
									if food.Parent ~= game.Players.LocalPlayer.Character then
										game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
										task.wait(0.1)
										game.Players.LocalPlayer.Character.Humanoid:EquipTool(food)
										task.wait(0.1)
									end
									food:Activate()
									task.wait(3)
									hungerpercent = (
										game:GetService("Players").LocalPlayer.PlayerGui.MainGui.Utility.StomachBar.BarF.Bar.AbsoluteSize.X
										/ game:GetService("Players").LocalPlayer.PlayerGui.MainGui.Utility.StomachBar.BarF.AbsoluteSize.X
									) * 100
								end
								hungerpercent = (
									game:GetService("Players").LocalPlayer.PlayerGui.MainGui.Utility.StomachBar.BarF.Bar.AbsoluteSize.X
									/ game:GetService("Players").LocalPlayer.PlayerGui.MainGui.Utility.StomachBar.BarF.AbsoluteSize.X
								) * 100
							until hungerpercent >= FillUp or autoeat == false
							game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
						end

						hungerpercent = (
							game:GetService("Players").LocalPlayer.PlayerGui.MainGui.Utility.StomachBar.BarF.Bar.AbsoluteSize.X
							/ game:GetService("Players").LocalPlayer.PlayerGui.MainGui.Utility.StomachBar.BarF.AbsoluteSize.X
						) * 100
						if hungerpercent < FillUp and autoeat then
							AutoEat()
						end
					end
				end

				if foodfound ~= nil then
					if foodfound == false then
						if NoFoodNotify then
							webhook("Macro Notifier", "You ran out of food.")
							disableAllTraining()
						end

						if LogOnNoFood then
							if NoFoodNotify then
								webhook("No Food Notifier", "You ran out of food. Logging.")
								task.wait(3)
							end

							repeat
								task.wait()
							until game.Players.LocalPlayer.PlayerGui.MainGui.Utility.CombatTag.Visible == false
							game:shutdown()
						end
					end
				end
			end
		end

		if autosupplement then
			if selectedsupplement ~= nil then
				if
					game:GetService("Players").LocalPlayer.PlayerGui.MainGui.Utility.VisualFrame
							:FindFirstChild(selectedsupplement)
						== nil
					and game.Players.LocalPlayer.Backpack:FindFirstChild(selectedsupplement)
				then
					local oldQuantity = nil
					game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
					task.wait(0.1)
					game.Players.LocalPlayer.Character.Humanoid:EquipTool(
						game.Players.LocalPlayer.Backpack:FindFirstChild(selectedsupplement)
					)
					task.wait(0.1)
					oldQuantity = game.Players.LocalPlayer.Character:FindFirstChild(selectedsupplement).Quantity.Value
					game.Players.LocalPlayer.Character:FindFirstChild(selectedsupplement):Activate()
					task.wait(0.1)
					repeat
						local took = false

						if game.Players.LocalPlayer.Character:FindFirstChild(selectedsupplement) == nil then
							took = true
						else
							if
								game.Players.LocalPlayer.Character:FindFirstChild(selectedsupplement).Quantity.Value
								~= oldQuantity
							then
								took = true
							end
						end
						task.wait()
					until took == true
					game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
					task.wait(0.1)
				end
			end
		end
	end

	local function automacrosprint()
		if CurrentRegening then
			shared.AllowSprinting = false
			VIM:SendKeyEvent(true, "W", false, game)
			task.wait(0.5)
		else
			shared.AllowSprinting = true
			VIM:SendKeyEvent(true, "W", false, game)
			task.wait(0.5)
		end
	end

	local function panicdash()
		if not panicdashdebounce then
			panicdashdebounce = true
			local haha = { "W", "A", "S", "D" }
			local randomdirection = haha[math.random(1, #haha)]

			VIM:SendKeyEvent(false, "W", false, game)
			task.wait()
			VIM:SendKeyEvent(true, randomdirection, false, game)
			task.wait(0.02)
			VIM:SendKeyEvent(true, "Q", false, game)
			task.wait()
			VIM:SendKeyEvent(false, "Q", false, game)
			task.wait(0.02)
			VIM:SendKeyEvent(false, randomdirection, false, game)
			task.wait()
			VIM:SendKeyEvent(true, "W", false, game)
			task.wait()
			task.delay(panicdashdelay, function()
				panicdashdebounce = false
			end)
			if CurrentRegening == false then
				automacrosprint()
			end
		end
	end

	local function StaminaCheck(lowstam, stamto)
		if lowstam == nil then
			lowstam = ministam
		end
		local function GetStamina()
			return (
				game.Players.LocalPlayer.Character.CurrentStamina.Value
				/ game.Players.LocalPlayer.Character.MaxStamina.Value
			) * 100
		end

		local function LowStamina()
			if stamto == nil then
				if regenstamina then
					stamto = regentoamt
				else
					stamto = ministam
				end
			end

			if CurrentRegening == false then
				task.spawn(function()
					repeat
						task.wait()
						CurrentRegening = true
					until GetStamina() >= stamto
					CurrentRegening = false
				end)
			end
		end

		if GetStamina() <= lowstam and CurrentRegening == false then
			LowStamina()
		end
	end

	local function panicstamcheck()
		local function GetStamina()
			return (
				game.Players.LocalPlayer.Character.CurrentStamina.Value
				/ game.Players.LocalPlayer.Character.MaxStamina.Value
			) * 100
		end

		local function LowStamina()
			if CurrentRegening == false then
				task.spawn(function()
					repeat
						task.wait()
						shared.AllowSprinting = false
						CurrentRegening = true
					until GetStamina() >= regentoamt
					CurrentRegening = false
				end)
			end
		end

		if GetStamina() <= ministam then
			LowStamina()
		end
	end

	local function esp(plrobj)
		if plrobj == game.Players.LocalPlayer or ESP == false then
			return
		end

		local NameLabel = Drawing.new("Text")
		NameLabel.Visible = false
		NameLabel.Center = true
		NameLabel.Outline = true
		NameLabel.Font = 2
		NameLabel.Color = Color3.fromRGB(66, 135, 245)
		NameLabel.Size = 13

		local HPLabel = Drawing.new("Text")
		HPLabel.Visible = false
		HPLabel.Center = true
		HPLabel.Outline = true
		HPLabel.Font = 2
		HPLabel.Color = Color3.fromRGB(255, 255, 255)
		HPLabel.Size = 13

		local StyleLabel = Drawing.new("Text")
		StyleLabel.Visible = false
		StyleLabel.Center = true
		StyleLabel.Outline = true
		StyleLabel.Font = 2
		StyleLabel.Color = Color3.fromRGB(255, 255, 255)
		StyleLabel.Size = 13

		local style

		local function FindStyle()
			pcall(function()
				local tool = plrobj.Character:FindFirstChildOfClass("Tool")
				if tool ~= nil then
					if tool:FindFirstChild("Style") then
						style = tool.Name
						return
					end
				end

				for i, v in pairs(plrobj.Backpack:GetChildren()) do
					if v:FindFirstChild("Style") then
						style = v.Name
						return
					end
				end

				style = "None"
				return
			end)
		end

		FindStyle()

		local renderstepped
		renderstepped = rs.RenderStepped:Connect(function()
			pcall(function()
				local distance = (
					plrobj.Character.HumanoidRootPart.Position
					- game.Players.LocalPlayer.Character.HumanoidRootPart.Position
				).Magnitude

				if plrobj.Character ~= nil and plrobj.Character:FindFirstChild("Head") and distance <= ESPDistance then
					local plr_pos, plr_onscreen = camera:WorldToViewportPoint(plrobj.Character.Head.Position)

					if game.Players:FindFirstChild(plrobj.Name) == nil or ESP == false then
						NameLabel:Remove()
						StyleLabel:Remove()
						HPLabel:Remove()
						renderstepped:Disconnect()
					end

					if plr_onscreen then
						local ToolEquipped = plrobj.Character:FindFirstChildOfClass("Tool") or { Name = "nil" }
						NameLabel.Position = Vector2.new(plr_pos.X, plr_pos.Y - 50)
						NameLabel.Text = "["
							.. plrobj.Name
							.. "]["
							.. round(
								(
									plrobj.Character.HumanoidRootPart.Position
									- game.Players.LocalPlayer.Character.HumanoidRootPart.Position
								).Magnitude
							)
							.. "]"
						NameLabel.Visible = true

						HPLabel.Position = Vector2.new(plr_pos.X, plr_pos.Y - 35)
						HPLabel.Text = "["
							.. round(((plrobj.Character.Humanoid.Health / plrobj.Character.Humanoid.MaxHealth) * 100))
							.. "% HP]"
							.. "["
							.. round((plrobj.Character.CurrentStamina.Value / plrobj.Character.MaxStamina.Value) * 100)
							.. "% Stam]"
						HPLabel.Visible = true

						StyleLabel.Position = Vector2.new(plr_pos.X, plr_pos.Y - 20)
						StyleLabel.Text = "[" .. style .. "][" .. ToolEquipped.Name .. "]"
						StyleLabel.Visible = true
					else
						NameLabel.Visible = false
						HPLabel.Visible = false
						StyleLabel.Visible = false
					end
				else
					NameLabel.Visible = false
					HPLabel.Visible = false
					StyleLabel.Visible = false
				end
			end)
		end)
	end

	local function GetPunchingBag()
		local bestdistance, bag = nil, nil
		local baginstances = {
			game:GetService("Workspace")["Bag Wrestling"],
			workspace,
			game:GetService("Workspace")["Kung Fu Dojo"].Bag,
			game:GetService("Workspace").Model,
			game:GetService("Workspace")["Organisation Building"],
			workspace["Judo Dojo"].bags,
		}

		for _, instance in pairs(baginstances) do
			for i, v in pairs(instance:GetChildren()) do
				if v.Name == "PunchingBag" or v:FindFirstChild("PunchingBag") then
					if v:FindFirstChild("PunchingBag") then
						v = v:FindFirstChild("PunchingBag")
					end
					local distance = (v.bag.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude

					if distance <= 10 then
						if bestdistance == nil and bag == nil then
							bestdistance = distance
							bag = v
						elseif bestdistance > distance then
							bestdistance = distance
							bag = v
						end
					end
				end
			end
		end

		return bag
	end

	local function GetStyle()
		local tool = game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool")
		if tool ~= nil then
			if tool:FindFirstChild("Style") then
				return tool
			end
		end

		for i, v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
			if v:FindFirstChild("Style") then
				return v
			end
		end

		return nil
	end

	local function GetClosestRoadwork()
		local rw, bestdistance = nil, nil

		for i, v in pairs(workspace:GetChildren()) do
			if v.Name:find("Roadwork") then
				local Closest = 100
				local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Head.Position).Magnitude

				if distance <= Closest then
					if rw and bestdistance then
						if distance < bestdistance then
							rw = v
							bestdistance = distance
						end
					else
						rw = v
						bestdistance = distance
					end
				end
			end
		end

		return rw
	end

	local function GetDuraBuy()
		local bestdistance, durabuy = nil, nil
		local durainstances = {
			workspace,
			workspace.kUREtRAINER,
		}

		for _, instance in pairs(durainstances) do
			for i, v in pairs(instance:GetChildren()) do
				if v.Name:find("Durability Training") or v:FindFirstChild("Durability Training: $140") then
					if v:FindFirstChild("Durability Training: $140") then
						v = v:FindFirstChild("Durability Training: $140")
					end

					local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Head.Position).Magnitude
					local MaxActivationDist = v.ClickDetector.MaxActivationDistance

					if distance <= MaxActivationDist then
						if bestdistance == nil and durabuy == nil then
							bestdistance = distance
							durabuy = v
						elseif bestdistance > distance then
							bestdistance = distance
							durabuy = v
						end
					end
				end
			end
		end

		return durabuy
	end

	local function duraturn(main, support)
		if durability == false then
			return
		end
		if main.Character.Humanoid.Health < main.Character.Humanoid.MaxHealth then
			repeat
				task.wait()
			until main.Character.Humanoid.Health >= main.Character.Humanoid.MaxHealth
			task.wait(0.5)
		end
		local distancebetweenplrs = (
			main.Character.HumanoidRootPart.Position - support.Character.HumanoidRootPart.Position
		).Magnitude
		if GetDuraBuy() == nil and SkillXP == false then
			return
		end
		if distancebetweenplrs > 17 and distancebetweenplrs <= 200 then
			repeat
				local newdistancebetweenplayers = (
					main.Character.HumanoidRootPart.Position - support.Character.HumanoidRootPart.Position
				).Magnitude
				task.wait()
			until newdistancebetweenplayers <= 17
			task.wait(0.5)
		end
		local mychar = game.Players.LocalPlayer.Character

		if support.Character.Name == mychar.Name and durability then
			if not SkillXP then
				repeat
					task.wait()
				until main.Character:FindFirstChild("DuraTrain") or durability == false

				local combatTool = GetStyle()
				local IsCombatEquipped = true
				pcall(function()
					local DaCustomTool = game.Players.LocalPlayer.Backpack:FindFirstChild(DuraTool)
						or game.Players.LocalPlayer.Character:FindFirstChild(DuraTool)
						or "None"

					if DaCustomTool == nil or DaCustomTool == "None" then
						print("USING Default")
						IsCombatEquipped = false
					else
						print("USING ", DaCustomTool)
						combatTool = DaCustomTool
					end
				end)

				if combatTool.Parent == game.Players.LocalPlayer.Backpack and durability then
					game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
					task.wait(0.1)
					game.Players.LocalPlayer.Character.Humanoid:EquipTool(combatTool)
					task.wait(0.1)
				end

				repeat
					local healthpercent = (main.Character.Humanoid.Health / main.Character.Humanoid.MaxHealth) * 100

					if healthpercent > stopAtHP and durability and main.Character:FindFirstChild("DuraTrain") then
						if durability and RhythmToggle and IsCombatEquipped then
							ChargeRhythm(combatTool)
						end

						if
							combatTool.Parent == game.Players.LocalPlayer.Character
							and main.Character:FindFirstChild("DuraTrain")
						then
							combatTool:Activate()
							task.wait(0.05)
						end
					elseif
						combatTool.Parent == game.Players.LocalPlayer.Backpack
						and durability
						and main.Character:FindFirstChild("DuraTrain")
					then
						game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
						task.wait(0.1)
						game.Players.LocalPlayer.Character.Humanoid:EquipTool(combatTool)
						task.wait(0.1)
					end

					task.wait()
				until healthpercent <= stopAtHP and main.Character:FindFirstChild("DuraTrain") == nil
					or durability == false
				task.wait(0.1)
				game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
				task.wait(0.9)
			else
				repeat
					local SkillTool, SkillHotbar = GetSkill()
					local healthpercent = (main.Character.Humanoid.Health / main.Character.Humanoid.MaxHealth) * 100

					if healthpercent > stopAtHP and SkillTool ~= nil and SkillHotbar ~= nil then
						if SkillTool.Parent == game.Players.LocalPlayer.Character and not SkillHotbar.CD.Visible then
							SkillTool:Activate()
							task.wait(1)
							repeat
								task.wait()
							until SkillHotbar.CD.Visible
						elseif SkillTool.Parent == game.Players.LocalPlayer.Backpack and not SkillHotbar.CD.Visible then
							game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
							task.wait(0.5)
							game.Players.LocalPlayer.Character.Humanoid:EquipTool(SkillTool)
							task.wait(0.5)
							SkillTool:Activate()
							task.wait(1)
							repeat
								task.wait()
							until SkillHotbar.CD.Visible
						end
					end
					task.wait()
				until healthpercent <= stopAtHP or durability == false or SkillXP == false
				task.wait(0.1)
				game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
				task.wait(0.9)
			end
		elseif main.Character.Name == mychar.Name and durability then
			if not SkillXP then
				local Dura = GetDuraBuy()
				local BeforeDuraDonePos

				if main.Character.Humanoid.Health < main.Character.Humanoid.MaxHealth then
					repeat
						task.wait()
					until main.Character.Humanoid.Health >= main.Character.Humanoid.MaxHealth
					task.wait(0.5)
				end

				if game.Players.LocalPlayer.Character:FindFirstChild("DuraTrain") == nil and durability then
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Durability Training") and durability then
						game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
						task.wait(0.1)
						game.Players.LocalPlayer.Character.Humanoid:EquipTool(
							game.Players.LocalPlayer.Backpack:FindFirstChild("Durability Training")
						)
						task.wait(0.1)
						game.Players.LocalPlayer.Character:FindFirstChild("Durability Training"):Activate()
						task.wait(0.1)
					elseif game.Players.LocalPlayer.Character:FindFirstChild("Durability Training") and durability then
						game.Players.LocalPlayer.Character:FindFirstChild("Durability Training"):Activate()
						task.wait(0.1)
					elseif durability then
						repeat
							fireclickdetector(Dura.ClickDetector)
							task.wait(1)
						until game.Players.LocalPlayer.Backpack:FindFirstChild("Durability Training")

						game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
						task.wait(0.1)
						game.Players.LocalPlayer.Character.Humanoid:EquipTool(
							game.Players.LocalPlayer.Backpack:FindFirstChild("Durability Training")
						)
						task.wait(0.1)
						game.Players.LocalPlayer.Character:FindFirstChild("Durability Training"):Activate()
						task.wait(0.1)
					end
				end

				BeforeDuraDonePos = game.Players.LocalPlayer.Character.HumanoidRootPart.Position

				repeat
					local healthpercent = (
						game.Players.LocalPlayer.Character.Humanoid.Health
						/ game.Players.LocalPlayer.Character.Humanoid.MaxHealth
					) * 100
					task.wait()

					if healthpercent <= stopAtHP then
						repeat
							game.Players.LocalPlayer.Character:FindFirstChild("Durability Training"):Activate()
							task.wait(1)
						until game.Players.LocalPlayer.Character:FindFirstChild("Durability Training") == nil
							or game.Players.LocalPlayer.Character:FindFirstChild("DuraTrain") == nil
					end

				until healthpercent <= stopAtHP
						and game.Players.LocalPlayer.Character:FindFirstChild("DuraTrain") == nil
					or durability == false

				task.wait(1)

				if AutoWalkAfterPushedBack then
					local distance = (BeforeDuraDonePos - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude

					if distance > 2 then
						game.Players.LocalPlayer.Character.Humanoid:MoveTo(BeforeDuraDonePos)
						game.Players.LocalPlayer.Character.Humanoid.MoveToFinished:Wait()
					end
				end
			else
				repeat
					local healthpercent = (
						game.Players.LocalPlayer.Character.Humanoid.Health
						/ game.Players.LocalPlayer.Character.Humanoid.MaxHealth
					) * 100
					task.wait()
				until healthpercent <= stopAtHP or durability == false or SkillXP == false
			end
		end
	end

	local function debuffCheck()
		if game.Players.LocalPlayer.Character.Ragdolled.Value == true then
			return false
		end

		return true
	end

	main:Label("Pushup/Squat auto train lowest mini stam is 15")
	trainingtoggles[#trainingtoggles + 1] = main:Toggle("Auto Train", false, function(Value)
		autotrain = Value

		while autotrain and task.wait() do
			StaminaCheck()
			maintenancechecks()
			pcall(function()
				if traintype ~= nil and trainspeed ~= nil then
					if traintype ~= "Stamina" then
						if game.Players.LocalPlayer.Character:FindFirstChild(traintype) then
							if trainspeed == "Slow" and CurrentRegening == false and debuffCheck() then
								local oldFatigue = tonumber(
									game.Players.LocalPlayer.PlayerGui.MainGui.Utility.BodyFatigue.Text
										:split(" ")[3]
										:split("%")[1]
								)
								game.Players.LocalPlayer.Character[traintype]:Activate()
								local curtime = tick()
								repeat
									task.wait()
								until tonumber(
											game.Players.LocalPlayer.PlayerGui.MainGui.Utility.BodyFatigue.Text
												:split(" ")[3]
												:split("%")[1]
										)
										~= oldFatigue
									or (tick() - curtime) >= 5
									or game.Players.LocalPlayer.Character:FindFirstChild(traintype) == nil
							elseif trainspeed == "Fast" and CurrentRegening == false and debuffCheck() then
								game.Players.LocalPlayer.Character[traintype]:Activate()
							end
						elseif
							game.Players.LocalPlayer.Backpack:FindFirstChild(traintype) and CurrentRegening == false
						then
							game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
							task.wait(0.1)
							game.Players.LocalPlayer.Character.Humanoid:EquipTool(
								game.Players.LocalPlayer.Backpack:FindFirstChild(traintype)
							)
							task.wait(0.1)
						end
					elseif traintype == "Stamina" then
						while task.wait(0.1) and autotrain and traintype == "Stamina" do
							pcall(function()
								local actionscript = getsenv(game:GetService("Players").LocalPlayer.Backpack.LocalS)
								local StamPercent = (
									game.Players.LocalPlayer.Character.CurrentStamina.Value
									/ game.Players.LocalPlayer.Character.MaxStamina.Value
								) * 100
								local LowStam = ministam

								if isrunning == false and StamPercent >= 100 and autotrain then
									actionscript.runPrompt()
									isrunning = true
									task.wait(1)
								elseif isrunning == true and autotrain then
									repeat
										StamPercent = (
											game.Players.LocalPlayer.Character.CurrentStamina.Value
											/ game.Players.LocalPlayer.Character.MaxStamina.Value
										) * 100
										task.wait()
									until StamPercent <= LowStam or StamPercent == 100 or autotrain == false

									if StamPercent < 100 or autotrain == false then
										actionscript.stopSprint()
										maintenancechecks()
									end
									isrunning = false
								end
							end)
						end
					end
				end
			end)
		end
	end)

	main:Slider("Minimum Stamina %", { min = 0, max = 100, def = ministam }, function(Value)
		ministam = Value
	end)

	main:Toggle("Regen Stamina", false, function(Value)
		regenstamina = Value
	end)

	main:Slider("Regen Stamina To %", { min = 0, max = 100, def = regentoamt }, function(Value)
		regentoamt = Value
	end)

	main:Dropdown("Train Type", { "Push up", "Squat", "Stamina" }, function(Value)
		traintype = Value
	end)

	main:Dropdown("Train Speed", { "Fast", "Slow" }, function(Value)
		trainspeed = Value
	end)

	trainingtoggles[#trainingtoggles + 1] = main:Toggle("Strike Speed", false, function(Value)
		strikespeed = Value

		local comboconnection
		comboconnection = game.Players.LocalPlayer.Character.ChildAdded:Connect(function(v)
			if strikespeed == false then
				comboconnection:Disconnect()
				return
			end
			if v.Name == "Attacking" and strikespeed then
				currentcombo = v.Value
			end
		end)

		while task.wait() and strikespeed do
			pcall(function()
				local bag = GetPunchingBag()
				local ssbuy = GetSSBuy()
				local combatTool = GetStyle()

				if bag ~= nil and ssbuy ~= nil and strikespeed then
					if
						game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("SpeedTraining") == nil
						and strikespeed
					then
						if
							game.Players.LocalPlayer.Backpack:FindFirstChild("Strike Speed Training") == nil
							and game.Players.LocalPlayer.Character:FindFirstChild("Strike Speed Training") == nil
							and strikespeed
						then
							maintenancechecks()
							game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
							task.wait(0.1)
							fireclickdetector(ssbuy.ClickDetector)
							task.wait(0.5)
							game.Players.LocalPlayer.Character.Humanoid:EquipTool(
								game.Players.LocalPlayer.Backpack:FindFirstChild("Strike Speed Training")
							)
							task.wait(0.2)
							repeat
								task.wait(0.5)
								if
									game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("SpeedTraining")
									== nil
								then
									game.Players.LocalPlayer.Character
										:FindFirstChild("Strike Speed Training")
										:Activate()
								end
							until game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("SpeedTraining")
						elseif
							game.Players.LocalPlayer.Character:FindFirstChild("Strike Speed Training") and strikespeed
						then
							repeat
								task.wait(0.5)
								if
									game:GetService("Players").LocalPlayr.PlayerGui:FindFirstChild("SpeedTraining")
									== nil
								then
									game.Players.LocalPlayer.Character
										:FindFirstChild("Strike Speed Training")
										:Activate()
								end
							until game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("SpeedTraining")
						elseif
							game.Players.LocalPlayer.Backpack:FindFirstChild("Strike Speed Training") and strikespeed
						then
							maintenancechecks()
							game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
							task.wait(0.1)
							game.Players.LocalPlayer.Character.Humanoid:EquipTool(
								game.Players.LocalPlayer.Backpack:FindFirstChild("Strike Speed Training")
							)
							task.wait(0.2)
							repeat
								task.wait(0.5)
								if
									game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("SpeedTraining")
									== nil
								then
									game.Players.LocalPlayer.Character
										:FindFirstChild("Strike Speed Training")
										:Activate()
								end
							until game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("SpeedTraining")
						end
					else
						pcall(function()
							if combatTool.Parent ~= game.Players.LocalPlayer.Character and strikespeed then
								game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
								task.wait(0.3)
								game.Players.LocalPlayer.Character.Humanoid:EquipTool(combatTool)
								task.wait(0.1)
							end

							local m2nextturn = false
							repeat
								if strikespeed and RhythmToggle then
									ChargeRhythm(combatTool)
								end

								if
									game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("SpeedTraining")
										~= nil
									and strikespeed
								then
									if
										game:GetService("Players").LocalPlayer.PlayerGui.SpeedTraining.CanHit.Value
											== true
										and combatTool.Parent == game.Players.LocalPlayer.Character
										and strikespeed
									then
										if combatTool.Parent == game.Players.LocalPlayer.Character then
											if not m2nextturn then
												repeat
													combatTool:Activate()
													task.wait()
												until game:GetService("Players").LocalPlayer.PlayerGui.SpeedTraining.CanHit.Value
														== true
													or strikespeed == false
													or combatTool.Parent == game.Players.LocalPlayer.Backpack
											else
												if ssuseM2 then
													repeat
														local successm2 = false

														if currentcombo == 5 then
															successm2 = true
															break
														end
														local VIM = game:GetService("VirtualInputManager")
														VIM:SendMouseButtonEvent(0, 500, 1, true, game, 1)
														task.wait(0.1)
														VIM:SendMouseButtonEvent(0, 500, 1, false, game, 1)
														task.wait(0.5)
													until successm2 == true
														or strikespeed == false
														or combatTool.Parent == game.Players.LocalPlayer.Backpack
														or ssuseM2 == false
												end
												m2nextturn = false
											end
											local Jaja = tick()
											repeat
												task.wait()
												if currentcombo == 4 and ssuseM2 then
													m2nextturn = true
												end
											until game:GetService("Players").LocalPlayer.PlayerGui.SpeedTraining.CanHit.Value
													== false
												or (tick() - Jaja) >= 0.5
											if currentcombo == 4 and m2nextturn == false and ssuseM2 then
												m2nextturn = true
											end
										end
										task.wait()
									end
								end
								task.wait()
							until game:GetService("Players").LocalPlayer.PlayerGui
										:FindFirstChild("SpeedTraining")
									== nil
								or strikespeed == false
						end)
					end
				end
			end)
		end
	end)

	main:Toggle("SS Use M2", false, function(Value)
		ssuseM2 = Value
	end)

	trainingtoggles[#trainingtoggles + 1] = main:Toggle("Strike Power", false, function(Value)
		strikepower = Value

		local comboconnection
		comboconnection = game.Players.LocalPlayer.Character.ChildAdded:Connect(function(v)
			if strikepower == false then
				comboconnection:Disconnect()
				return
			end
			if v.Name == "Attacking" and strikepower then
				currentcombo = v.Value
			end
		end)

		startPunching = false
		local reequipdebounce = false

		while task.wait() and strikepower do
			local bag = GetPunchingBag()
			local combatTool = GetStyle()

			if bag ~= nil and strikepower then
				local StamPercent = (
					game.Players.LocalPlayer.Character.CurrentStamina.Value
					/ game.Players.LocalPlayer.Character.MaxStamina.Value
				) * 100
				maintenancechecks()

				if startPunching == false then
					if StamPercent < RunToPercent then
						repeat
							StamPercent = (
								game.Players.LocalPlayer.Character.CurrentStamina.Value
								/ game.Players.LocalPlayer.Character.MaxStamina.Value
							) * 100
							task.wait()
						until StamPercent >= RunToPercent or strikepower == false

						startPunching = true
					elseif StamPercent > RunToPercent then
						while task.wait(0.1) and strikepower and startPunching == false do
							if strikepower == false then
								return
							end
							pcall(function()
								local actionscript = getsenv(game:GetService("Players").LocalPlayer.Backpack.LocalS)
								local StamPercent = (
									game.Players.LocalPlayer.Character.CurrentStamina.Value
									/ game.Players.LocalPlayer.Character.MaxStamina.Value
								) * 100

								if isrunning == false and StamPercent > RunToPercent and strikepower then
									actionscript.runPrompt()
									isrunning = true
									task.wait(1)
								elseif isrunning == true and strikepower then
									repeat
										StamPercent = (
											game.Players.LocalPlayer.Character.CurrentStamina.Value
											/ game.Players.LocalPlayer.Character.MaxStamina.Value
										) * 100
										task.wait()
									until StamPercent <= RunToPercent or StamPercent == 100 or strikepower == false

									if StamPercent <= RunToPercent and strikepower then
										actionscript.stopSprint()
										startPunching = true
									end
									isrunning = false
								end
							end)
						end
					end
				elseif
					startPunching
					and StamPercent > RunToPercent
					and StamPercent > PunchStartPercent
					and StamPercent > PunchEndPercent
				then
					startPunching = false
				elseif startPunching and strikepower and combatTool then
					repeat
						StamPercent = (
							game.Players.LocalPlayer.Character.CurrentStamina.Value
							/ game.Players.LocalPlayer.Character.MaxStamina.Value
						) * 100
						task.wait()
					until StamPercent >= PunchStartPercent or strikepower == false or PunchStartPercent < RunToPercent

					maintenancechecks()
					if
						combatTool.Parent == game.Players.LocalPlayer.Backpack
						and strikepower
						and not reequipdebounce
					then
						reequipdebounce = true
						game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
						task.wait(0.1)
						game.Players.LocalPlayer.Character.Humanoid:EquipTool(combatTool)
						task.wait(0.1)
						reequipdebounce = false
					end

					repeat
						maintenancechecks()
						task.wait()
						if strikepower == false then
							return
						end
						task.wait()
						local StamPercent = (
							game.Players.LocalPlayer.Character.CurrentStamina.Value
							/ game.Players.LocalPlayer.Character.MaxStamina.Value
						) * 100
						pcall(function()
							if strikepower and RhythmToggle then
								ChargeRhythm(combatTool)
							end

							if combatTool.Parent == game.Players.LocalPlayer.Character and CurrentRegening == false then
								repeat
									StamPercent = (
										game.Players.LocalPlayer.Character.CurrentStamina.Value
										/ game.Players.LocalPlayer.Character.MaxStamina.Value
									) * 100
									if combatTool.Parent == game.Players.LocalPlayer.Character then
										combatTool:Activate()
									end
									task.wait()
								until currentcombo ~= nil and currentcombo == 4
									or combatTool.Parent == game.Players.LocalPlayer.Backpack
									or StamPercent <= PunchEndPercent
									or startPunching == false
									or StamPercent >= 90

								if currentcombo ~= nil then
									if
										currentcombo == 4
										and m2already == false
										and StamPercent >= PunchEndPercent
										and spuseM2
									then
										repeat
											local successm2 = false

											if
												game.Players.LocalPlayer.Character:FindFirstChild("Attacking")
												and game.Players.LocalPlayer.Character:FindFirstChild("Attacking").Value
													== 5
											then
												successm2 = true
											end
											StamPercent = (
												game.Players.LocalPlayer.Character.CurrentStamina.Value
												/ game.Players.LocalPlayer.Character.MaxStamina.Value
											) * 100
											local VIM = game:GetService("VirtualInputManager")
											VIM:SendMouseButtonEvent(0, 500, 1, true, game, 1)
											task.wait()
											VIM:SendMouseButtonEvent(0, 500, 1, false, game, 1)
											task.wait()
										until successm2 == true
											or strikepower == false
											or StamPercent >= 90
											or combatTool.Parent == game.Players.LocalPlayer.Backpack
										task.wait(0.1)
										m2already = true
									elseif
										currentcombo == 4
										and m2already
										and StamPercent >= PunchEndPercent
										and spuseM2
									then
										currentcombo = nil
										m2already = false
									end
								end
								task.wait()
							end
						end)
					until strikepower == false or StamPercent <= PunchEndPercent or StamPercent >= 90
					startPunching = false
				end
			end
		end
	end)

	main:Toggle("SP Use M2", false, function(Value)
		spuseM2 = Value
	end)

	main:Slider("SP Run to %", { def = RunToPercent, max = 100, min = 0 }, function(Value)
		RunToPercent = Value
	end)

	main:Slider("SP Punch Start %", { def = PunchStartPercent, max = 100, min = 0 }, function(Value)
		PunchStartPercent = Value
	end)

	main:Slider("SP Punch End %", { def = PunchEndPercent, max = 100, min = 0 }, function(Value)
		PunchEndPercent = Value
	end)

	main:Toggle("Use Rhythm on Trainings", false, function(Value)
		RhythmToggle = Value
	end)

	trainingtoggles[#trainingtoggles + 1] = main:Toggle("Machines", false, function(Value)
		machines = Value

		while task.wait() and machines do
			pcall(function()
				if
					game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("TreadmillMachineGUI")
					and machines
					and machinetype ~= nil
					and treadselect ~= nil
				then
					local GUI = game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("TreadmillMachineGUI")

					if GUI and machines then
						if not GUI.Frame3.Visible then
							StaminaCheck(99, 100)
						end

						if GUI.Frame.Visible and machines and CurrentRegening == false then
							SimulateClick(GUI.Frame.StatPickF[treadselect], "Function")
							task.wait(0.1)
						elseif GUI.Frame2.Visible and machines and CurrentRegening == false then
							local i = 5

							repeat
								if not GUI.Frame2.Visible then
									break
								end
								SimulateClick(GUI.Frame2.ListF[tostring(i)], "Function")
								task.wait(0.1)
								i = i - 1
							until i <= 0
						elseif GUI.Frame3.Visible and machines and CurrentRegening == false then
							if GUI.Frame3.Start.Visible and machines and CurrentRegening == false then
								task.spawn(function()
									SimulateClick(GUI.Frame3.Start, "Function")
								end)
								task.wait(0.1)
							elseif not GUI.Frame3.Start.Visible and machines and CurrentRegening == false then
								StaminaCheck()
								if GUI.Frame3.TrainingF.ButtonTemplate.Visible and machines then
									if
										tostring(GUI.Frame3.TrainingF.ButtonTemplate.Input.TextColor3) == "1, 1, 1"
										and CurrentRegening == false
									then
										task.wait(0.07)
										VIM:SendKeyEvent(
											true,
											GUI.Frame3.TrainingF.ButtonTemplate.Input.Text,
											false,
											game
										)
										task.wait()
										VIM:SendKeyEvent(
											false,
											GUI.Frame3.TrainingF.ButtonTemplate.Input.Text,
											false,
											game
										)
										task.wait()
									end
								end
							end
						end
					end
				elseif
					game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("BarbellMachineGUI")
					or game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("SquatMachineGUI")
						and machinetype ~= nil
				then
					local GUI = game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("BarbellMachineGUI")
						or game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("SquatMachineGUI")

					if GUI and machines then
						if GUI.Frame.Visible then
							StaminaCheck(99, 100)
							task.wait()
						end

						if GUI.Frame.Visible and machines and CurrentRegening == false then
							local i = 6

							repeat
								if not GUI.Frame.Visible then
									break
								end
								SimulateClick(GUI.Frame.ListF["Barbell " .. tostring(i) .. " Weight"], "Function")
								task.wait(0.1)
								i = i - 1
							until i <= 0
						elseif GUI.Frame2.Visible and machines and CurrentRegening == false then
							if GUI.Frame2.Start.Visible and machines and CurrentRegening == false then
								task.spawn(function()
									SimulateClick(GUI.Frame2.Start, "Function")
								end)
								task.wait(0.1)
							elseif not GUI.Frame2.Start.Visible and machines and CurrentRegening == false then
								StaminaCheck()
								local Icon = GUI.Frame2.LiftingF:FindFirstChild("LiftIcon")

								if GUI.Frame2.LiftingF.Visible and machines then
									if Icon and CurrentRegening == false then
										task.wait(0.07)
										SimulateClick(Icon, "Function")
									end
								end
							end
						end
					end
				else
					maintenancechecks()

					if LastMachine ~= nil then
						if
							(
									LastMachine.Base.Position
									- game.Players.LocalPlayer.Character.HumanoidRootPart.Position
								).Magnitude
								<= LastMachine.ClickDetector.MaxActivationDistance
							and GetMachineType(LastMachine) == machinetype
						then
							fireclickdetector(LastMachine.ClickDetector)
							task.wait(0.5)
						elseif GetMachineType(LastMachine) ~= machinetype then
							LastMachine = nil
						end
					end

					local MachineQuery = ClosestMachine()
					if MachineQuery ~= nil and debuffCheck() and machinetype ~= nil then
						LastMachine = MachineQuery
						fireclickdetector(LastMachine.ClickDetector)
						task.wait(0.5)
					elseif
						MachineQuery == nil
						and debuffCheck()
						and machinetype ~= nil
						and WalkBackWhenFar
						and LastMachine ~= nil
					then
						game.Players.LocalPlayer.Character.Humanoid:MoveTo(LastMachine.Base)
						task.wait(2)
					end
				end
			end)
		end
		if machines == false and LastMachine ~= nil then
			LastMachine = nil
		end
	end)

	main:Dropdown("Machine", { "Bench", "Squat", "Treadmill" }, function(Value)
		machinetype = Value
	end)

	main:Dropdown("Treadmill Option", { "Stamina", "RunningSpeed" }, function(Value)
		treadselect = Value
	end)

	main:Toggle("Walk Back When Far", false, function(Value)
		WalkBackWhenFar = Value
	end)

	main:Toggle("Log When Money Out", false, function(Value)
		LogOnNotEnoughMoney = Value
	end)

	main:Label("-- make sure both accs have same settings --")
	main:Label("you need 2 accounts that are using the script")

	trainingtoggles[#trainingtoggles + 1] = main:Toggle("Durability", false, function(Value)
		durability = Value

		while task.wait() and durability do
			if ft ~= nil and st ~= nil and durability then
				if game.Players.LocalPlayer.Name == ft or game.Players.LocalPlayer.Name == st and durability then
					local ftplr = game.Players:FindFirstChild(ft)
					local stplr = game.Players:FindFirstChild(st)

					if ftplr.Character ~= nil and stplr.Character ~= nil and not durainprogress and durability then
						local distancebetweenplrs = (
							ftplr.Character.HumanoidRootPart.Position - stplr.Character.HumanoidRootPart.Position
						).Magnitude

						if
							distancebetweenplrs <= 10 and GetDuraBuy() ~= nil
							or SkillXP and distancebetweenplrs <= 10
						then
							maintenancechecks()
							durainprogress = true
							if taketurns then
								repeat
									task.wait()
								until ftplr.Character.Humanoid.Health >= ftplr.Character.Humanoid.MaxHealth
									or durability == false
								duraturn(ftplr, stplr)
								task.wait()
								repeat
									task.wait()
								until stplr.Character.Humanoid.Health >= stplr.Character.Humanoid.MaxHealth
									or durability == false
								duraturn(stplr, ftplr)
							else
								repeat
									task.wait()
								until ftplr.Character.Humanoid.Health >= ftplr.Character.Humanoid.MaxHealth
									or durability == false

								duraturn(ftplr, stplr)
							end
							durainprogress = false
						end
					end
				end
			end
		end
	end)

	main:Textbox("First Turn", function(txt)
		ft = txt
	end)

	main:Textbox("Second Turn", function(txt)
		st = txt
	end)

	main:Toggle("Take Turns", false, function(Value)
		taketurns = Value
	end)

	main:Dropdown("DuraTool", { "Metal Bat", "Revolver", "Default" }, function(Value)
		DuraTool = Value
	end)

	main:Label("-- AutoWalkAfterPushedBack only for dura receiver --")

	main:Toggle("Auto Walk After Pushed Back", false, function(Value)
		AutoWalkAfterPushedBack = Value
	end)

	main:Slider("Health % to Stop", { min = 0, max = 100, def = stopAtHP }, function(Value)
		stopAtHP = Value
	end)

	main:Label("makes dura farm a skill xp farm in sparring arenas")
	main:Label("have the skills on your hotbar for the farm")

	main:Toggle("Skill XP mode", false, function(Value)
		SkillXP = Value
	end)

	notify:Toggle("Staff Notifier", false, function(Value)
		staffnotifier = Value

		if staffnotifier then
			for i, v in pairs(game.Players:GetPlayers()) do
				if staffnotifier then
					Notifier(v)
				end
			end
		end
	end)

	notify:Toggle("Disable All When Staff Joins", false, function(Value)
		disableOnStaff = Value
	end)

	notify:Toggle("Cop Notifier", false, function(Value)
		copnotifier = Value

		if copnotifier then
			for i, v in pairs(game.Players:GetPlayers()) do
				if copnotifier then
					Notifier(v)
				end
			end
		end
	end)

	notify:Toggle("Flow NPC Notifier", false, function(Value)
		flownotifier = Value

		if flownotifier then
			if game:GetService("Workspace"):FindFirstChild("XinFolder") then
				Notifier()
			end

			flowconnection = workspace.Live.ChildAdded:Connect(function()
				if flownotifier then
					if workspace.Live:FindFirstChild("Luke Xin") then
						Notifier()
					end
				end
			end)
		else
			if flowconnection then
				flowconnection:Disconnect()
			end
		end
	end)

	notify:Toggle("Street Fighter Notifier", false, function(Value)
		sfnotifier = Value

		if sfnotifier then
			if game:GetService("Workspace"):FindFirstChild("AokiFolder") then
				Notifier()
			end

			sfconnection = workspace.ChildAdded:Connect(function(child)
				if sfnotifier then
					if child.ClassName == "Folder" and child.Name == "AokiFolder" then
						Notifier()
					end
				end
			end)
		else
			if sfconnection then
				sfconnection:Disconnect()
			end
		end
	end)

	notify:Toggle("Macro Notifier", false, function(Value)
		macroruin = Value

		if macroruin then
			local connection
			connection = game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ChildAdded:Connect(function(child)
				if macroruin ~= true then
					connection:Disconnect()
				end
				if
					child.Name == "ErrorPrompt"
					and child:FindFirstChild("MessageArea")
					and child.MessageArea:FindFirstChild("ErrorFrame")
				then
					task.wait(0.5)
					webhook(
						"Macro Ruin Notifier",
						"You were disconnected Reason:\n"
							.. game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ErrorPrompt.MessageArea.ErrorFrame.ErrorMessage.Text
					)
				end
			end)
		end

		while task.wait() and macroruin do
			if
				game.Players.LocalPlayer.PlayerGui.MainGui.Utility.CombatTag.Visible
				and not macroruindebounce
				and alreadynotifieduser ~= CurrentGanker
				and CurrentGanker ~= nil
			then
				macroruindebounce = true
				local daganker = CurrentGanker
				alreadynotifieduser = daganker

				webhook(
					"Macro Ruin Notifier",
					"You getting macro ganked! you better get yo get back!\n" .. CurrentGanker
				)
				macroruindebounce = false
			end
		end
	end)

	pcall(function()
		if writefile then
			if OPsData == nil then
				local ex = { "PlayerUserIdHere", "AnotherPlayerUserIdHere", "BeSureToAddCommaAfter" }
				writefile("/m1keincorporated/MOoppositions.json", game:GetService("HttpService"):JSONEncode(ex))
			end

			pcall(function()
				OPsData = game:GetService("HttpService"):JSONDecode(readfile("/m1keincorporated/MOoppositions.json"))
			end)

			notify:Label("go to your executors folder to add ops")
			notify:Label("Executor/workspace/m1keincorporated/MOoppositions.json")

			notify:Toggle("Notify when OPs join", false, function(Value)
				OPSNotifier = Value

				OPsData = game:GetService("HttpService"):JSONDecode(readfile("/m1keincorporated/MOoppositions.json"))

				for i, v in pairs(game.Players:GetPlayers()) do
					if table.find(OPsData, tostring(v.UserId)) then
						webhook(
							"Opposition Detected",
							"DisplayName: "
								.. v.DisplayName
								.. "\nUsername: "
								.. v.Name
								.. "\nUserId: "
								.. tostring(v.UserId)
						)
					end
				end

				while OPSNotifier and task.wait() do
					OPsData = game:GetService("HttpService")
						:JSONDecode(readfile("/m1keincorporated/MOoppositions.json"))
				end
			end)
		end
	end)

	notify:Toggle("Notify When Done Sleeping(0%)", false, function(Value)
		SleepNotifier = Value

		while task.wait() and SleepNotifier do
			if IsSleeping() then
				local Fatigue = tonumber(
					game.Players.LocalPlayer.PlayerGui.MainGui.Utility.BodyFatigue.Text:split(" ")[3]:split("%")[1]
				)

				if Fatigue <= 0 then
					webhook("Sleep Notifier", "You're done sleeping! GET YO ASS UP!!!")
					task.wait(60)
				end
			end
		end
	end)

	notify:Toggle("Notify & Stop when No Food", false, function(Value)
		NoFoodNotify = Value
	end)

	notify:Toggle("Log when No Food", false, function(Value)
		LogOnNoFood = Value
	end)

	local dataTable = {
		discId = "",
		webhookUrl = "",
	}

	pcall(function()
		if isfile("/m1keincorporated/Mighty_Omega.json") then
			local data = game:GetService("HttpService"):JSONDecode(readfile("/m1keincorporated/Mighty_Omega.json"))

			dataTable["discId"] = data["discId"]
			dataTable["webhookUrl"] = data["webhookUrl"]
		else
			local data = game:GetService("HttpService"):JSONEncode(dataTable)
			writefile("/m1keincorporated/Mighty_Omega.json", data)
		end
	end)

	local test = notify:Textbox("Webhook Url", function(txt)
		webhookUrl = txt
		dataTable["webhookUrl"] = webhookUrl
		local data = game:GetService("HttpService"):JSONEncode(dataTable)
		if writefile then
			writefile("/m1keincorporated/Mighty_Omega.json", data)
		end
	end)
	if dataTable["webhookUrl"] ~= "" then
		webhookUrl = dataTable["webhookUrl"]
		test:SetText(dataTable["webhookUrl"])
	end

	local test2 = notify:Textbox("Discord User Id", function(txt)
		if tonumber(txt) == nil then
			ping = "@everyone"
		else
			ping = "<@" .. txt .. ">"
			dataTable["discId"] = txt
			local data = game:GetService("HttpService"):JSONEncode(dataTable)
			if writefile then
				writefile("/m1keincorporated/Mighty_Omega.json", data)
			end
		end
	end)
	if dataTable["discId"] ~= "" then
		ping = "<@" .. dataTable["discId"] .. ">"
		test2:SetText(dataTable["discId"])
	end

	notify:Button("Test Webhook", function()
		webhook("Webhook Test", "<3")
	end)

	pcall(function()
		autocook:Toggle("Auto Cook", false, function(Value)
			acook = Value

			while task.wait() and acook do
				if CheckForFood() and acook then
					local Pan

					repeat
						task.wait()
					until GetPan() ~= nil or acook == false
					if acook == false then
						return
					end
					Pan = GetPan()

					game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
					task.wait()
					for i, v in pairs(recipes[SelectedFood]) do
						local tool = game.Players.LocalPlayer.Backpack:FindFirstChild(i)
						game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
						task.wait()
						if acook == false then
							return
						end
						local potdebounce = false
						repeat
							if Pan.Ingredients:FindFirstChild(i) ~= nil then
								if Pan.Ingredients:FindFirstChild(i).Value ~= v and not potdebounce then
									potdebounce = true
									VIM:SendKeyEvent(true, "E", false, game)
									task.wait(0.1)
									VIM:SendKeyEvent(false, "E", false, game)
									task.wait(0.1)
									potdebounce = false
								end
							elseif Pan.Ingredients:FindFirstChild(i) == nil and not potdebounce then
								potdebounce = true
								VIM:SendKeyEvent(true, "E", false, game)
								task.wait(0.1)
								VIM:SendKeyEvent(false, "E", false, game)
								task.wait(0.1)
								potdebounce = false
							end
						until Pan.Ingredients:FindFirstChild(i) ~= nil
								and Pan.Ingredients:FindFirstChild(i).Value == v
							or acook == false
						if acook == false then
							return
						end
						task.wait()
						game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
						task.wait(0.1)
					end
					task.wait()
					game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
					task.wait()
					if Pan ~= nil and acook then
						if acook == false then
							return
						end
						fireclickdetector(Pan.ClickDetector)
						task.wait()
						repeat
							task.wait()
						until Pan.FoodP.TimeG.TextLabel.Text == "!!" or acook == false
						if acook == false then
							return
						end
						fireclickdetector(Pan.ClickDetector)
						task.wait()
					end
				end
			end
		end)

		local foodlist = {}

		for i, v in pairs(recipes) do
			foodlist[#foodlist + 1] = i
		end

		autocook:Dropdown("Food to Auto Cook", foodlist, function(Value)
			SelectedFood = Value
		end)

		autocook:Label("(auto buy ingred until you get enough for 1 serving)")

		abn = autocook:Label("Auto Buying RN: None")

		absbox = autocook:Textbox("Servings (Integer)", function(txt)
			if tonumber(txt) ~= nil then
				if tonumber(txt) > 8 then
					absbox:SetText("8")
					TotalServings = 8
				elseif tonumber(txt) < 1 then
					absbox:SetText("1")
					TotalServings = 1
				else
					TotalServings = tonumber(txt)
				end
			else
				absbox:SetText("1")
			end
		end)
		absbox:SetText("1")

		autocook:Button("Auto Buy Ingredients to Serving Size", function()
			if SelectedFood ~= nil then
				for i, v in pairs(recipes[SelectedFood]) do
					local finished = false
					local start = tick()
					local timesbought = 0
					local required = v

					if TotalServings > 1 then
						required = v * TotalServings
						if required > 15 then
							required = 15
						end
					end
					abn:SetText("Auto Buying RN: " .. i .. "(" .. timesbought .. "/" .. required .. ")")

					local function GetPossibleBuyingRN()
						local ingreds = {}

						for _, child in pairs(workspace:GetChildren()) do
							if child.Name:find(i) then
								table.insert(ingreds, child)
							end
						end

						return ingreds
					end

					local ingredLocations = GetPossibleBuyingRN()

					repeat
						for _, child in pairs(ingredLocations) do
							local distance = (
								child.Head.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position
							).Magnitude

							if distance <= 5 then
								repeat
									fireclickdetector(child.ClickDetector)
									task.wait(0.1)
								until child.Name ~= "Purchased!"
								timesbought = timesbought + 1
								abn:SetText("Auto Buying RN: " .. i .. "(" .. timesbought .. "/" .. required .. ")")
								task.wait(0.5)
							end
							task.wait()
						end

						if game.Players.LocalPlayer.Backpack:FindFirstChild(i) then
							if
								timesbought >= required
								or game.Players.LocalPlayer.Backpack:FindFirstChild(i).Quantity.Value >= 15
							then
								finished = true
								break
							end
						elseif (tick() - start) >= 1200 then
							abn:SetText("Auto Buy Timed out!")
							return
						end
						task.wait()
					until finished == true
				end
				abn:SetText("Finished Buying Ingredients for " .. TotalServings .. " Serving(s)")
			end
		end)
	end)

	misc:Toggle("Auto Eat", false, function(Value)
		autoeat = Value
	end)

	misc:Slider("Eat at Hunger %", { min = 0, max = 100, def = 30 }, function(Value)
		EatAt = Value
	end)

	misc:Slider("Fill up to Hunger %", { min = 0, max = 100, def = 80 }, function(Value)
		FillUp = Value
	end)

	misc:Toggle("Dont Eat When In Combat", false, function(Value)
		stopAEinCombat = Value
	end)

	misc:Toggle("Auto Supplement", false, function(Value)
		autosupplement = Value
	end)

	misc:Dropdown("Supplement", { "BCAA", "Protein Shake", "Fat Burner", "Scalar" }, function(Value)
		selectedsupplement = Value
	end)

	misc:Toggle("Hold Click (Tools)", false, function(Value)
		holdclick = Value

		while task.wait() and holdclick do
			if UIS:IsMouseButtonPressed(Enum.UserInputType.MouseButton1) then
				while UIS:IsMouseButtonPressed(Enum.UserInputType.MouseButton1) and task.wait() do
					pcall(function()
						if UIS:IsMouseButtonPressed(Enum.UserInputType.MouseButton1) then
							game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool"):Activate()
						end
					end)
				end
			end
		end
	end)

	misc:Toggle("Auto Sprint (Combat)", false, function(Value)
		autosprintcombat = Value

		local actionscript = getsenv(game:GetService("Players").LocalPlayer.Backpack.LocalS)

		if autosprintcombat then
			began = game:GetService("UserInputService").InputBegan:Connect(function(input, chat)
				if chat then
					return
				end

				if input.KeyCode == Enum.KeyCode.W and holdingW == false and autosprintcombat then
					actionscript.runPrompt()
					holdingW = true
				end
			end)

			ended = game:GetService("UserInputService").InputEnded:Connect(function(input, chat)
				if chat then
					return
				end

				if input.KeyCode == Enum.KeyCode.W and holdingW == true and autosprintcombat then
					holdingW = false
				end
			end)
		else
			if began ~= nil and ended ~= nil then
				began:Disconnect()
				ended:Disconnect()
			end
		end
	end)

	misc:Toggle("Disable Trainings When InCombat", false, function(Value)
		StopInCombat = Value

		while task.wait() and StopInCombat do
			if game.Players.LocalPlayer.PlayerGui.MainGui.Utility.CombatTag.Visible then
				disableAllTraining()
				task.wait(2)
			end
		end
	end)

	misc:Toggle("Disable Trainings When Knocked", false, function(Value)
		StopKnocked = Value

		while task.wait() and StopKnocked do
			if game.Players.LocalPlayer.Character:FindFirstChild("Ragdolled").Value == true then
				disableAllTraining()
				task.wait(2)
			end
		end
	end)

	misc:Button("Serverhop to Lowest Server", function(Value)
		local Http = game:GetService("HttpService")
		local TPS = game:GetService("TeleportService")
		local Api = "https://games.roblox.com/v1/games/"

		local _place = game.PlaceId
		local _servers = Api .. _place .. "/servers/Public?sortOrder=Asc&limit=100"
		function ListServers(cursor)
			local Raw = game:HttpGet(_servers .. ((cursor and "&cursor=" .. cursor) or ""))
			return Http:JSONDecode(Raw)
		end

		local Server, Next
		repeat
			local Servers = ListServers(Next)
			Server = Servers.data[1]
			Next = Servers.nextPageCursor
		until Server

		TPS:TeleportToPlaceInstance(_place, Server.id, game.Players.LocalPlayer)
	end)

	misc:Toggle("Auto Buy Foods Nearby", false, function(Value)
		autobuyitem = Value

		if autobuyitem then
			local function GetClosestItem()
				local foodsnear = {}

				for i, v in pairs(ItemTable) do
					if
						(game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Head.Position).Magnitude
						<= v.ClickDetector.MaxActivationDistance
					then
						table.insert(foodsnear, v)
					end
				end

				return foodsnear
			end

			while autobuyitem and task.wait() do
				local foodstobuy = GetClosestItem()

				if autobuyitem and #GetClosestItem() > 0 then
					for i, v in pairs(foodstobuy) do
						if autobuyitem == false then
							return
						end
						fireclickdetector(v.ClickDetector)
						task.wait(0.15)
					end
				end
			end
		end
	end)

	misc:Toggle("Auto Panic", false, function(Value)
		autopanic = Value

		local function IsInCombat()
			local status

			local suc = pcall(function()
				if game.Players.LocalPlayer:FindFirstChild("PlayerGui") then
					if game.Players.LocalPlayer.PlayerGui:FindFirstChild("MainGui") then
						status = game.Players.LocalPlayer.PlayerGui.MainGui.Utility.CombatTag.Visible
					end
				end
			end)

			if not suc then
				status = nil
			end

			return status
		end

		while task.wait() and autopanic do
			if IsInCombat() == true and autopanic then
				disableAllTraining()
				game.Players.LocalPlayer.Character.Humanoid:UnequipTools()

				if macroruin then
					webhook("Auto Panic", CurrentGanker .. " activated Combat Sequence!")
				end

				task.wait(1)

				task.spawn(function()
					while task.wait(panicdelay) and autopanic do
						pcall(function()
							local chance = math.random(1, 4)
							if chance >= 2 then
								panicangle = panicangle * -1
							end

							game.Workspace.CurrentCamera.CFrame = game:GetService("Workspace").CurrentCamera.CFrame
								* CFrame.Angles(0, math.rad(panicangle), 0)
							panicangle = math.random(35, 90)
						end)
					end
				end)

				task.spawn(function()
					shared.AllowSprinting = false
					local function IsDraining()
						local lastStamVal = game.Players.LocalPlayer.Character.CurrentStamina.Value

						task.wait(0.5)
						if lastStamVal > game.Players.LocalPlayer.Character.CurrentStamina.Value then
							return true
						end
						return false
					end

					while task.wait(0.1) and autopanic do
						pcall(function()
							local actionscript = getsenv(game:GetService("Players").LocalPlayer.Backpack.LocalS)
							local StamPercent = (
								game.Players.LocalPlayer.Character.CurrentStamina.Value
								/ game.Players.LocalPlayer.Character.MaxStamina.Value
							) * 100
							local LowStam = ministam

							if isrunning == false and CurrentRegening == false and shared.AllowSprinting then
								actionscript.runPrompt()
								isrunning = true
								task.wait(1)
							elseif isrunning == true and shared.AllowSprinting then
								repeat
									StamPercent = (
										game.Players.LocalPlayer.Character.CurrentStamina.Value
										/ game.Players.LocalPlayer.Character.MaxStamina.Value
									) * 100
									task.wait()
								until CurrentRegening == true
									or StamPercent == 100
									or autopanic == false
									or shared.AllowSprinting == false
									or IsDraining() == false

								if
									StamPercent <= ministam
									or shared.AllowSprinting == false
									or autopanic == false
									or CurrentRegening == true
								then
									actionscript.stopSprint()
								end
								isrunning = false
							elseif isrunning == true and shared.AllowSprinting == false then
								actionscript.stopSprint()
								isrunning = false
							end
						end)
					end

					shared.AllowSprinting = false
				end)

				repeat
					task.wait()
					pcall(function()
						panicstamcheck()

						if game.Players.LocalPlayer.Character.Humanoid.MoveDirection == Vector3.new(0, 0, 0) then
							automacrosprint()
						else
							panicdash()
						end
					end)
				until IsInCombat() == false or autopanic == false
				shared.AllowSprinting = false
				if autopanic then
					if macroruin then
						webhook("Auto Panic", "Logged Safely!")
						task.wait()
					end

					game:shutdown()
					return
				end
			end
		end
	end)

	misc:Toggle("Player ESP", false, function(Value)
		ESP = Value

		if ESP then
			for i, v in pairs(game.Players:GetPlayers()) do
				esp(v)
			end

			local plrconnection
			plrconnection = game.Players.PlayerAdded:Connect(function(plr)
				if ESP == false then
					plrconnection:Disconnect()
					return
				end
				esp(plr)
			end)
		end
	end)

	misc:Slider("ESP Distance", { min = 0, def = 10000, max = 10000 }, function(Value)
		ESPDistance = Value
	end)

	misc:Toggle("Auto Starve", false, function(Value)
		autostarve = Value

		while task.wait() and autostarve do
			local actionscript = getsenv(game:GetService("Players").LocalPlayer.Backpack.LocalS)
			local StamPercent = (
				game.Players.LocalPlayer.Character.CurrentStamina.Value
				/ game.Players.LocalPlayer.Character.MaxStamina.Value
			) * 100

			if
				StamPercent >= staminabelowpercent
				and ASisrunning == false
				and game.Players.LocalPlayer.Character:FindFirstChild("Ragdolled").Value == false
			then
				actionscript.runPrompt()
				ASisrunning = true
			elseif StamPercent <= staminabelowpercent and ASisrunning then
				task.wait(0.1)
				ASisrunning = false
			elseif StamPercent == 100 then
				task.wait(0.5)
				if StamPercent == 100 then
					ASisrunning = false
				end
			end
		end
	end)

	misc:Slider("Keep Stamina Below %", { min = 0, def = 20, max = 100 }, function(Value)
		staminabelowpercent = Value
	end)

	misc:Toggle("Auto Disable Macros", false, function(Value)
		AutoStop = Value
	end)

	misc:Slider("Fatigue % to Stop", { min = 0, max = 100, def = FatigueToStop }, function(Value)
		FatigueToStop = Value
	end)

	misc:Label("Note: consider auto sleep as risky |g Do Nothing is default")

	misc:Dropdown(
		"When Macro Stopped",
		{ "Do Nothing", "Log/Leave game", "Auto Sleep & Log", "Auto Sleep & Continue" },
		function(Value)
			if Value == "Do Nothing" then
				LogOnFatigued = false
				autosleepRes = false
				autosleepLog = false
			elseif Value == "Log/Leave game" then
				LogOnFatigued = true
				autosleepRes = false
				autosleepLog = false
			elseif Value == "Auto Sleep & Log" then
				LogOnFatigued = false
				autosleepRes = false
				autosleepLog = true
			elseif Value == "Auto Sleep & Continue" then
				LogOnFatigued = false
				autosleepRes = true
				autosleepLog = false
			else
				LogOnFatigued = false
				autosleepRes = false
				autosleepLog = false
			end
		end
	)

    if hookmetamethod then
        Backup = hookmetamethod(
            Mouse,
            "__index",
            newcclosure(function(self, idx)
                if idx == "Target" and broomjobactive and broomjobpart ~= nil and autojobs then
                    return broomjobpart
                end

                return Backup(self, idx)
            end)
        )
    end

	trainingtoggles[#trainingtoggles + 1] = risky:Toggle("Auto Jobs", false, function(Value)
		autojobs = Value

		if autojobs == false then
			_G.OngoingPath = false
		end

		local og = Vector3.new(2.6999998092651367, 45.04999923706055, 222.13999938964844)
		local new = Vector3.new(2.7, 45.05, 73.14)
		local AUTOJOBBARRIERS = {}
		AUTOJOBBARRIERS[1] = Instance.new("Part", workspace)
		AUTOJOBBARRIERS[1].Position = Vector3.new(-252.3034210205078, 54.62002182006836, -584.091064453125)
		AUTOJOBBARRIERS[1].Orientation = Vector3.new(0, 0, 0)
		AUTOJOBBARRIERS[1].Size = Vector3.new(28.020000457763672, 21.84000015258789, 3.559999942779541)
		AUTOJOBBARRIERS[1].Anchored = true
		AUTOJOBBARRIERS[1].CanCollide = true
		AUTOJOBBARRIERS[1].Transparency = 1
		AUTOJOBBARRIERS[2] = Instance.new("Part", workspace)
		AUTOJOBBARRIERS[2].Position = Vector3.new(287.8071594238281, 47.193782806396484, -902.21875)
		AUTOJOBBARRIERS[2].Orientation = Vector3.new(0, 0, 0)
		AUTOJOBBARRIERS[2].Size = Vector3.new(2.6999998092651367, 45.04999923706055, 222.13999938964844)
		AUTOJOBBARRIERS[2].Anchored = true
		AUTOJOBBARRIERS[2].CanCollide = true
		AUTOJOBBARRIERS[2].Transparency = 1
		AUTOJOBBARRIERS[4] = Instance.new("Part", workspace)
		AUTOJOBBARRIERS[4].Position = Vector3.new(-285.6453552246094, 48.400028228759766, -564.8450927734375)
		AUTOJOBBARRIERS[4].Orientation = Vector3.new(0, -30, 0)
		AUTOJOBBARRIERS[4].Size = Vector3.new(6.940000534057617, 10.199999809265137, 7.690000057220459)
		AUTOJOBBARRIERS[4].Anchored = true
		AUTOJOBBARRIERS[4].CanCollide = true
		AUTOJOBBARRIERS[4].Transparency = 1
		AUTOJOBBARRIERS[5] = Instance.new("Part", workspace)
		AUTOJOBBARRIERS[5].Position = Vector3.new(-306.9322204589844, 51.81392288208008, -615.2486572265625)
		AUTOJOBBARRIERS[5].Orientation = Vector3.new(0, 90, 0)
		AUTOJOBBARRIERS[5].Size = Vector3.new(34.63999938964844, 15.630000114440918, 5.739999294281006)
		AUTOJOBBARRIERS[5].Anchored = true
		AUTOJOBBARRIERS[5].CanCollide = true
		AUTOJOBBARRIERS[5].Transparency = 1
		AUTOJOBBARRIERS[6] = Instance.new("Part", workspace)
		AUTOJOBBARRIERS[6].Position = Vector3.new(-276.83843994140625, 51.203548431396484, -580.1591796875)
		AUTOJOBBARRIERS[6].Orientation = Vector3.new(0, 0, 0)
		AUTOJOBBARRIERS[6].Size = Vector3.new(2.9099998474121094, 14.970000267028809, 2.179999828338623)
		AUTOJOBBARRIERS[6].Anchored = true
		AUTOJOBBARRIERS[6].CanCollide = true
		AUTOJOBBARRIERS[6].Transparency = 1
		AUTOJOBBARRIERS[8] = Instance.new("Part", workspace)
		AUTOJOBBARRIERS[8].Position = Vector3.new(314.088134765625, 47.193782806396484, -790.2724609375)
		AUTOJOBBARRIERS[8].Orientation = Vector3.new(0, -89, 0)
		AUTOJOBBARRIERS[8].Size = Vector3.new(2.6999998092651367, 45.04999923706055, 55.47999954223633)
		AUTOJOBBARRIERS[8].Anchored = true
		AUTOJOBBARRIERS[8].CanCollide = true
		AUTOJOBBARRIERS[8].Transparency = 1
		AUTOJOBBARRIERS[9] = Instance.new("Part", workspace)
		AUTOJOBBARRIERS[9].Position = Vector3.new(287.8071594238281, 47.193782806396484, -671.853759765625)
		AUTOJOBBARRIERS[9].Orientation = Vector3.new(0, 0, 0)
		AUTOJOBBARRIERS[9].Size = Vector3.new(2.6999998092651367, 45.04999923706055, 218.58999633789062)
		AUTOJOBBARRIERS[9].Anchored = true
		AUTOJOBBARRIERS[9].CanCollide = true
		AUTOJOBBARRIERS[9].Transparency = 1
		AUTOJOBBARRIERS[10] = Instance.new("Part", workspace)
		AUTOJOBBARRIERS[10].Position = Vector3.new(314.088134765625, 47.193782806396484, -779.8624877929688)
		AUTOJOBBARRIERS[10].Orientation = Vector3.new(0, -89, 0)
		AUTOJOBBARRIERS[10].Size = Vector3.new(2.6999998092651367, 45.04999923706055, 55.47999954223633)
		AUTOJOBBARRIERS[10].Anchored = true
		AUTOJOBBARRIERS[10].CanCollide = true
		AUTOJOBBARRIERS[10].Transparency = 1
		AUTOJOBBARRIERS[11] = Instance.new("Part", workspace)
		AUTOJOBBARRIERS[11].Position = Vector3.new(-278.10223388671875, 51.81392288208008, -600.8236694335938)
		AUTOJOBBARRIERS[11].Orientation = Vector3.new(0, 0, 0)
		AUTOJOBBARRIERS[11].Size = Vector3.new(63.4900016784668, 15.630000114440918, 5.739999294281006)
		AUTOJOBBARRIERS[11].Anchored = true
		AUTOJOBBARRIERS[11].CanCollide = true
		AUTOJOBBARRIERS[11].Transparency = 1
		AUTOJOBBARRIERS[98] = Instance.new("Part", workspace)
		AUTOJOBBARRIERS[98].Position = Vector3.new(-1041.891, 59.14, -327.758)
		AUTOJOBBARRIERS[98].Orientation = Vector3.new(0, 0, 0)
		AUTOJOBBARRIERS[98].Size = Vector3.new(59, 32, 186)
		AUTOJOBBARRIERS[98].Anchored = true
		AUTOJOBBARRIERS[98].CanCollide = true
		AUTOJOBBARRIERS[98].Transparency = 1
		AUTOJOBBARRIERS[99] = Instance.new("Part", workspace)
		AUTOJOBBARRIERS[99].Position = Vector3.new(346.556, 25.2, -784.352)
		AUTOJOBBARRIERS[99].Orientation = Vector3.new(0, 90, 0)
		AUTOJOBBARRIERS[99].Size = Vector3.new(7, 1, 4)
		AUTOJOBBARRIERS[99].Anchored = true
		AUTOJOBBARRIERS[99].CanCollide = true
		AUTOJOBBARRIERS[99].Transparency = 1

		if autojobs then
			task.spawn(function()
				shared.AllowSprinting = false

				while task.wait(0.1) and autojobs do
					pcall(function()
						local actionscript = getsenv(game:GetService("Players").LocalPlayer.Backpack.LocalS)
						local StamPercent = (
							game.Players.LocalPlayer.Character.CurrentStamina.Value
							/ game.Players.LocalPlayer.Character.MaxStamina.Value
						) * 100
						local LowStam = ministam

						if isrunning == false and StamPercent >= 100 and shared.AllowSprinting then
							actionscript.runPrompt()
							isrunning = true
							task.wait(1)
						elseif isrunning == true and shared.AllowSprinting then
							repeat
								StamPercent = (
									game.Players.LocalPlayer.Character.CurrentStamina.Value
									/ game.Players.LocalPlayer.Character.MaxStamina.Value
								) * 100
								task.wait()
							until StamPercent <= LowStam
								or StamPercent == 100
								or autojobs == false
								or shared.AllowSprinting == false

							if StamPercent <= ministam or shared.AllowSprinting == false or autojobs == false then
								actionscript.stopSprint()
							end
							isrunning = false
						elseif isrunning == true and shared.AllowSprinting == false then
							actionscript.stopSprint()
							isrunning = false
						end
					end)
				end

				shared.AllowSprinting = false
			end)

			local hum = char.Humanoid
			local PFS = game:GetService("PathfindingService")
			local HRP = char.HumanoidRootPart
			local pathStatus = Enum.PathStatus

			_G.currentPoint = nil
			_G.OngoingPath = false

			local function createPath(point)
				local currentPath = PFS:FindPathAsync(HRP.Position, point)
				local pathExists = false

				if currentPath.Status == pathStatus.Success then
					pathExists = true
					_G.OngoingPath = true

					spawn(function()
						while pathExists and task.wait() and _G.currentPoint ~= nil and _G.OngoingPath and autojobs do
							local x, y = pcall(function()
								if (HRP.Position - _G.currentPoint).Magnitude > 5 then
									hum.WalkToPoint = _G.currentPoint
								end
							end)
							if not x then
								warn(y)
							end
						end
					end)

					local lastbroken = false
					local antisusdebounce = false
					local alreadychanced = false
					local oldhumanpos, lastupdate = nil, nil

					for i, v in pairs(currentPath:GetWaypoints()) do
						if _G.OngoingPath ~= true then
							return
						end

						if v.Action == Enum.PathWaypointAction.Jump then
							hum:ChangeState(Enum.HumanoidStateType.Jumping)
						end

						local part = Instance.new("Part")
						part.Shape = "Ball"
						part.Material = "Neon"
						part.Size = Vector3.new(0.6, 0.6, 0.6)
						part.Position = v.Position + Vector3.new(0, 6, 0)
						part.Anchored = true
						part.CanCollide = false
						part.Parent = game.Workspace

						local oldpos = HRP.Position
						local updatedelay = false

						local function percentchance(x)
							if 100 * math.random() < x then
								return true
							else
								return false
							end
						end

						if lastupdate == nil then
							lastupdate = tick()
						else
							if (tick() - lastupdate) >= 2 then
								lastupdate = tick()
								oldhumawnpos = HRP.Position
							end
						end

						repeat
							task.wait()
							if autojobs == false then
								game.Debris:AddItem(part, 0.01)
								return
							end
							_G.currentPoint = v.Position

							if percentchance(3) and not antisusdebounce and alreadychanced == false then
								task.spawn(function()
									antisusdebounce = true
									shared.AllowSprinting = false
									task.wait(math.random(1, 3))
									if game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("JobGUI") then
										shared.AllowSprinting = true
									end
									antisusdebounce = false
								end)
							end
							alreadychanced = true

							if
								(HRP.Position - v.Position).Magnitude > 5
								and (HRP.Position - part.Position).Magnitude > 4
							then
								if oldpos ~= HRP.Position and not lastbroken and not updatedelay then
									task.spawn(function()
										updatedelay = true
										oldpos = HRP.Position
										task.delay(1, function()
											updatedelay = false
										end)
									end)
								elseif oldpos == HRP.Position and not lastbroken then
									oldpos = HRP.Position
									lastbroken = true
									break
								elseif oldpos == HRP.Position and lastbroken then
									task.spawn(function()
										task.wait(1)
										if oldpos == HRP.Position then
											hum:ChangeState(Enum.HumanoidStateType.Jumping)
											task.wait(1)
										end

										oldpos = HRP.Position
										lastbroken = false
									end)
								end
							elseif oldhumanpos ~= nil then
								if (HRP.Position - oldhumanpos).Magnitude <= 0.05 then
									hum:ChangeState(Enum.HumanoidStateType.Jumping)
									task.wait(1)
								end
							end
						until (HRP.Position - v.Position).Magnitude < PointRangeTilNext
							or (HRP.Position - part.Position).Magnitude < 5
							or _G.OngoingPath ~= true
							or autojobs == false
						game.Debris:AddItem(part, 0.01)
					end

					_G.OngoingPath = false
				elseif currentPath.Status ~= pathStatus.Success or _G.currentPoint == nil then
					pathExists = false
				end
			end

			local JobStuff = {
				["Convenience"] = {
					JB = workspace.JobBoardModel,
					JBget = Vector3.new(-315.9144592285156, 47.29416275024414, -589.2377319335938),
				},
				["Japanese1"] = {
					JB = workspace.JobBoardModel1,
					JBget = Vector3.new(-1167, 47, -223),
				},
			}

			while task.wait() and autojobs do
				if SelectedJob == nil or JobBoard == nil then
					repeat
						task.wait()
					until SelectedJob ~= nil and JobBoard ~= nil or autojobs == false
				end
				if game.Players.LocalPlayer.Character.Ragdolled.Value then
					disableAllTraining()
					if macroruin then
						webhook("Macro Notifier", "Knocked/Ragdolled while doing Auto Job. Auto Job turned off")
					end
					return
				end
				shared.AllowSprinting = false
				local JB = JobStuff[JobBoard].JB
				local JBget = JobStuff[JobBoard].JBget
				local jbdistance = (HRP.Position - JB.Board.Position).Magnitude
				local jobui = game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("JobGUI")
				local cleared = false

				if jobui == nil then
					if jbdistance <= 9 then
						maintenancechecks()
						repeat
							fireclickdetector(JB.ClickDetector)
							task.wait()
						until game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("JobGUI")
					end
				elseif jobui then
					if
						jobui.Frame.Title.Text:find("Restock") and SelectedJob == "Restock"
						or SelectedJob == "All" and jobui.Frame.Title.Text:find("Restock")
					then
						cleared = true
						AUTOJOBBARRIERS[2].Size = og
					elseif
						jobui.Frame.Title.Text:find("Cleaning") and SelectedJob == "Cleaning"
						or SelectedJob == "All" and jobui.Frame.Title.Text:find("Cleaning")
					then
						if JobBoard == "Convenience" then
							WalkTo(Vector3.new(-370, 47, -582))
						end

						broomjobactive = true

						repeat
							task.wait()

							local annoyingpart = game:GetService("Workspace").Jobs.BroomClean[JobBoard].Part9
							if annoyingpart.Transparency ~= 1 then
								broomjobpart = annoyingpart
								if JobBoard == "Convenience" then
									WalkTo(Vector3.new(-347, 47, -577))
								else
									WalkTo(annoyingpart.Position)
								end
								task.wait(0.1)
								if game.Players.LocalPlayer.Backpack:FindFirstChild("Broom") then
									game.Players.LocalPlayer.Character.Humanoid:EquipTool(
										game.Players.LocalPlayer.Backpack:FindFirstChild("Broom")
									)
									task.wait(0.1)
								end

								VIM:SendMouseButtonEvent(0, 500, 0, true, game, 1)
								task.wait(0.1)
								repeat
									task.wait()
								until annoyingpart.Transparency == 1
							end

							local v = BestBroomSpot()

							if v ~= nil then
								broomjobpart = v
								shared.currentPoint = nil
								WalkTo(v.Position)
								task.wait(0.1)
								if game.Players.LocalPlayer.Backpack:FindFirstChild("Broom") then
									game.Players.LocalPlayer.Character.Humanoid:EquipTool(
										game.Players.LocalPlayer.Backpack:FindFirstChild("Broom")
									)
									task.wait(0.1)
								end

								VIM:SendMouseButtonEvent(0, 500, 0, true, game, 1)
								task.wait(0.1)
								repeat
									task.wait()
								until v.Transparency == 1
							end

						until game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("JobGUI") == nil
							or autojobs == false

						broomjobactive = false

						if JobBoard == "Convenience" then
							game.Players.LocalPlayer.Character.Humanoid:MoveTo(Vector3.new(-370, 47, -582))
							game.Players.LocalPlayer.Character.Humanoid.MoveToFinished:Wait()
						end
						task.spawn(function()
							createPath(JBget)
						end)
					else
						SimulateClick(jobui.Frame.Quit, "Function")
					end
				end

				if cleared then
					local progress = tonumber(jobui.Frame.Progress.Text:split("/")[1]:split(":")[2])

					if progress == 0 then
						AUTOJOBBARRIERS[2].Size = og
						task.delay(math.random(1, 3), function()
							shared.AllowSprinting = true
						end)
						createPath(workspace.Jobs.SupplyDelivery[JobBoard].Part1.Position)
						shared.AllowSprinting = false
					elseif progress == 1 then
						AUTOJOBBARRIERS[2].Size = new
						task.delay(math.random(1, 3), function()
							shared.AllowSprinting = true
						end)
						createPath(workspace.Jobs.SupplyDelivery[JobBoard].Part2.Position)
						shared.AllowSprinting = false

						task.delay(math.random(1, 3), function()
							shared.AllowSprinting = true
						end)
						createPath(JBget)
						shared.AllowSprinting = false
					end
				end
			end
		end

		if autojobs == false then
			for i, v in pairs(AUTOJOBBARRIERS) do
				game.Debris:AddItem(v, 0.01)
			end
		end
	end)

	risky:Dropdown("Job Selector", { "Cleaning", "Restock", "All" }, function(Value)
		SelectedJob = Value
	end)

	risky:Dropdown("Job Board", { "Convenience", "Japanese1" }, function(Value)
		JobBoard = Value
	end)

	risky:Label("-- if supply job stop randomly use Point mag below -- ")

	risky:Slider("Point Magnitude Til Next", { def = PointRangeTilNext, max = 30, min = 0 }, function(Value)
		PointRangeTilNext = Value
	end)

	trainingtoggles[#trainingtoggles + 1] = risky:Toggle("Auto Roadwork", false, function(Value)
		Roadwork = Value

		if Roadwork then
			task.spawn(function()
				while task.wait(0.1) and Roadwork do
					local actionscript = getsenv(game:GetService("Players").LocalPlayer.Backpack.LocalS)
					local StamPercent = (
						game.Players.LocalPlayer.Character.CurrentStamina.Value
						/ game.Players.LocalPlayer.Character.MaxStamina.Value
					) * 100
					local LowStam = ministam

					if RWCanSprint and Roadwork then
						if isrunning == false and StamPercent >= 100 and RWCanSprint then
							actionscript.runPrompt()
							isrunning = true
							task.wait(1)
						elseif isrunning == true then
							repeat
								StamPercent = (
									game.Players.LocalPlayer.Character.CurrentStamina.Value
									/ game.Players.LocalPlayer.Character.MaxStamina.Value
								) * 100
								task.wait()
							until StamPercent <= LowStam
								or StamPercent == 100
								or Roadwork == false
								or RWCanSprint == false

							if StamPercent < 100 or autotrain == false or RWCanSprint == false then
								actionscript.stopSprint()
								maintenancechecks()
							end
							isrunning = false
						end
					end
				end
			end)

			while task.wait() and Roadwork do
				pcall(function()
					local MyStorage = workspace:FindFirstChild(game.Players.LocalPlayer.Name .. " Storage")
					local RWBuy = GetClosestRoadwork()

					if
						game.Players.LocalPlayer.Backpack:FindFirstChild("Roadwork") == nil
						and game.Players.LocalPlayer.Character:FindFirstChild("Roadwork") == nil
					then
						if RWBuy ~= nil then
							RWCanSprint = true
							createPath(RWBuy.Head.Position)
							RWCanSprint = false
							task.wait(0.1)
							fireclickdetector(RWBuy.ClickDetector)
							task.wait(0.1)
						end
					else
						if #MyStorage:GetChildren() < 1 then
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Roadwork") then
								game.Players.LocalPlayer.Character.Humanoid:EquipTool(
									game.Players.LocalPlayer.Backpack:FindFirstChild("Roadwork")
								)
								task.wait(0.1)
							end
							game.Players.LocalPlayer.Character:FindFirstChild("Roadwork"):Activate()
						else
							print("WALK TO", MyStorage:GetChildren()[1])
							RWCanSprint = true
							createPath(MyStorage:GetChildren()[1].Position)
						end
					end
				end)
			end
		end
	end)

	risky:Label("-- if roadwork stop randomly use cp mag below -- ")

	risky:Slider("CP Magnitude Til Next", { def = CPRangeTilNext, max = 30, min = 0 }, function(Value)
		CPanRangeTilNext = Value
	end)

	local function ScanTable(table, string)
		for i, v in pairs(table) do
			if v == string then
				return i
			end
		end

		return nil
	end

	local function AztupElements()
		local LivingThings
		LivingThings = workspace:FindFirstChild("Live") or Instance.new("Model")
		local Events = game.ReplicatedStorage.Events
		getgenv().runningSpeed = 500
		local ATBdistance = 5 --1-10
		local ATBrange = 100 -- 0-100
		local ATBloop = nil
		local angleOffSet = CFrame.Angles(math.rad(-90), 0, 0)

		local function UtilityFind(t, c)
			for i, v in next, t do
				if c(v, i) then
					return v, i
				end
			end

			return nil
		end

		local function parseKey(str)
			return UtilityFind({ str:byte(1, 9999) }, function(v)
				return v > 128
			end)
		end

		local function getKey(script)
			if not script:IsA("LocalScript") then
				error("Expected a localscript got " .. script.ClassName)
			end
			local key

			local ran, env = pcall(getsenv, script)
			if not ran then
				return
			end

			for _, v in next, env do
				if typeof(v) == "function" then
					for _, k in next, getupvalues(v) do
						if typeof(k) == "string" and parseKey(k) then
							key = k
							break
						end
					end
				end
			end

			if key then
				return key
			end

			for _, v in next, script.Parent:GetDescendants() do
				local con = string.match(v.ClassName, "Button") and getconnections(v.MouseButton1Click)[1]
					or getconnections(v.Changed)[1]
				if con and con.Function then
					for _, k in next, getupvalues(v) do
						if typeof(k) == "string" and parseKey(k) then
							key = k
							break
						end
					end

					if key then
						break
					end
				end
			end
			return key
		end

		getgenv().getKey = getKey

		local function getMobInRange(range)
			local plr = game.Players.LocalPlayer
			local char = plr.Character
			local inRange
			local closest = range
			for i, v in next, LivingThings:GetChildren() do
				if v ~= char then
					if not game.Players:FindFirstChild(v.Name) then
						if (v:FindFirstChild("HumanoidRootPart")) and char:FindFirstChild("HumanoidRootPart") then
							if (v.HumanoidRootPart.Position - char.HumanoidRootPart.Position).magnitude <= closest then
								inRange = v
								closest = (v.HumanoidRootPart.Position - char.HumanoidRootPart.Position).magnitude
								break
							end
						end
					end
				end
			end

			return inRange
		end

		local plr = game.Players.LocalPlayer
		local char = plr.Character
		local getupvalue = debug.getupvalue
		local getupvalues = debug.getupvalues
		local getconstant = debug.getconstant
		local getconstants = debug.getconstants

		local parryAnims = {
			["rbxassetid://7009320896"] = { ["Guardbreak"] = false },
			["rbxassetid://5087462384"] = { ["Guardbreak"] = false },
			["rbxassetid://6501739912"] = { ["Guardbreak"] = false },
			["rbxassetid://6704457409"] = { ["Guardbreak"] = false },
			["rbxassetid://6718814119"] = { ["Guardbreak"] = false },
			["rbxassetid://5029356929"] = { ["Guardbreak"] = false },
			["rbxassetid://6930761828"] = { ["Guardbreak"] = false },
			["rbxassetid://5087464114"] = { ["Guardbreak"] = false },
			["rbxassetid://5029359784"] = { ["Guardbreak"] = false },
			["rbxassetid://7876039532"] = { ["Guardbreak"] = false },
			["rbxassetid://5810497127"] = { ["Guardbreak"] = false },
			["rbxassetid://7891093418"] = { ["Guardbreak"] = false },
			["rbxassetid://6930758587"] = { ["Guardbreak"] = false },
			["rbxassetid://5110868660"] = { ["Guardbreak"] = false },
			["rbxassetid://7877241063"] = { ["Guardbreak"] = false },
			["rbxassetid://6550835152"] = { ["Guardbreak"] = false },
			["rbxassetid://6604546413"] = { ["Guardbreak"] = false },
			["rbxassetid://6875783564"] = { ["Guardbreak"] = false },
			["rbxassetid://5052660577"] = { ["Guardbreak"] = false },
			["rbxassetid://7877246443"] = { ["Guardbreak"] = false },
			["rbxassetid://8594975706"] = { ["Guardbreak"] = false },
			["rbxassetid://5865529031"] = { ["Guardbreak"] = false },
			["rbxassetid://5116608619"] = { ["Guardbreak"] = false },
			["rbxassetid://5110454001"] = { ["Guardbreak"] = false },
			["rbxassetid://5092035643"] = { ["Guardbreak"] = false },
			["rbxassetid://5869781872"] = { ["Guardbreak"] = false },
			["rbxassetid://5110500012"] = { ["Guardbreak"] = false },
			["rbxassetid://5645707634"] = { ["Guardbreak"] = false },
			["rbxassetid://6718812539"] = { ["Guardbreak"] = false },
			["rbxassetid://6194195462"] = { ["Guardbreak"] = false },
			["rbxassetid://5110724393"] = { ["Guardbreak"] = false },
			["rbxassetid://6930759930"] = { ["Guardbreak"] = false },
			["rbxassetid://5883810295"] = { ["Guardbreak"] = false },
			["rbxassetid://4918348016"] = { ["Guardbreak"] = false },
			["rbxassetid://5092037778"] = { ["Guardbreak"] = false },
			["rbxassetid://5052449595"] = { ["Guardbreak"] = false },
			["rbxassetid://5087459369"] = { ["Guardbreak"] = false },
			["rbxassetid://5873100725"] = { ["Guardbreak"] = false },
			["rbxassetid://6573164932"] = { ["Guardbreak"] = false },
			["rbxassetid://6566644368"] = { ["Guardbreak"] = false },
			["rbxassetid://7791575394"] = { ["Guardbreak"] = false },
			["rbxassetid://6360102363"] = { ["Guardbreak"] = false },
			["rbxassetid://6719137742"] = { ["Guardbreak"] = false },
			["rbxassetid://5052435233"] = { ["Guardbreak"] = false },
			["rbxassetid://7876328758"] = { ["Guardbreak"] = false },
			["rbxassetid://6875731587"] = { ["Guardbreak"] = false },
			["rbxassetid://5126044328"] = { ["Guardbreak"] = false },
			["rbxassetid://7887536058"] = { ["Guardbreak"] = false },
			["rbxassetid://6674659296"] = { ["Guardbreak"] = false },
			["rbxassetid://7130763680"] = { ["Guardbreak"] = false },
			["rbxassetid://5092042225"] = { ["Guardbreak"] = false },
			["rbxassetid://5110453274"] = { ["Guardbreak"] = false },
			["rbxassetid://6360098898"] = { ["Guardbreak"] = false },
			["rbxassetid://6704318501"] = { ["Guardbreak"] = false },
			["rbxassetid://5870608112"] = { ["Guardbreak"] = false },
			["rbxassetid://5126071335"] = { ["Guardbreak"] = false },
			["rbxassetid://6257267175"] = { ["Guardbreak"] = false },
			["rbxassetid://10234589242"] = { ["Guardbreak"] = false }, --Tiger Hunt
			["rbxassetid://10234603041"] = { ["Guardbreak"] = true }, --Snake Bite
			["rbxassetid://10261951458"] = { ["Guardbreak"] = false }, --Dragon Claw
			["rbxassetid://5594891491"] = { ["Guardbreak"] = false }, --Bear Hug
			["rbxassetid://7819569583"] = { ["Guardbreak"] = false }, --BlastCore
			["rbxassetid://4901795168"] = { ["Guardbreak"] = true }, --brawl GB
			["rbxassetid://4973374984"] = { ["Guardbreak"] = true }, --Thai GB
			["rbxassetid://5016575571"] = { ["Guardbreak"] = true }, --Karate gb
			["rbxassetid://6169229434"] = { ["Guardbreak"] = true }, --Wrestling GB
			["rbxassetid://5016611308"] = { ["Guardbreak"] = true }, --Sumo GB
			["rbxassetid://6538829055"] = { ["Guardbreak"] = true }, --Taek GB
			["rbxassetid://6585959296"] = { ["Guardbreak"] = true }, --Raishin GB
			["rbxassetid://6194191510"] = { ["Guardbreak"] = true }, --Kure GB
			["rbxassetid://4918356164"] = { ["Guardbreak"] = true }, --Boxing GB
			["rbxassetid://6169361647"] = { ["Guardbreak"] = true }, --Karate GB
		}

		local guardBreakTable = {
			["Corkscrew"] = true,
			["Blast Core"] = true,
			["Flying Knee"] = true,
			["Axe Kick"] = true,
			["Tiger Bite"] = true,
			["Reverse Heel"] = true,
			["Solid Strike"] = true,
			["Jolt Hook"] = true,
			["Flying Side Kick"] = true,
			["Sumo Throw"] = true,
			["Bear Hug"] = true,
			["Shoulder Bash"] = true,
			["Forearm Smash"] = true,
			["Suplex"] = true,
			["Elbow Drop"] = 0.1,
			["Body Slam"] = true,
			["Eye Slice"] = true,
		}

		local function getStyle()
			if plr:FindFirstChild("Backpack") then
				return
			end
			if plr.Backpack:FindFirstChild("Style") then
				return plr.Backpack:FindFirstChild("Style").Parent
			elseif char:FindFirstChild("Style") then
				return char:FindFirstChild("Style").Parent
			end
			return nil
		end

		local function blockAttack()
			local key = getKey(plr.Backpack.LocalS)
			if not key then
				return
			end

			plr.Backpack.Action:FireServer(key, "Block", { true })
		end

		local function unblockAttack()
			local key = getKey(plr.Backpack.LocalS)
			if not key then
				return
			end

			plr.Backpack.Action:FireServer(key, "Block", { false })
		end

		local function guardBreak()
			local key = getKey(plr.Backpack.LocalS)
			if not key then
				return
			end

			plr.Backpack.Action:FireServer(key, "GuardBreak", { true })
		end

		getgenv().autoBlockconnections = {}

		local function autoParry(v)
			local plr = game.Players.LocalPlayer
			local char = plr.Character
			if v == char then
				return
			end

			local hrp = v:WaitForChild("HumanoidRootPart", 10)
			local animator = v:WaitForChild("Humanoid", 10) and v.Humanoid:WaitForChild("Animator", 10)
			if not hrp or not animator then
				return
			end

			getgenv().autoBlockconnections[#getgenv().autoBlockconnections + 1] = animator.AnimationPlayed:Connect(
				function(animationTrack)
					local combat = getStyle()
					local animation = animationTrack.Animation
					local id = animation.AnimationId
					local tool = v:FindFirstChildWhichIsA("Tool")
					local willGuardbreak = tool and guardBreakTable[tool.Name]

					local distance = hrp.Parent and char and (hrp.Position - char.HumanoidRootPart.Position).magnitude
					if
						not distance
						or distance > getgenv().ParryRange
						or not parryAnims[id]
						or not (math.random(1, 100) <= getgenv().ParryChance)
					then
						return
					end

					if willGuardbreak or parryAnims[id]["Guardbreak"] then
						if char:FindFirstChild("Blocking") then
							return combat:Activate()
						end --If we already blocking then just parry?

						if parryAnims[id]["Guardbreak"] then --Calculate speed
							task.wait(animationTrack.Speed / 10)
						end

						blockAttack()

						if getgenv().AutoCounter then
							guardBreak()
						end --This allows us to counter while blocking

						combat:Activate()
						task.wait(0.4)
						unblockAttack()
						return --We dont want to do anything else if they guardbreak
					end

					blockAttack()

					if getgenv().AutoCounter then
						guardBreak()
					end --This allows us to counter while blocking

					task.wait(0.4)
					unblockAttack()
				end
			)
		end

		risky:Label("-THESE ALL FROM AZTUP HUB NOT MINE-")
		risky:Label("(aztup hub source is public to anyone)")

		risky:Toggle("Auto Parry", false, function(Value)
			getgenv().AutoParry = Value

			if not getgenv().AutoParry then
				for i, v in pairs(getgenv().autoBlockconnections) do
					v:Disconnect()
				end

				return
			end

			for _, v in next, LivingThings:GetChildren() do
				task.spawn(autoParry, v)
			end

			LivingThings.ChildAdded:Connect(autoParry)
		end)

		risky:Slider("AP Range", { min = 1, max = 30, def = 18 }, function(Value)
			getgenv().ParryRange = Value
		end)

		risky:Slider("AP Chance", { min = 1, max = 100, def = 100 }, function(Value)
			getgenv().ParryChance = Value
		end)

		risky:Toggle("Auto Counter", false, function(Value)
			getgenv().AutoCounter = Value
		end)

		risky:Toggle("Attach to Back (Mobs)", false, function(Value)
			getgenv().attachtoback = Value

			if not getgenv().attachtoback then
				if ATBloop ~= nil then
					ATBloop:Disconnect()
					ATBloop = nil
				end
				return
			end

			local lastcheck = tick()
			local target = getMobInRange(ATBrange)
			print(target)
			local plr = game.Players.LocalPlayer
			local char = plr.Character

			ATBloop = game.RunService.Heartbeat:Connect(function()
				print("loop")
				if tick() - lastcheck >= 0.1 and target then
					lastcheck = tick()

					if target:FindFirstChild("KO") then
						return
					end
				end

				print(target)
				if not target or not target.Parent then
					target = getMobInRange(ATBrange)
				end
				print("1")
				if not target or not target:FindFirstChild("HumanoidRootPart") then
					return
				end
				print("2")

				char.HumanoidRootPart.CFrame = target.HumanoidRootPart.CFrame
					* (CFrame.new(0, ATBdistance, 1) * angleOffSet)
				char.HumanoidRootPart.AssemblyLinearVelocity = Vector3.zero
				char.HumanoidRootPart.AssemblyAngularVelocity = Vector3.zero
			end)
		end)

		risky:Slider("ATB Distance", { min = 1, max = 10, def = 5 }, function(Value)
			ATBdistance = Value
		end)

		risky:Slider("ATB Range", { min = 0, max = 100, def = 100 }, function(Value)
			ATBrange = Value
		end)

		local oldSpeed

		risky:Toggle("RunSpeed Changer", false, function(Value)
			getgenv().RunSpeedChanger = Value

			local func
			for i, v in next, getconnections(Events.UpdateStats.OnClientEvent) do
				if v.Function and not is_executor_closure(v.Function) then
					func = v.Function
				end
			end

			local tab = getupvalue(func, 1)
			oldSpeed = rawget(tab, "RunningSpeed") or oldSpeed
			if not getgenv().RunSpeedChanger then
				setmetatable(tab, nil)
				rawset(tab, "RunningSpeed", oldSpeed)
				return
			end

			setmetatable(tab, {
				__newindex = function(t, k, v)
					if k == "RunningSpeed" then
						return
					end
					return rawset(t, k, v)
				end,
				__index = function(t, k)
					if k == "RunningSpeed" then
						return getgenv().runningSpeed
					end
				end,
			})
			rawset(tab, "RunningSpeed", nil)
		end)

		risky:Slider("RunSpeed", { min = 0, max = 2300, def = 500 }, function(Value)
			getgenv().runningSpeed = Value
		end)

		local RhythmLooping = false

		risky:Toggle("Inf Rhythm", false, function(Value)
			getgenv().InfRhythm = Value
			if not RhythmLooping and getgenv().InfRhythm then
				local key = getKey(game.Players.LocalPlayer.Backpack.LocalS)
				if not key then
					return print("KEY NOT FOUND")
				end
				local action = game.Players.LocalPlayer.Backpack.Action
				action:FireServer(key, "RhythmStance", true)
				RhythmLooping = true
				repeat
					task.wait(0.1)
				until not getgenv().InfRhythm
				RhythmLooping = false
				action:FireServer(key, "RhythmStance", false)
			end
		end)

		risky:Toggle("Inf Dash", false, function(Value)
			getgenv().InfDash = Value

			if getgenv().InfDash then
				local env = getsenv(game.Players.LocalPlayer.Backpack.LocalS)
				repeat
					task.wait(0.1)
					setupvalue(env.Dash, 2, 3)
					setupvalue(env.Dash, 3, "")
				until not getgenv().InfDash
			end
		end)

		risky:Toggle("No Stam Dash", false, function(Value)
			getgenv().NoStamDash = Value
			local env = getsenv(game.Players.LocalPlayer.Backpack.LocalS)
			local constantNum = ScanTable(getconstants(env.Dash), "FireServer")
			if not getgenv().NoStamDash then
				setconstant(getsenv(plr.Backpack.LocalS).Dash, constantNum, "FireServer")
				return
			end
			setconstant(getsenv(plr.Backpack.LocalS).Dash, constantNum, "GetChildren")
		end)

		local InfTreadLoop = false

		risky:Toggle("Inf Treadmill Stamina", false, function(Value)
			getgenv().infTreadmillStamina = Value
		end)

		risky:Bind("Inf Tread Bind", Enum.KeyCode.Nine, function()
			if getgenv().infTreadmillStamina and not InfTreadLoop then
				getgenv().infTreadmillStaminaEnabled = true
				InfTreadLoop = true

				win.Notify({
					Title = "Inf Treadmill Stamina",
					Text = tostring(getgenv().infTreadmillStaminaEnabled),
				})

				local key = getKey(plr.Backpack.LocalS)

				if key then
					local action = plr.Backpack.Action
					repeat
						action:FireServer(key, "RunToggle", { [1] = true, [2] = false })
						task.wait()
						action:FireServer(key, "RunToggle", { false })
						task.wait(0.3)
					until not getgenv().infTreadmillStaminaEnabled or not getgenv().infTreadmillStamina
				end
				InfTreadLoop = false
				getgenv().infTreadmillStaminaEnabled = false
			elseif getgenv().infTreadmillStamina and InfTreadLoop then
				getgenv().infTreadmillStaminaEnabled = false
				win.Notify({
					Title = "Inf Treadmill Stamina",
					Text = tostring(getgenv().infTreadmillStaminaEnabled),
				})
			end
		end)
	end

	local aztupInit = false

    if typeof(getgc) ~= "nil" then
        risky:Button("-- Aztup MO Features --", function()
            if not getgenv().ACBYPASS then
                local banRemote
                local remoteKey

                local plr = game.Players.LocalPlayer
                local getupvalues = debug.getupvalues
                local getconstant = debug.getconstant
                local getconstants = debug.getconstants

                local ran, err = pcall(function()
                    local function initGC()
                        for _, v in next, getgc() do
                            local constants

                            local valid = pcall(function()
                                if typeof(v) == "function" and islclosure(v) and not is_executor_closure(v) then
                                    constants = getconstants(v)
                                end
                            end)

                            if constants ~= nil and valid then
                                if ScanTable(constants, "F1ySuspicion") then
                                    banRemote = getconstant(v, ScanTable(getconstants(v), "F1ySuspicion") - 1)
                                    local remoteFolder = 24

                                    for _, uv in next, getupvalues(v) do
                                        if typeof(uv) == "string" then
                                            remoteKey = uv
                                        end
                                    end

                                    if getupvalue(v, remoteFolder + 1) ~= remoteKey then
                                        plr:Kick("Kicked you to protect your account something, in the game has changed.")
                                        return
                                    end

                                    if
                                        getupvalue(v, remoteFolder)
                                        and getupvalue(v, remoteFolder):FindFirstChild(banRemote)
                                    then
                                        banRemote = getupvalue(v, remoteFolder):FindFirstChild(banRemote)
                                        return true
                                    else
                                        return plr:Kick("Failed to grab ban remote")
                                    end
                                end
                            end
                        end
                    end

                    print("waiting for gc scan.")
                    repeat
                        task.wait()
                    until initGC()

                    if not banRemote or not remoteKey then
                        plr:Kick("Kicked you to protect your account something, in the game has changed.")
                        return
                    end

                    if banRemote.Name ~= "Detector" then
                        plr:Kick("Kicked you to protect your account something, in the game has changed.")
                        return
                    end

                    local oldNamecall
                    oldNamecall = hookmetamethod(game, "__namecall", function(self, ...)
                        local ncMethod = getnamecallmethod()
                        if
                            self == banRemote and ncMethod == "FireServer"
                            or self == banRemote and ncMethod == "fireServer"
                        then
                            return
                        end

                        return oldNamecall(self, ...)
                    end)

                    local oldFireServer
                    oldFireServer = hookfunction(Instance.new("RemoteEvent").FireServer, function(self, ...)
                        if self == banRemote then
                            return
                        end

                        return oldFireServer(self, ...)
                    end)

                    getgenv().ACBYPASS = true
                end)

                if not ran then
                    warn(err)
                end
            end

            if getgenv().ACBYPASS and not aztupInit then
                aztupInit = true
                AztupElements()
            end
        end)
    else
        risky:Label("-- Unavaliable on your Executor --")
    end

	game.Players.PlayerAdded:Connect(function(v)
		if staffnotifier or copnotifier then
			Notifier(v)
		end

		if OPSNotifier and OPsData ~= nil then
			OPsData = game:GetService("HttpService"):JSONDecode(readfile("/m1keincorporated/MOoppositions.json"))

			if table.find(OPsData, tostring(v.UserId)) then
				webhook(
					"Opposition Detected",
					"DisplayName: " .. v.DisplayName .. "\nUsername: " .. v.Name .. "\nUserId: " .. tostring(v.UserId)
				)
			end
		end
	end)

	return win
end

local function RevengersDos(name)
    local win = library:Window(name,Color3.fromRGB(200,0,0))
    win.PromptDiscord("y7H2qGmNKd")
    
    local main = win:Tab("made by Lofi<3")
    local purchases = win:Tab("Purchases")
    local training = win:Tab("Training")
    local eating = win:Tab("Eating")
    local extras = win:Tab("Extras")
    local stats = win:Tab("Stats")
    local misc = win:Tab("Misc")
    
    spawn(function()
        while true do task.wait()
        pcall(function()
            game:GetService("Players").LocalPlayer.Backpack.Client.Check:Destroy()
            game:GetService("Players").LocalPlayer.Backpack.Client.ClientCheck:Destroy()
        end)
    end
    end)
    
    spawn(function()
        getgenv().staff = true
        while getgenv().staff do task.wait(0.5)
            pcall(function()
                for i,v in pairs(game.Players:GetPlayers()) do
                    if v:GetRankInGroup(12005833) >= 5 then
                        game.Players.LocalPlayer:Kick(v:GetRoleInGroup(12005833).." Joined.\n\nGroupID:"..v:GetRankInGroup(12005833))
                    end
                end
            end)
        end
    end)
    
    --//Funcs--\\
    local AutoTreadmills
    local AutoTreadmill = false
    local AutoPushups
    local AutoPushup = false
    local AutoDumbells
    local AutoDumbell = false
    local AutoSitups
    local AutoSitup = false
    local AutoSquats
    local AutoSquat = false
    local AutoBuyMembership
    local AutoBuyHealthCare
    local AutoBuyBaseReset
    local AutoBuyRest
    local AutoBuyAdvancedReset
    local AutoMembership
    local AutoDropCashFunc
    local AutoDropCash
    local Money
    local Anchor
    local Anchoring = false
    local BypassAnti
    local Bypass = false
    local AutoFatFunc
    local AutoFat = false
    local AutoSkinnyFunc 
    local AutoSkinny = false
    local AutoEatBurger
    local AutoEatB = false
    local AutoEatSalad
    local AutoEatS = false
    local AutoEatFries
    local AutoEatF = false
    local AutoDeposit
    local AutoDep = false
    local DepAmm = "0"
    local WithdrawFunc
    local Withdraw = false
    local WithAmm = "0"
    local TraAmm = "0"
    local DropAmm = "0"
    local FatAmm ="0"
    local InfFunc 
    local Inf = false
    local WardrobeFunc
    local HitboxFunc
    local Hitbox
    local HitAmm = "0"
    local OpenAtmFunc
    local AutoBuyAllClothing
    local Boxing
    local Brute
    local SchoolBoy
    local AutoPbFunc
    local AutoPb = false
    local PbAmm = "0"
    local PbDist = "0"
    local AutoFarmFunc
    local AutoFarm = false
    --// toggle vars \\--
    
    AutoFarmFunc = function()
        while AutoFarm do
            local args = {
                [1] = "kaoru",
                [2] = "take"
            }
    
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            task.wait(0.1)
            game.Players.LocalPlayer.Character:MoveTo(Vector3.new(1683, 40, -1244))
            task.wait(0.2)
            fireclickdetector(game:GetService("Workspace").Game.JobStuff.Crates.ClickDetector)
            game.Players.LocalPlayer.Character:MoveTo(Vector3.new(920, 40, -1106))
        end
    end
    
    Boxing = function()
        for i = 1,6 do
        local args = {
            [1] = "grippo",
            [2] = "training"
        }
        
        game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
    end
    end
    
    Brute = function()
        local args = {
            [1] = "yuriko",
            [2] = "take"
        }
        
        game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
        task.wait()
        local args = {
            [1] = "YurikoQuest"
        }
        
        game:GetService("ReplicatedStorage").Events.CheckQuest:InvokeServer(unpack(args))
    task.wait()
    local args = {
        [1] = "valefor",
        [2] = "done"
    }
    
    game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
    task.wait()
    local args = {
        [1] = "yuriko",
        [2] = "complete"
    }
    
    game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
    task.wait()
    for i =1,6 do
    local args = {
        [1] = "yuriko",
        [2] = "training"
    }
    
    game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
    end
    end
    
    SchoolBoy = function()
        for i = 1,6 do
        local args = {
            [1] = "schoolboy",
            [2] = "training"
        }
        
        game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
    end
    end
    
    AutoPbFunc = function()
    while AutoPb do task.wait(0.3)
    task.spawn(function()
    local LocalPlayer, Character = game.Players.LocalPlayer, game.Players.LocalPlayer.Character
    local Animations = {}
    
    for i,v in pairs(game:GetService("ReplicatedStorage").Animation:GetDescendants()) do
        if v:IsA("Folder") and v.Name == "General" then
            for k,x in pairs(v:GetChildren()) do
                if x.Name:find("Yari") or x.Name:find("Circularity") or x.Name:find("Kick") or x.Name:find("Heavy") or x.Name:find("Slash") or x.Name:find("Slam") or x.Name:find("Fist") or x.Name:find("Finisher") or x.Name:find("Ferris") or x.Name:find("Foot") or x.Name:find("Ground") or x.Name:find("Barrage") or x.Name:find("Wind") or x.Name:find("Combination") or x.Name:find("Circularity") or x.Name:find("Punch") or x.Name:find("Punisher") or x.Name:find("Bones") or x.Name:find("Wind") or x.Name:find("Combination") or x.Name:find("Circularity") or x.Name:find("Punch") then
                table.insert(Animations, x.AnimationId)
            end
        end
    end
    end
    
    while AutoPb do task.wait(0.3)
        pcall(function()
        for i,v in pairs(game:GetService("Players"):GetChildren()) do
            if v ~= LocalPlayer then
                local distance = (Character:WaitForChild("HumanoidRootPart").Position - v.Character:WaitForChild("HumanoidRootPart").Position).Magnitude
                if distance <= PbDist then
                    local Humanoid = v.Character:WaitForChild("Humanoid")
                    for _,track in pairs(Humanoid:GetPlayingAnimationTracks()) do
                         if table.find(Animations, track.Animation.AnimationId) then
                            task.wait(PbAmm/100)
                            game:GetService("VirtualInputManager"):SendKeyEvent(true, "F", false, game)
                            task.wait(0.30)
                            game:GetService("VirtualInputManager"):SendKeyEvent(false, "F", false, game)
                            task.wait(0.5)
                            
                        end
                    end
                end
            end
        end
    end)
    end
    end)
    
    while AutoPb do task.wait(0.3)
    task.spawn(function()
        local LocalPlayer, Character = game.Players.LocalPlayer, game.Players.LocalPlayer.Character
        local Animations = {}
        
        for i,v in pairs(game:GetService("ReplicatedStorage").Animation:GetDescendants()) do
            if v:IsA("Folder") and v.Name == "General" then
                for k,x in pairs(v:GetChildren()) do
                    if x.Name:find("Teppo") or x.Name:find("Combination") or x.Name:find("Punisher") or x.Name:find("Bones") then
                    table.insert(Animations, x.AnimationId)
                end
            end
        end
        end
    
        while AutoPb do task.wait(0.3)
            pcall(function()
            for i,v in pairs(game:GetService("Players"):GetChildren()) do
                if v ~= LocalPlayer then
                    local distance = (Character:WaitForChild("HumanoidRootPart").Position - v.Character:WaitForChild("HumanoidRootPart").Position).Magnitude
                    if distance <= PbDist then
                        local Humanoid = v.Character:WaitForChild("Humanoid")
                        for _,track in pairs(Humanoid:GetPlayingAnimationTracks()) do
                             if table.find(Animations, track.Animation.AnimationId) then
                                task.wait(0.09)
                                game:GetService("VirtualInputManager"):SendKeyEvent(true, "F", false, game)
                                task.wait(0.30)
                                game:GetService("VirtualInputManager"):SendKeyEvent(false, "F", false, game)
                                task.wait(0.5)
                                
                            end
                        end
                    end
                end
            end
        end)
        end
        end)
    end
    end
    end
    
    AutoEatBurger = function()
        while AutoEatB do task.wait()
            if game:GetService("Players").LocalPlayer.Stats.Hunger.Value == 20 then
                fireclickdetector(game:GetService("Workspace").Game.Selling.Hamburger.ClickDetector)
                task.wait()
                for i,v in next, game.Players.LocalPlayer.Backpack:GetChildren() do
                    task.wait()
                    if v:isA("Tool") and v.Name == "Hamburger" then
                        game.Players.LocalPlayer.Character.Humanoid:EquipTool(v)
                        game:GetService("Players").LocalPlayer.Character:FindFirstChild("Hamburger"):Activate()
                    end
                end
            end
    
            end
    end
    
    AutoBuyAllClothing = function()
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Red Striped Clothes"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Black Half-Shirt"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "White Hoodie"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Black Suit"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Gray Hoodie"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Gray Suit"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Red Clothes"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Old Clothes"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Millitary-like Clothes"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Blue Shirt"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Black Outfit"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Blue Hoodie"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Red Outfit"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Yellow Outfit"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Sportswear"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Sleeveless Jacket"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Trenchcoat"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Icey Outfit"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Sea Girl"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Red Suit"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Casual Outfit"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Comfortable Casual"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Volleyball Kit"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
            local args = {
                [1] = "seller",
                [2] = "buy",
                [3] = "Casual Job Uniform"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))    
    end
    
    WithdrawFunc = function()
        while Withdraw do task.wait()
            local args = {
                [1] = "withdraw",
                [2] = WithAmm
            }
            game:GetService("Players").LocalPlayer.PlayerGui.MainGui.ATM.Server:InvokeServer(unpack(args))
        end
    end
    
    HitboxFunc = function()
        while Hitbox do task.wait()
            for i,v in next, game:GetService("Workspace").Game.Bikes:GetDescendants() do
                if v:isA("Part") and v.Name == "Hitbox" then
                    v.Size = Vector3.new(5, 3, HitAmm)
                end
            end
        end
    end
    
    
    AutoEatSalad = function()
        while AutoEatS do task.wait()
            if game:GetService("Players").LocalPlayer.Stats.Hunger.Value == 20 then
                fireclickdetector(game:GetService("Workspace").Game.Selling.Fries.ClickDetector)
                task.wait()
                for i,v in next, game.Players.LocalPlayer.Backpack:GetChildren() do
                    task.wait()
                    if v:isA("Tool") and v.Name == "Fries" then
                        game.Players.LocalPlayer.Character.Humanoid:EquipTool(v)
                        game:GetService("Players").LocalPlayer.Character:FindFirstChild("Fries"):Activate()
    
            end
        end
    end
    end
    end
    
    WardrobeFunc = function()
            local args = {
                [1] = "register",
                [2] = "wardrobe"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
    end
    
    
    InfFunc = function()
        while Inf do task.wait()
            if game:GetService("Players").LocalPlayer.Stats.Fatigue.Value >= FatAmm then
                local args = {
                    [1] = "register",
                    [2] = "take1"
                }
                
                game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
    task.wait()
        local args = {
            [1] = "register",
            [2] = "rest"
        }
        
        game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
    end   
    end
    end
    
    AutoEatFries = function()
        while AutoEatS do task.wait()
            if game:GetService("Players").LocalPlayer.Stats.Hunger.Value == 20 then
                fireclickdetector(game:GetService("Workspace").Game.Selling.Salad.ClickDetector)
                task.wait()
                for i,v in next, game.Players.LocalPlayer.Backpack:GetChildren() do
                    task.wait()
                    if v:isA("Tool") and v.Name == "Salad" then
                        game.Players.LocalPlayer.Character.Humanoid:EquipTool(v)
                        game:GetService("Players").LocalPlayer.Character:FindFirstChild("Salad"):Activate()
    
            end
        end
    end
    end
    end
    
    AutoFatFunc = function()
        while AutoFat do task.wait()
        pcall(function()
    fireclickdetector(game:GetService("Workspace").Game.Selling.Hamburger.ClickDetector)
    task.wait()
    for i,v in next, game.Players.LocalPlayer.Backpack:GetChildren() do
        task.wait()
        if v:isA("Tool") and v.Name == "Hamburger" then
            game.Players.LocalPlayer.Character.Humanoid:EquipTool(v)
            game:GetService("Players").LocalPlayer.Character:FindFirstChild("Hamburger"):Activate()
        end
    end
    end)
    end
    end
    
    AutoSkinnyFunc = function()
        while AutoSkinny do task.wait()
        pcall(function()
    fireclickdetector(game:GetService("Workspace").Game.Selling.Salad.ClickDetector)
    task.wait()
    for i,v in next, game.Players.LocalPlayer.Backpack:GetChildren() do
        task.wait()
        if v:isA("Tool") and v.Name == "Salad" then
            game.Players.LocalPlayer.Character.Humanoid:EquipTool(v)
            game:GetService("Players").LocalPlayer.Character:FindFirstChild("Salad"):Activate()
        end
    end
    end)
    end
    end
    
    AutoBuyMembership = function()
        while AutoMembership do task.wait()
            if game.Players.LocalPlayer.Stats.GymTime.Value <= 300 then
            local args = {
                [1] = "cashier girl",
                [2] = "take"
            }
            
            game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
    end
    end
    end
    
    AutoBuyRest = function()
    local args = {
        [1] = "register",
        [2] = "take1"
    }
    
    game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
    task.wait()
    local args = {
    [1] = "register",
    [2] = "rest"
    }
    
    game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
    end
    
    AutoBuyBaseReset = function()
        local args = {
            [1] = "nurse",
            [2] = "take"
        }
        
        game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))    
    end
    
    AutoBuyAdvancedReset = function()
        local args = {
            [1] = "nurse",
            [2] = "take2"
        }
        
        game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))    
    end
    
    AutoBuyHealthCare = function()
        local args = {
            [1] = "doctor",
            [2] = "take"
        }
        
        game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
    end
    
    AutoDropCashFunc = function()
        while AutoDropCash do task.wait(2)
    local args = {
        [1] = DropAmm
    }
    
    game:GetService("Players").LocalPlayer.PlayerGui.MainGui.Stats:FindFirstChild("2").Yen.drop:FireServer(unpack(args))
    end
    end
    
    AutoTreadmills = function()
        while AutoTreadmill do task.wait() 
        pcall(function()
        if game:GetService("Players").LocalPlayer.Stats.Stamina.Value == game.Players.LocalPlayer.Character.INFO.MaxStamina.Value then
            for i,k in pairs(game:GetService("Workspace").Game.WorkOut.Treadmill:GetChildren()) do
    if k.CFrame == CFrame.new(1062.53577, 40.4393845, -1231.08936, -0.0175019503, 0, 0.999846935, 0, 1, 0, -0.999846935, 0, -0.0175019503) then
            for i,v in pairs(k:GetDescendants()) do
            if v:IsA("ProximityPrompt") then
                fireproximityprompt(v)
            end
        
        end
        end
    end
    end
        end)
        end
    end
    
    AutoPushups = function()
        while AutoPushup do task.wait()
            pcall(function()
                if game:GetService("Players").LocalPlayer.Stats.Stamina.Value == game.Players.LocalPlayer.Character.INFO.MaxStamina.Value then
                    for i,k in pairs(game:GetService("Workspace").Game.WorkOut.PushUp:GetChildren()) do
            if k.CFrame == CFrame.new(1117.58826, 38.0501251, -1262.35608, 0, 0, -1, 0, 1, 0, 1, 0, 0) then
                    for i,v in pairs(k:GetDescendants()) do
                    if v:IsA("ProximityPrompt") then
                        fireproximityprompt(v)
                        end
                end
            
            end
            end
            end
            end)
    end
    end
    
    AutoDumbells = function()
        while AutoDumbell do task.wait()
        pcall(function()
            if game:GetService("Players").LocalPlayer.Stats.Stamina.Value == game.Players.LocalPlayer.Character.INFO.MaxStamina.Value then
                for i,k in pairs(game:GetService("Workspace").Game.WorkOut.Dumbells:GetChildren()) do
        if k.CFrame == CFrame.new(1053.72571, 40.1236, -1273.3252, 0, 0, 1, 0, 1, -0, -1, 0, 0) then
                for i,v in pairs(k:GetDescendants()) do
                    if v:IsA("ProximityPrompt") then
                fireproximityprompt(v)
            end
        
        end
        end
    end
        end
        end)
    end
    end
    
    AutoSitups = function()
        while AutoSitup do task.wait()
            pcall(function()
                if game:GetService("Players").LocalPlayer.Stats.Stamina.Value == game.Players.LocalPlayer.Character.INFO.MaxStamina.Value then
                    for i,k in pairs(game:GetService("Workspace").Game.WorkOut.SitUp:GetChildren()) do
            if k.CFrame == CFrame.new(1104.08826, 38.0501251, -1262.35608, 0, 0, -1, 0, 1, 0, 1, 0, 0) then
                    for i,v in pairs(k:GetDescendants()) do
                        if v:IsA("ProximityPrompt") then
                    fireproximityprompt(v)
                    end
                end
            end
        end
        end
    end)
    end
    end
    
    AutoDeposit = function()
        while AutoDep do task.wait()
        local args = {
            [1] = "deposit",
            [2] = DepAmm
        }
        
        game:GetService("Players").LocalPlayer.PlayerGui.MainGui.ATM.Server:InvokeServer(unpack(args))
        
    end
    end
    
    
    AutoSquats = function()
        while AutoSquat do task.wait()
            pcall(function()
                if game:GetService("Players").LocalPlayer.Stats.Stamina.Value == game.Players.LocalPlayer.Character.INFO.MaxStamina.Value then
                    for i,k in pairs(game:GetService("Workspace").Game.WorkOut.Squats:GetChildren()) do
            if k.CFrame == CFrame.new(1090.58826, 38.0501251, -1262.35608, 0, 0, -1, 0, 1, 0, 1, 0, 0) then
                    for i,v in pairs(k:GetDescendants()) do
                        if v:IsA("ProximityPrompt") then
                    fireproximityprompt(v)
                        end
                end
            
            end
            end
            end
            end)
    end
    end
    
    Money = function()
        local args = {
            [1] = 0/0
        }
        
        game:GetService("Players").LocalPlayer.PlayerGui.MainGui.Stats:FindFirstChild("2").Yen.drop:FireServer(unpack(args))
    end
    
    Anchor = function()
        while Anchoring do task.wait()
        for i, x in next,game.Players.LocalPlayer.Character:GetDescendants() do
            if x:IsA("BasePart") and not x.Anchored then
                x.Anchored = true
            end
        end
    end
    for i, x in next, game.Players.LocalPlayer.Character:GetDescendants() do
        if x:IsA("BasePart") and x.Anchored then
            x.Anchored = false
        end
    end
    end
    
    
    BypassAnti = function()
        while Bypass do task.wait()
            pcall(function()
                game:GetService("Players").LocalPlayer.Backpack.Client.Check:Destroy()
                game:GetService("Players").LocalPlayer.Backpack.Client.ClientCheck:Destroy()
            end)
        end
    end
    
    local function SafeSpot()
        local baseplate = Instance.new("Part")
    baseplate.Parent = workspace
    baseplate.Size = Vector3.new(100,5,100) 
    baseplate.Anchored = true
    baseplate.Position = game.Players.LocalPlayer.Character.HumanoidRootPart.Position + Vector3.new(0,110,0)
    task.wait(1)
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = baseplate.CFrame + Vector3.new(0,10,0)
    end
    
    --\\ Main //--

    main:Label("---Astra bad ash<3---")
    
    main:Button("Wardrobe",function()
        pcall(function()
            WardrobeFunc()
    end) 
    end)
    
    
    main:Button("Safe-Spot",function()
        pcall(function()
            SafeSpot()
    end) 
    end)
    
    --\\ Training //--
    training:Label("---Training Shit <3---")
    
    training:Toggle("Auto Treadmill",false, function(Value)
        local togglefunc = AutoTreadmills
        AutoTreadmill = Value
        if AutoTreadmill then
            pcall(function()
            togglefunc()
        end)
    end
    end)
    
    training:Toggle("Auto Dumbells",false, function(Value)
        local togglefunc = AutoDumbells
        AutoDumbell = Value
        if AutoDumbell then
            pcall(function()
              togglefunc()
            end)
        end
    end)
    
    training:Toggle("Auto Pushups",false, function(Value)
        local togglefunc = AutoPushups
        AutoPushup = Value
        if AutoPushup then
            pcall(function()
            togglefunc()
        end)
    end
    end)
    
    training:Toggle("Auto Situps",false,function(Value)
        local togglefunc = AutoSitups
        AutoSitup = Value
        if AutoSitup then
            pcall(function()
              togglefunc()
            end)
        end
    end)
    
    training:Toggle("Auto Squats",false, function(Value)
        local togglefunc = AutoSquats
        AutoSquat = Value
        if AutoSquat then
            pcall(function()
              togglefunc()
            end)
        end
    end)
    
    training:Label("---Sora a baddie<3---")
    
    training:Toggle("Reset Fatigue & Hunger",false, function(Value)
        local togglefunc = InfFunc
        Inf = Value
        if Inf then
            pcall(function()
            togglefunc()
        end)
    end
    end)
    
    training:Slider("Reset Fatigue Percentage",{min=0,max=100,def=FatAmm},function(Value)
        FatAmm = Value
    end)
    
    --\\ Misc //--
    
    --// Purchase \\--
    purchases:Label("---Purchase Items<3---")
    
    purchases:Button("Bat", function()
        local args = {
            [1] = "bat seller",
            [2] = "buy"
        }
        
        game:GetService("ReplicatedStorage").Events.DialogueAnswer:InvokeServer(unpack(args))
        
    end)
    
    purchases:Button("Rest",function()
        AutoBuyRest()
    end) 
    
    purchases:Button("Health Care",function()
        AutoBuyHealthCare()
    end) 
    
    purchases:Button("Base Reset",function()
        AutoBuyBaseReset()
    end) 
    
    purchases:Button("Auto Buy Clothing",function()
        AutoBuyAllClothing()
    end) 
    
    purchases:Button("Advanced Reset",function()
        AutoBuyAdvancedReset()
    end) 
    
    purchases:Button("Stat Check",function()
        fireclickdetector(game:GetService("Workspace").Game.Selling["Stat Check"].ClickDetector)
    end) 
    
    purchases:Button("Ramen",function()
        fireclickdetector(game:GetService("Workspace").Game.Selling.Ramen.ClickDetector)
    end) 
    
    purchases:Button("Salad",function()
        fireclickdetector(game:GetService("Workspace").Game.Selling.Salad.ClickDetector)
    end)
    
    purchases:Button("Latte",function()
        fireclickdetector(game:GetService("Workspace").Game.Selling.Latte.ClickDetector)
    end) 
    
    purchases:Button("Purple Candy",function()
        fireclickdetector(game:GetService("Workspace").Game.Selling["Purple Candy"].ClickDetector)
    end) 
    
    purchases:Button("Pink Candy",function()
        fireclickdetector(game:GetService("Workspace").Game.Selling["Pink Candy"].ClickDetector)
    end) 
    
    purchases:Button("Orange Candy",function()
        fireclickdetector(game:GetService("Workspace").Game.Selling["Orange Candy"].ClickDetector)
    end) 
    
    purchases:Button("Green Candy",function()
        fireclickdetector(game:GetService("Workspace").Game.Selling["Green Candy"].ClickDetector)
    end) 
    
    purchases:Button("Blue Candy",function()
        fireclickdetector(game:GetService("Workspace").Game.Selling["Blue Candy"].ClickDetector)
    end) 
    
    purchases:Button("Red Candy",function()
        fireclickdetector(game:GetService("Workspace").Game.Selling["Red Candy"].ClickDetector)
    end) 
    
    purchases:Button("Chocolate Chip Cookie",function()
        fireclickdetector(game:GetService("Workspace").Game.Selling["Chocolate Chip Cookie"].ClickDetector)
    end) 
    
    purchases:Button("Hamburger",function()
        fireclickdetector(game:GetService("Workspace").Game.Selling.Hamburger.ClickDetector)
    end) 
    
    purchases:Button("Fries",function()
        fireclickdetector(game:GetService("Workspace").Game.Selling.Fries.ClickDetector)
    end) 
    
    purchases:Button("Cola",function()
        fireclickdetector(game:GetService("Workspace").Game.Selling.Cola.ClickDetector)
    end)
    
    purchases:Button("Impact Training",function()
        fireclickdetector(game:GetService("Workspace").Game.Selling["Impact Training"].ClickDetector)
    end) 
    
    purchases:Button("Debit Card",function()
        fireclickdetector(game:GetService("Workspace").Game.Selling["Debit Card"].ClickDetector)
    end) 
     
    purchases:Button("Face Mask", function()
        fireclickdetector(game:GetService("Workspace").Game.Clothes:GetChildren()[17].Torso.ClickDetector)
    end)
    
    purchases:Label("---Styles<3---")
    
    purchases:Button("Brute",function()
        pcall(function()
            Brute()
    end) 
    end)
    
    purchases:Button("Boxing",function()
        pcall(function()
            Boxing()
    end) 
    end)
    
    purchases:Button("School Boy",function()
        pcall(function()
            SchoolBoy()
    end) 
    end)
    
    --\\ Buy //--
    
    misc:Label("---Drops<3---")
    
    misc:Toggle("Auto Drop",false, function(Value)
        local togglefunc = AutoDropCashFunc
        AutoDropCash = Value
        if AutoDropCash then
            pcall(function()
            togglefunc()
        end)
    end
    end)
    
    misc:Slider("Drop Ammount",{min=0,max=5000,def=DropAmm},function(Value)
        DropAmm = Value
    end)
    
    
    misc:Label("---Deposits<3---")
    
    misc:Toggle("Auto Deposit",false, function(Value)
        local togglefunc = AutoDeposit
        AutoDep = Value
        if AutoDep then
            pcall(function()
            togglefunc()
        end)
    end
    end)
    
    misc:Slider("Deposit Amount",{min=0,max=500000,def=DepAmm},function(Value)
        DepAmm = Value
    end)
    
    misc:Label("---Withdraw<3---")
    
    misc:Toggle("Auto Withdraws",false,function(Value)
        local togglefunc = WithdrawFunc
        Withdraw = Value
        if Withdraw then
            pcall(function()
            togglefunc()
        end)
    end
    end)
    
    misc:Slider("Withdraw Ammount",{min=0,max=5000,def=DepAmm},function(Value)
        WithAmm = Value
    end)
    
    misc:Label("---Transfers<3---")
    
    misc:Textbox("Auto Transfer",function(Value)
        pcall(function()
        local name = Value
        local args = {
            [1] = "transfer",
            [2] = TraAmm,
            [3] = name
        }
        
        game:GetService("Players").LocalPlayer.PlayerGui.MainGui.ATM.Server:InvokeServer(unpack(args))
        end)
    end)
    
    misc:Slider("Transfer Ammount",{min=0,max=500000,def=TraAmm},function(Value)
        TraAmm = Value
    end)
    
    --// Eating --\\
    eating:Label("---BULKING & CUTTING <3---")
    
    eating:Label("---Auto Eat Detects Hunger Percentage<3---")
    
    eating:Toggle("Auto Eat Burger",false, function(Value)
        local togglefunc = AutoEatBurger
        AutoEatB = Value
        if AutoEatB then
            pcall(function()
            togglefunc()
        end)
    end
    end)
    
    eating:Toggle("Auto Eat Fries",false,function(Value)
        local togglefunc = AutoEatFries
        AutoEatF = Value
        if AutoEatF then
            pcall(function()
            togglefunc()
        end)
    end
    end)
    
    eating:Toggle("Auto Eat Salad",false, function(Value)
        local togglefunc = AutoEatSalad
        AutoEatS = Value
        if AutoEatS then
            pcall(function()
            togglefunc()
        end)
    end
    end)
    
    eating:Toggle("Auto Fat",false, function(Value)
        local togglefunc = AutoFatFunc
        AutoFat = Value
        if AutoFat then
            pcall(function()
            togglefunc()
        end)
    end
    end)
    
    eating:Toggle("Auto Skinny",false, function(Value)
        local togglefunc = AutoSkinnyFunc
        AutoSkinny = Value
        if AutoSkinny then
            pcall(function()
            togglefunc()
        end)
    end
    end)
    
    --// EXTRAS \\--
    
    extras:Toggle("Anchor",false, function(Value)
        local togglefunc = Anchor
        Anchoring = Value
        if Anchoring then
            pcall(function()
            togglefunc()
        end)
    end
    end)
    
    extras:Toggle("MoneyFarm",false, function(Value)
        local togglefunc = AutoFarmFunc
        AutoFarm = Value
        if AutoFarm then
            pcall(function()
            togglefunc()
        end)
    end
    end)
    
    extras:Toggle("Bypass-AntiCheat",false, function(Value)
        local togglefunc = BypassAnti
        Bypass = Value
        if Bypass then
            pcall(function()
            togglefunc()
        end)
    end
    end)
    
    extras:Toggle("Auto Buy Membership",false, function(Value)
        local togglefunc = AutoBuyMembership
        AutoMembership = Value
        if AutoMembership then
            pcall(function()
            togglefunc()
        end)
    end
    end)
    
    extras:Toggle("Hitbox",false, function(Value)
        local togglefunc = HitboxFunc
        Hitbox = Value
        if Hitbox then
            pcall(function()
            togglefunc()
        end)
    end
    for i,v in next, game:GetService("Workspace").Game.Bikes:GetDescendants() do
        if v:isA("Part") and v.Name == "Hitbox" then
            v.Size = Vector3.new(1, 1, 1)
        end
    end
    end)
    
    extras:Slider("Hitbox Size",{min=0,max=100,def=FatAmm},function(Value)
        HitAmm = Value
    end)
    
    --// Stat Check \\--
    stats:Label("---Stat Check<3---")
    
    stats:Label("Strength<3")
    
    local StatCheck2  = stats:Label(game:GetService("Players").LocalPlayer.Stats.StrengthEXP.Value)
    task.spawn(function()
    task.wait(0.5)
    while true do task.wait(0.9)
    StatCheck2:SetText(game:GetService("Players").LocalPlayer.Stats.StrengthEXP.Value)
    end
    end)
    task.wait()
    
    stats:Label("Defense<3")
    
    task.spawn(function()
    local StatCheck  = stats:Label(game:GetService("Players").LocalPlayer.Stats.DefenseEXP.Value)
    task.wait(0.5)
    while true do task.wait(0.9)
    StatCheck:SetText(game:GetService("Players").LocalPlayer.Stats.DefenseEXP.Value)
    task.wait()
    end
    end)
    
    stats:Label("Stamina<3")
    
    local StatCheck3  = stats:Label(game:GetService("Players").LocalPlayer.Stats.StaminaEXP.Value)
    task.wait(0.5)
    task.spawn(function()
    while true do task.wait(0.9)
    StatCheck3:SetText(game:GetService("Players").LocalPlayer.Stats.StaminaEXP.Value)
    end
    end)
    
    stats:Label("Speed<3")
    
    local StatCheck4  = stats:Label(game:GetService("Players").LocalPlayer.Stats.SpeedBoost.Value)
    task.wait(0.5)
    task.spawn(function()
    while true do task.wait(0.9)
    StatCheck4:SetText(game:GetService("Players").LocalPlayer.Stats.SpeedBoost.Value)
    task.wait()
    end
    end)
    
    stats:Label("Fat<3")
    
    local StatCheck5  = stats:Label(game:GetService("Players").LocalPlayer.Stats.Fat.Value)
    task.wait(0.5)
    task.spawn(function()
    while true do task.wait(0.9)
    StatCheck5:SetText(game:GetService("Players").LocalPlayer.Stats.Fat.Value)
    end
    end)
    
    return win
end

local function Ken_Omega(name)
    local win = library:Window(name,Color3.fromRGB())
    win.PromptDiscord("y7H2qGmNKd")
    
    local main = win:Tab("mike hates this game")
    main:Label("-- All features made by ! Zho#7471, myke helped a bit --")
    
    local misc = win:Tab("misc")
    
    local itemselected
    local autobuyitem
    local NOCLIP
    local SelectedBag
    local ClickSpeed, TweenSpeed = 2, 4 -- 1 clickspeed should be set by default
    local CurrentStamina, MaximumStamina, MinimumStamina = game.Players.LocalPlayer.Character.Stamina, game.Players.LocalPlayer.Character.Stamina.MaxValue, 10
    local HungerAmount = 10
    local AutoEat
    local AutoTools
    local SelectedTool
    local AutoSparTraining
    local AutoShadowTraining
    local AutoSelfPunch
    local FastAutoSelfPunch
    local AutoRoadWork
    local AutoJobs
    local BetterAutoJobs
    local AutoDeposit
    local LocalPlayer, Character, HumanoidRootPart = game.Players.LocalPlayer, game.Players.LocalPlayer.Character, game.Players.LocalPlayer.Character.HumanoidRootPart
    local BAGS = {
        CFrame.new(-1685.0011, 93.5063248, -132.730225, 0.999947369, 8.00805822e-08, 0.0102596376, -8.01791487e-08, 1, 9.19620469e-09, -0.0102596376, -1.00183302e-08, 0.999947369), -- Bag 1
        CFrame.new(-1694.87891, 93.5063248, -133.061447, 0.999771833, 6.57242039e-10, -0.0213605817, -5.36138023e-10, 1, 5.67523628e-09, 0.0213605817, -5.66248914e-09, 0.999771833), -- Bag 2
        CFrame.new(-1704.84485, 93.5063248, -133.934753, 1, 3.79463323e-08, 5.28495366e-05, -3.79501337e-08, 1, 7.19224076e-08, -5.28495366e-05, -7.19244184e-08, 1), -- Bag 3
        CFrame.new(-1715.08411, 93.5063248, -132.694626, 0.999996305, 1.22755779e-07, 0.00271634944, -1.22694061e-07, 1, -2.2889342e-08, -0.00271634944, 2.25559784e-08, 0.999996305), -- Bag 4
        CFrame.new(-1725.078, 93.5063248, -132.691666, 0.999781847, -3.24157057e-08, 0.0208870079, 3.25733502e-08, 1, -7.2072659e-09, -0.0208870079, 7.88605359e-09, 0.999781847) -- Bag 5
    }

    
    local function autoeat()
        while AutoEat do task.wait()
            if (game.Players.LocalPlayer.PlayerGui.HUD.Food.AbsoluteSize.X/game:GetService("Players").LocalPlayer.PlayerGui.HUD.Back3.AbsoluteSize.X * 100) <= HungerAmount and not game.Players.LocalPlayer.Character:FindFirstChildWhichIsA("Tool") then
                for _,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                    if v:IsA("Tool") and v:FindFirstChild("Hunger") then
                        v.Parent = game.Players.LocalPlayer.Character
                        game.Players.LocalPlayer.Character:FindFirstChildWhichIsA("Tool"):Activate()
                        task.wait(3)
                        break
                    end
                end
            end
        end
    end
    
    local function autodeposit()
        while AutoDeposit do task.wait()
            if game:GetService("Players").LocalPlayer.PlayerGui.HUD.Money.Text ~= "0$" then
                local depamt = game:GetService("Players").LocalPlayer.PlayerGui.HUD.Money.Text:split("$")[1]
                
                if depamt:find(",") then
                   depamt = depamt:split(",")
                    depamt = tonumber(depamt[1]..depamt[2])
                else
                    depamt = tonumber(depamt)
                end
                
                game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Withdraw"):FireServer("Deposit", depamt)
            end
        end
    end
    
    local function autotools(ToolType)
        while AutoTools do task.wait()
            pcall(function()
                    if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolType) then
                        game.Players.LocalPlayer.Backpack:FindFirstChild(ToolType).Parent = game.Players.LocalPlayer.Character
                    elseif game.Players.LocalPlayer.Character:FindFirstChild(ToolType) == nil then
                        return
                    end
                    repeat task.wait()
                        if game:GetService("Players").LocalPlayer.Status:FindFirstChild("Training") then
                            task.wait()
                        elseif game:GetService("Players").LocalPlayer.Status:FindFirstChild("Cancel") or game:GetService("Players").LocalPlayer.Status:FindFirstChild("Cancel") == nil and game:GetService("Players").LocalPlayer.Status:FindFirstChild("Training") == nil then
                            game:GetService("VirtualInputManager"):SendMouseButtonEvent(500, 500, 0, true, game, 1)
                            task.wait(ClickSpeed)
                        end
                    until CurrentStamina.Value <= MinimumStamina or getgenv().AutoTools == false
                    game.Players.LocalPlayer.Character.Humanoid:UnequipTools(v)
                    repeat task.wait() until CurrentStamina.Value >= MaximumStamina or getgenv().AutoTools == false
            end)
        end
    end
    
    function GoToShop()
        Tween(CFrame.new(-2114.79028, 93.6563492, 114.331741, -0.99812305, -4.37287078e-08, 0.0612398796, -4.24695692e-08, 1, 2.18623732e-08, -0.0612398796, 1.92205079e-08, -0.99812305))
    end
    
    function GoToGym()
        Tween(CFrame.new(-1703.69983, 93.5063248, -123.967247, 0.999823213, 1.33610989e-09, -0.018802302, -1.31415789e-09, 1, 1.17987464e-09, 0.018802302, -1.1549568e-09, 0.999823213))
    end
    
    function GoToHospital()
        Tween(CFrame.new(-1789.677, 92.5563278, -302.842987, -0.999996185, 8.55703988e-08, 0.00275733043, 8.55462901e-08, 1, -8.86184903e-09, -0.00275733043, -8.62593641e-09, -0.999996185))
    end
    
    function GoToStatCheckup()
        Tween(CFrame.new(-1761.34961, 95.2061234, 186.927795, -0.0287035853, 2.51191441e-08, -0.999587953, -3.56071794e-09, 1, 2.52317456e-08, 0.999587953, 4.28349223e-09, -0.0287035853))
    end
    
    function GoToKNC()
        Tween(CFrame.new(-1847.86475, 92.5563202, 9.41817856, 0.0396863557, 1.39161891e-08, -0.999212205, 5.74216186e-09, 1, 1.41552263e-08, 0.999212205, -6.29940722e-09, 0.0396863557))
    end
    
    function GoToConstructionSite()
        Tween(CFrame.new(-1547.13647, 140.777939, 173.305527, -0.0362943858, -9.38506051e-10, 0.99934113, 7.31345606e-09, 1, 1.2047372e-09, -0.99934113, 7.35236272e-09, -0.0362943858))
    end
    
    function GoToGravityChamber()
        Tween(CFrame.new(-2056.39429, 111.366653, 786.944153, -0.996872604, 7.96786068e-08, -0.0790255293, 7.93209836e-08, 1, 7.66448505e-09, 0.0790255293, 1.37213241e-09, -0.996872604))
    end
        
    function autospartrain(SelectedBag)
        while AutoSparTraining do task.wait()
            pcall(function()
                if not LocalPlayer.Backpack:FindFirstChild("Spar Training") and not Character:FindFirstChild("Spar Training") and not Character:FindFirstChild("Right") and not Character:FindFirstChild("Left") then
                    fireclickdetector(workspace.Shop["Spar Training $380"].Head.ClickDetector)
                else
                    local TS = game:GetService("TweenService"):Create(HumanoidRootPart, TweenInfo.new(3), {CFrame = SelectedBag})
                    TS:Play()
                    task.wait(1)
                    LocalPlayer.Backpack:FindFirstChild("Spar Training").Parent = Character
                    Character:FindFirstChild("Spar Training"):Activate()
                    task.wait(0.35)
                    LocalPlayer.Backpack:FindFirstChild("Basic Combat").Parent = Character
                    repeat task.wait()
                        Character:FindFirstChild("Basic Combat"):Activate()
                    until Character:FindFirstChild("Right") == nil or Character:FindFirstChild("Left") == nil or getgenv().AutoSparTraining ~= true
                    Character:FindFirstChild("Basic Combat").Parent = LocalPlayer.Backpack
                end
            end)
        end
    end
    
    local function autoshadowtraining()
        while AutoShadowTraining do task.wait()
            pcall(function()
                local shadowtrain = game:GetService("Workspace").Shop["Shadow Training $130"].Head

                if game.Players.LocalPlayer.Backpack:FindFirstChild("Shadow Training") or game.Players.LocalPlayer.Character:FindFirstChild("Shadow Training") then
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Shadow Training") then
                       game.Players.LocalPlayer.Backpack:FindFirstChild("Shadow Training").Parent = game.Players.LocalPlayer.Character 
                    end

                    task.wait(0.25)
                    game.Players.LocalPlayer.Character:FindFirstChild("Shadow Training"):Activate()
                    game.Players.LocalPlayer.Backpack:FindFirstChild("Basic Combat").Parent = game.Players.LocalPlayer.Character
                    repeat task.wait(0.25)
                        local Distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - game:GetService("Workspace").Live:WaitForChild("Shadow").HumanoidRootPart.Position).Magnitude
                        if game:GetService("Workspace").Live:FindFirstChild("Shadow") and Distance <= 10 then
                            game.Players.LocalPlayer.Character:SetPrimaryPartCFrame(CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position, game:GetService("Workspace").Live:FindFirstChild("Shadow").HumanoidRootPart.Position))
                            task.wait(0.25)
                            game.Players.LocalPlayer.Character:FindFirstChild("Basic Combat"):Activate()
                        end
                    until game.Players.LocalPlayer.Status:FindFirstChild("Shadow") == nil or AutoShadowTraining == false
                    game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
                elseif not game.Players.LocalPlayer.Status:FindFirstChild("Shadow") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Shadow Training") and not game.Players.LocalPlayer.Character:FindFirstChild("Shadow Training") then
                    local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - shadowtrain.Position).Magnitude
            
                    if distance > 5 then
                        repeat
                            local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - shadowtrain.Position).Magnitude
                            Tween(shadowtrain.CFrame * CFrame.new(0,3,0))
                            task.wait()
                        until distance <= 5
                    end
            
                    fireclickdetector(shadowtrain.ClickDetector)
                end
            end)
        end
    end
    
    local function autoselfpunch()
        while AutoSelfPunch do task.wait()
            pcall(function()
                local shadowtrain = game:GetService("Workspace").Shop["Self Punch $130"].Head

                if game.Players.LocalPlayer.Backpack:FindFirstChild("Self Punch") or game.Players.LocalPlayer.Character:FindFirstChild("Self Punch") then
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Self Punch") then
                        game.Players.LocalPlayer.Backpack:FindFirstChild("Self Punch").Parent = game.Players.LocalPlayer.Character 
                        task.wait()
                    end
                    
                    repeat task.wait()
                        game.Players.LocalPlayer.Character:FindFirstChild("Self Punch"):Activate()
                    until game.Players.LocalPlayer.Character.Humanoid.Health <= 10 or AutoSelfPunch == false
                    game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
                    repeat wait() until game.Players.LocalPlayer.Character.Humanoid.Health >= 99 or AutoSelfPunch == false
                elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Self Punch") and not game.Players.LocalPlayer.Character:FindFirstChild("Self Punch") then
                    local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - shadowtrain.Position).Magnitude
            
                    if distance > 5 then
                        repeat
                            local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - shadowtrain.Position).Magnitude
                            Tween(shadowtrain.CFrame * CFrame.new(0,3,0))
                            task.wait()
                        until distance <= 5
                    end
            
                    fireclickdetector(shadowtrain.ClickDetector)
                end
            end)
        end
    end
    
    local function fastautoselfpunch()
        while FastAutoSelfPunch do task.wait()
            pcall(function()
                if game.Players.LocalPlayer.Backpack:FindFirstChild("Self Punch") or game.Players.LocalPlayer.Character:FindFirstChild("Self Punch") then
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Self Punch") then
                        game.Players.LocalPlayer.Backpack:FindFirstChild("Self Punch").Parent = game.Players.LocalPlayer.Character 
                        task.wait()
                    end
                    
                    repeat task.wait()
                        game.Players.LocalPlayer.Character:FindFirstChild("Self Punch"):Activate()
                    until game.Players.LocalPlayer.Character.Humanoid.Health <= 5 or FastAutoSelfPunch == false
                    game.Players.LocalPlayer.Character.Humanoid:UnequipTools()
                    game.Players.LocalPlayer.Character:ClearAllChildren()
                end
            end)
        end
    end
    
    local function autoroadwork()
        while AutoRoadWork do task.wait()
            if game.Players.LocalPlayer.Backpack:FindFirstChild("Roadwork Training") or game.Players.LocalPlayer.Character:FindFirstChild("Roadwork Training") then
                if game.Players.LocalPlayer.Backpack:FindFirstChild("Roadwork Training") then
                   game.Players.LocalPlayer.Backpack:FindFirstChild("Roadwork Training").Parent = game.Players.LocalPlayer.Character
                   task.wait()
                end
                
                game.Players.LocalPlayer.Character:FindFirstChild("Roadwork Training"):Activate()
                for i = 1,5 do
                    local v = game:GetService("Workspace").Roadwork[i]
                    
                    local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Position).Magnitude
        
                    if distance > 5 then
                        repeat
                            local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Position).Magnitude
                            Tween(v.CFrame)
                            task.wait()
                        until distance <= 5
                    end
                end
            elseif not game.Players.LocalPlayer.Status:FindFirstChild("Roadwork") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Roadwork Training") and not game.Players.LocalPlayer.Character:FindFirstChild("Roadwork Training") then
                local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - game:GetService("Workspace").Shop["Roadwork Training $130"].Head.Position).Magnitude
        
                if distance > 5 then
                    repeat
                        local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - game:GetService("Workspace").Shop["Roadwork Training $130"].Head.Position).Magnitude
                        Tween(game:GetService("Workspace").Shop["Roadwork Training $130"].Head.CFrame)
                        task.wait()
                    until distance <= 5
                end
                
                fireclickdetector(game:GetService("Workspace").Shop["Roadwork Training $130"].Head.ClickDetector)
            end
        end
    end
    
    function autojobs()
            while AutoJobs do task.wait()
                pcall(function()
                    if not game.Players.LocalPlayer:FindFirstChild("Mission") then
                        local TS = game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(3), {CFrame = CFrame.new(-1609.43213, 92.5563278, -144.275177)})
                        TS:Play()
                        TS.Completed:Wait()
                        fireclickdetector(game:GetService("Workspace").Corkboard.Board["Color this to paint the board"].ClickDetector)
                    else
                        if game.Players.LocalPlayer:FindFirstChild("Dirt") or game.Players.LocalPlayer:FindFirstChild("Poster") then
                            for _,v in pairs(getconnections(game.Players.LocalPlayer.PlayerGui.Mission.Frame.close.MouseButton1Click)) do
                                v.Function()
                            end
                        elseif game.Players.LocalPlayer.Character:FindFirstChild("Grocery") then
                            local TS = game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(3), {CFrame = CFrame.new(-1921.3241, 92.5563202, 201.322205)})
                            TS:Play()
                            TS.Completed:Wait()
                        end
                    end
                end)
            end
    end
    
    function betterautojobs()
            while BetterAutoJobs do task.wait()
                pcall(function()
                    if not game.Players.LocalPlayer:FindFirstChild("Mission") then
                        local TS = game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(TweenSpeed), {CFrame = CFrame.new(-1734.70801, 92.6061554, 1156.31775, 0.999422491, 1.17015053e-09, 0.0339807905, -9.66603131e-10, 1, -6.00650019e-09, -0.0339807905, 5.97018568e-09, 0.999422491)})
                        TS:Play()
                        TS.Completed:Wait()
                        fireclickdetector(game:GetService("Workspace").Corkboard2.Board["Color this to paint the board"].ClickDetector)
                    else
                        if game.Players.LocalPlayer:FindFirstChild("Mission") and game.Players.LocalPlayer.PlayerGui.Mission.Frame.Desc.Text == "Deliver the groceries to the residents" or game.Players.LocalPlayer.PlayerGui.Mission.Frame.Desc.Text == "Clean the docks of grime! (10/10)" then
                            for _,v in pairs(getconnections(game.Players.LocalPlayer.PlayerGui.Mission.Frame.close.MouseButton1Click)) do
                                v.Function()
                            end
                        elseif game.Players.LocalPlayer:FindFirstChild("Mission") and game.Players.LocalPlayer.PlayerGui.Mission.Frame.Desc.Text == "Deliver the boulder to the hole in the wall" then
                            local TS = game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(TweenSpeed), {CFrame = CFrame.new(-2145.64087, 88.6061554, 1482.83337, -0.000931585324, -2.89127158e-08, 0.999999583, 1.22299193e-09, 1, 2.89138669e-08, -0.999999583, 1.24992716e-09, -0.000931585324)})
                            TS:Play()
                            TS.Completed:Wait()
                            fireclickdetector(game:GetService("Workspace").rocks["Rusted Rock"].ClickDetector)
                            local SecondTS = game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(TweenSpeed), {CFrame = CFrame.new(-1878.96033, 81.6061554, 1479.54956, 0.0441947803, -6.90214241e-09, -0.999022961, 5.32841271e-10, 1, -6.8853212e-09, 0.999022961, -2.2802539e-10, 0.0441947803)})
                            SecondTS:Play()
                            SecondTS.Completed:Wait()
                        end
                    end
                end)
            end
    end
    
    local TPS = {
        ["Shop"] = GoToShop,
        ["Gym"] = GoToGym,
        ["Hospital"] = GoToHospital,
        ["Stat Checkup"] = GoToStatCheckup,
        ["KNC"] = GoToKNC,
        ["Construction Site"] = GoToConstructionSite,
        ["Gravity Chamber"] = GoToGravityChamber,
    }
    
    main:Toggle("Auto Jobs",false,function(Value)
        AutoJobs = Value
        
        if AutoJobs then
           autojobs() 
        end
    end)
    
    main:Toggle("Auto Jobs (DOCKS JB)",false,function(Value)
        BetterAutoJobs = Value
        
        if BetterAutoJobs then
           betterautojobs() 
        end
    end)
    
    main:Toggle("Auto Train",false,function(Value)
        AutoTools = Value
        
        if AutoTools then
            repeat task.wait() until SelectedTool ~=  nil
            autotools(SelectedTool)
        end
    end)
    
    main:Dropdown("Tools (Auto Train)",{"Situp","Pushup","Light Weight","Medium Weight","Heavy Weight"},function(Value)
        SelectedTool = Value
    end)
    
    main:Toggle("Auto Eat",false,function(Value)
        AutoEat = Value
        
        if AutoEat then
           autoeat() 
        end
    end)
    
    main:Slider("Auto Eat Percent",{min=0,max=100,def=HungerAmount},function(Value)
        HungerAmount = Value
    end)
    
    main:Toggle("Auto Spar Training",false,function(Value)
        AutoSparTraining = Value
        
        if AutoSparTraining then
            repeat task.wait() until SelectedBag ~= nil
            autospartrain(SelectedBag)
        end
    end)
    
    main:Dropdown("Boxing Bags (SPAR)",{1,2,3,4,5},function(Value)
        if BAGS[tonumber(Value)] ~= nil then
            SelectedBag = BAGS[tonumber(Value)]
        end
    end)
    
    main:Toggle("Auto Shadow Training",false,function(Value)
        AutoShadowTraining = Value
        
        if AutoShadowTraining then
           autoshadowtraining() 
        end
    end)
    
    main:Toggle("Auto Self Punch",false,function(Value)
        AutoSelfPunch = Value
        
        if AutoSelfPunch then
           autoselfpunch() 
        end
    end)
    
    main:Label("-- For Fast Version you need Self Punch already in inv --")
    
    main:Toggle("Fast Auto Self Punch",false,function(Value)
        FastAutoSelfPunch = Value
        
        if FastAutoSelfPunch then
           fastautoselfpunch() 
        end
    end)
    
    main:Toggle("Auto Roadwork",false,function(Value)
        AutoRoadWork = Value
        
        if AutoRoadWork then
           autoroadwork() 
        end
    end)
    
    main:Slider("Tween Speed",{def = getgenv().speed, min = 0, max = 500},function(Value)
        getgenv().speed = Value
    end)
    
    misc:Label("-- BANK CARD NEEDED FOR BANK FEATURES --")
    
    misc:Toggle("Auto Deposit",false,function(Value)
        AutoDeposit = Value
        
        if AutoDeposit then
           autodeposit() 
        end
    end)
    
    misc:Label("-- After typing the amount press enter --")
    
    misc:Textbox("Deposit Money",function(Value)
        local amt = tonumber(Value)
        
        if amt ~= nil then
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Withdraw"):FireServer("Deposit", amt)
        end
    end)
    
    misc:Textbox("Withdraw Money",function(Value)
        local amt = tonumber(Value)
        
        if amt ~= nil then
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Withdraw"):FireServer("Withdraw", amt)
        end
    end)
    
    misc:Toggle("Noclip",false,function(Value)
        NOCLIP = Value
        
        if NOCLIP then
           local Noclipping
           local function NoclipLoop()
        		if NOCLIP and plr.Character ~= nil then
        			for _, child in pairs(plr.Character:GetDescendants()) do
        				if child:IsA("BasePart") and child.CanCollide == true then
        					child.CanCollide = false
        				end
        			end
        		elseif NOCLIP == false then
        		    Noclipping:Disconnect()
        		    return
        		end
        	end
        	Noclipping = game.RunService.Stepped:Connect(NoclipLoop)
        end
    end)
    
    misc:Dropdown("Shop Items",workspace.Shop:GetChildren(),function(Value)
        itemselected = workspace.Shop[Value]
    end)
    
    misc:Button("Teleport to Item",function()
        if itemselected ~= nil then
            Tween(itemselected.Head.CFrame)
        end
    end)
    
    misc:Toggle("Auto Buy Item",false,function(Value)
        autobuyitem = Value
        
        if itemselected ~= nil and autobuyitem then
            while autobuyitem and task.wait() do
                if autobuyitem then
                  fireclickdetector(itemselected.Head.ClickDetector)
                  task.wait()
                   
                  if dupeItem then
                    for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                        if v:IsA("Tool") then
                            v.Parent = game.Players.LocalPlayer.Character
                        end
                    end 
                  end
                end
            end
        elseif autobuyitem == false then
            for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
                if v:IsA("Tool") then
                    v.Parent = game.Players.LocalPlayer.Backpack
                end
            end
        end
    end)
    
    misc:Toggle("Bypass Item Limit (autobuy)",false,function(Value)
        dupeItem = Value
    end)
    
    misc:Toggle("Anchor (unmoveable)",false,function(Value)
        game.Players.LocalPlayer.Character.HumanoidRootPart.Anchored = Value
    end)

    misc:Dropdown("Teleports",{"Shop","Gym","Hospital","Stat Checkup","KNC","Construction Site","Gravity Chamber"},function(Value)
        if TPS[Value] ~= nil then
           TPS[Value]() 
        end
    end)
    
    return win
end

local function Deepwoken_Dev(name)
    local win = library:Window(name,Color3.fromRGB())
    win.PromptDiscord("y7H2qGmNKd")
    
    local main = win:Tab("Main")
    main:Label("-- All features made by sweety#3848 --")
    main:Label("(script is currently in beta and still wip)")
    
    local tps = win:Tab("Teleports")
    local visuals = win:Tab("Visuals")
    
    local no_anims  
    local isSpectating = false
    local players = game:GetService("Players")
    local userInputService = game:GetService("UserInputService")
    local username
    local legit_autoloot
    local rage_autoloot
    local plrLabel
    local plrDD
    local autoParry
    local parryDistance
    local keyDebounce = false
    local PlayerESP
    local plrESPConnection
    local APToggle
    local apchars = {}
    local c = workspace.CurrentCamera
    local ps = game:GetService("Players")
    local lp = ps.LocalPlayer
    local rs = game:GetService("RunService")
    local allowed_animations = {
        "rbxassetid://10495930879", -- Sword Slash1 && Slash3
        "rbxassetid://10495930927", -- Sword Slash2
        "rbxassetid://10495931227", -- Sword, Club Running Attack
    
        "rbxassetid://10495932382", -- Sword, Rapier, Spear, Club Aerial Stab
    
        "rbxassetid://10495932450", -- TwoHanded Sword Slash1 && Slash3
        "rbxassetid://10495932503", -- TwoHanded Sword Slash2
    
        "rbxassetid://10495943900", -- Rapier Slash1 && Slash3
        "rbxassetid://10495943948", -- Rapier Slash2
    
        "rbxassetid://10495933846", -- Dagger Slash1 && Slash3
        "rbxassetid://10495933923", -- Dagger Slash2
        "rbxassetid://10495933537", -- Dagger, Legion Kata Running Attack
        "rbxassetid://10495934238", -- Dagger Aerial Stab
    
        "rbxassetid://10495934354", -- Greataxe && Hammer && TwoHanded Slash1
        "rbxassetid://10495934515", -- Greataxe && Hammer && TwoHanded Slash2
        "rbxassetid://10495934626", -- Greataxe && TwoHanded Greataxe Slash3 && Running Attack &&& Hammer Slash3 and Running Attack
        "rbxassetid://10495935670", -- Greataxe && TwoHanded Greataxe && Legion Kata Aerial Stab
    
        "rbxassetid://10495936565", -- Spear Slash1 && Slash3
        "rbxassetid://10495936682", -- Spear Slash2
        "rbxassetid://10495936961", -- Spear Running Attack
    
        "rbxassetid://10495937166", -- TwoHanded Spear Slash1 && Slash3
        "rbxassetid://10495937257", -- TwoHanded Spear Slash2
        "rbxassetid://10495937087", -- TwoHanded Spear Running Attack
    
        "rbxassetid://10495941011", -- Greatsword Slash1 && Slash3
        "rbxassetid://10495941091", -- Greatsword Slash2
        "rbxassetid://10495940225", -- Greatsword && TwoHanded Running Attack
    
        "rbxassetid://10495940500", -- TwoHanded Greatsword Slash1 && Slash3
        "rbxassetid://10495940398", -- TwoHanded Greatsword Slash2
    
        "rbxassetid://10495941409", -- Club (a special hammer or something) Slash1
        "rbxassetid://10495941515", -- Club Slash2
        "rbxassetid://10495941460", -- Club Slash3
    
        "rbxassetid://10495931657", -- TwoHanded Club Slash1
        "rbxassetid://10495931803", -- TwoHanded Club Slash2
        "rbxassetid://10495931908", -- TwoHanded Club Slash3
    
        "rbxassetid://10495943055", -- Legion Kata Slash1
        "rbxassetid://10495942809", -- Legion Kata Slash2
        "rbxassetid://10495942893", -- Legion Kata Slash3
    
        "rbxassetid://10495943843", -- Jus Karita Slash1
        "rbxassetid://10495943649", -- Jus Karita Slash2
        "rbxassetid://10495943734", -- Jus Karita Slash3
        "rbxassetid://10495943484", -- Jus Karita Running Attack
    
        "rbxassetid://10495948728", -- Railblade Slash1
        "rbxassetid://10495948813", -- Railblade Slash2
        "rbxassetid://10495949033", -- Railblade Slash3
    
        "rbxassetid://10495945813", -- TwoHand Railblade Slash1
        "rbxassetid://10495945662", -- TwoHand Railblade Slash2
    
        -- R
        --"rbxassetid://10495921369", -- Shattered Katana
    }

    local function PressKey(length)
        pcall(function()
            print("PressKey called with length", length)
            print("keyDebounce before:", keyDebounce)
            if not keyDebounce then
                keyDebounce = true
                
                -- adjust wait times based on range of animation lengths
                local wait_time
                if length <= 0.3 then
                    wait_time = 0.05
                elseif length > 0.3 and length <= 0.5 then
                    wait_time = 0.3
                elseif length > 0.5 and length <= 0.7 then
                    wait_time = 0.2
                else
                    wait_time = 0.3
                end
                
                task.wait(wait_time)
                game:GetService("VirtualInputManager"):SendKeyEvent(true, "F", false, game)
                task.wait(0.1)
                game:GetService("VirtualInputManager"):SendKeyEvent(false, "F", false, game)
                task.wait(0.1)
                keyDebounce = false
            else
                print("PressKey skipped due to keyDebounce")
            end
            print("keyDebounce after:", keyDebounce)
        end)
    end

    local function GetNearby()
        local closest = {}
        
        local range = parryDistance
        local local_player = game.Players.LocalPlayer
        local local_character = local_player.Character
        
        if not local_character:FindFirstChild("HumanoidRootPart") then
            return closest
        end
        
        local local_position = local_character.HumanoidRootPart.Position
        for _, player in ipairs(game.Players:GetPlayers()) do
            if player ~= local_player then
                local character = player.Character
                if character then
                    local humanoid = character:FindFirstChildOfClass("Humanoid")
                    if humanoid then
                        local distance = (character.HumanoidRootPart.Position - local_position).Magnitude
                        if distance <= range then
                            table.insert(closest, character)
                        end
                    end
                end
            end
        end
        
        return closest
    end
    
    local function AutoParry(track)
        local length = track.Length
        PressKey(length)
    end
    
    local function spectatePlayer(playerName)
        local targetPlayer = players:FindFirstChild(playerName)
        
        if targetPlayer == nil and plrLabel ~= nil then
            plrLabel:SetText("User Previously Selected Not Found!") 
        end
        
        while targetPlayer do
            local targetCharacter = targetPlayer.Character
            if targetCharacter then
                workspace.CurrentCamera.CameraSubject = targetCharacter.Humanoid
            end
            targetPlayer = players:FindFirstChild(playerName)
            if not isSpectating then
                break
            end
            task.wait()
        end
    end
    
    local function waitForGuiChild(gui, childName)
        local child = gui:WaitForChild(childName)
        while not child:IsDescendantOf(gui) do
            child = gui:WaitForChild(childName)
        end
        return child
    end

    local function getChestContent()
        local playerGui = game:GetService("Players").LocalPlayer.PlayerGui
        local choicePrompt = nil
        local contentFrame = nil
        local content = {}
    
        repeat
            choicePrompt = waitForGuiChild(playerGui, "ChoicePrompt")
            contentFrame = choicePrompt:FindFirstChild("ChoiceFrame") and waitForGuiChild(choicePrompt.ChoiceFrame, "Options")
            task.wait(0.1)
        until choicePrompt and contentFrame
    
        for _, v in pairs(contentFrame:GetChildren()) do
            if v:IsA("TextButton") then
                table.insert(content, v.Name)
            end
        end
    
        if #content == 0 then
            warn("No content found in chest.")
        end
    
        return content
    end
    
    local function openChest(chest)
        local localPlayer = game:GetService("Players").LocalPlayer
        local part = chest.Part
        local openDistance = 3
    
        while part and (localPlayer.Character.HumanoidRootPart.Position - part.Position).Magnitude <= openDistance do
            task.wait()
        end
    
        if part then
            game:GetService("VirtualInputManager"):SendKeyEvent(true, "E", false, game)
            task.wait(0.005)
            game:GetService("VirtualInputManager"):SendKeyEvent(false, "E", false, game)
            task.wait(0.1)

            local content = getChestContent()
            for _, item in ipairs(content) do
                game:GetService("Players").LocalPlayer:WaitForChild("PlayerGui"):WaitForChild("ChoicePrompt"):WaitForChild("Choice"):FireServer(item)
            end

            while part.Parent do
                task.wait()
            end
        end
    end
    
    local function chestTeleport()
        local localPlayer = game:GetService("Players").LocalPlayer
        local chests = workspace.Thrown
    
        for _, child in ipairs(chests:GetChildren()) do
            if child:IsA("Model") and child.Name == "Model" then
                local part = child.Part
                localPlayer.Character.HumanoidRootPart.CFrame = part.CFrame
                task.wait(0.1)
                game:GetService("VirtualInputManager"):SendKeyEvent(true, "E", false, game)
                task.wait(0.005)
                game:GetService("VirtualInputManager"):SendKeyEvent(false, "E", false, game)
                task.wait(0.1)
    
                local content = getChestContent()
                for _, item in ipairs(content) do
                    game:GetService("Players").LocalPlayer:WaitForChild("PlayerGui"):WaitForChild("ChoicePrompt"):WaitForChild("Choice"):FireServer(item)
                end
    
                while part.Parent do
                    task.wait()
                end
            end
        end
    end
    
    local function esp(p,cr)
        local h = cr:WaitForChild("Humanoid")
        local hrp = cr:WaitForChild("HumanoidRootPart")
    
        local text = Drawing.new("Text")
        text.Visible = false
        text.Center = true
        text.Outline = true 
        text.Font = 2
        text.Color = Color3.fromRGB(255,255,255)
        text.Size = 13
    
        local healthText = Drawing.new("Text")
        healthText.Visible = false
        healthText.Center = true
        healthText.Outline = true 
        healthText.Font = 2
        healthText.Color = Color3.fromRGB(255,255,255)
        healthText.Size = 13
    
        local c1
        local c2
        local c3
        local c4
    
        local function dc()
            text.Visible = false
            text:Remove()
            healthText.Visible = false
            healthText:Remove()
            if c1 then
                c1:Disconnect()
                c1 = nil 
            end
            if c2 then
                c2:Disconnect()
                c2 = nil 
            end
            if c3 then
                c3:Disconnect()
                c3 = nil 
            end
            if c4 then
                c4:Disconnect()
                c4 = nil
            end
        end
    
        c2 = cr.AncestryChanged:Connect(function(_,parent)
            if not parent then
                dc()
            end
        end)
    
        c3 = h.HealthChanged:Connect(function(v)
            if (v<=0) or (h:GetState() == Enum.HumanoidStateType.Dead) then
                dc()
            else
                healthText.Text = "Health: "..math.floor(h.Health)
                healthText.Visible = true
            end
        end)
    
        c1 = rs.RenderStepped:Connect(function()
            local hrp_pos,hrp_onscreen = c:WorldToViewportPoint(hrp.Position)
            if hrp_onscreen then
                text.Position = Vector2.new(hrp_pos.X, hrp_pos.Y)
                text.Text = p.Name
                text.Visible = true
    
                local health_pos = Vector2.new(hrp_pos.X, hrp_pos.Y + 15)
                healthText.Position = health_pos
                healthText.Visible = true
            else
                text.Visible = false
                healthText.Visible = false
            end
            
            if PlayerESP ~= true then
                dc()
            end
        end)
    end
    
    local function p_added(p)
        if p.Character then
            esp(p,p.Character)
        end
        p.CharacterAdded:Connect(function(cr)
            esp(p,cr)
        end)
    end

    APToggle = main:Toggle("Auto Parry (WIP)",false,function(Value)
        autoParry = Value
        
        while task.wait() and autoParry do
            local nearby_players = GetNearby()
            for _, player_character in ipairs(nearby_players) do
                local humanoid = player_character:FindFirstChildOfClass("Humanoid")
                if humanoid then
                    local success, result = pcall(function()
                        local animator = humanoid.Animator
                        local playing_tracks = animator:GetPlayingAnimationTracks()
                        for _, track in ipairs(playing_tracks) do
                            if table.find(allowed_animations, track.Animation.AnimationId) then
                                AutoParry(track)
                            end
                        end
                    end)
                    if not success then
                        warn("Character Error: " .. player_character.Name .. ": " .. result)
                    end
                end
            end
        end
    end)
    
    main:Slider("AP Detection Radius",{min=0,max=30,def=13},function(Value)
        parryDistance = Value
    end)

    main:Toggle("Auto Loot (Legit)",false,function(Value)
        legit_autoloot = Value
        
        while task.wait() and legit_autoloot do
            pcall(function()
                local chests = workspace.Thrown:GetChildren()
                for _, child in ipairs(chests) do
                    if child:IsA("Model") and child.Name == "Model" then
                        openChest(child)
                    end
                end
            end)
        end
    end)
    
    main:Toggle("Auto Loot (TP)",false,function(Value)
        rage_autoloot = Value
        
        while task.wait() and rage_autoloot do
            pcall(function()
                chestTeleport()
            end)
        end
    end)

    main:Toggle("No Anims",false,function(Value)
        no_anims = Value
        
        local player = game:GetService("Players").LocalPlayer
        local character = player.Character or player.CharacterAdded:Wait()
        local humanoid = character:FindFirstChild("Humanoid")
        
        if humanoid then
            -- Loop and stop all playing animations.
            while task.wait() and no_anims do
                local playingAnimations = humanoid:GetPlayingAnimationTracks()
                if #playingAnimations > 0 then
                    for _, track in pairs(playingAnimations) do
                        track:Stop()
                    end
                end
            end
        else
            print("no humanoid :) ")
        end
    end)
    
    plrLabel = main:Label("No User Selected")
    
    main:Bind("Spectate User",Enum.KeyCode.K,function()
        isSpectating = not isSpectating -- Cambiar el estado de isSpectating al presionar la tecla K
        if isSpectating then
            spectatePlayer(username)
        else
            local player = players.LocalPlayer
            local character = player.Character
            local humanoid = character and character:FindFirstChildOfClass("Humanoid")
            if humanoid then
                workspace.CurrentCamera.CameraSubject = humanoid
            end
        end
    end)
    
    main:Button("Teleport to User",function()
        local plrtoTpTo = game.Players:FindFirstChild(username)
        
        if plrtoTpTo then
            plr.Character.HumanoidRootPart.CFrame = plrtoTpTo.Character.HumanoidRootPart.CFrame * CFrame.new(0,0,4)
        else
            plrLabel:SetText("User Selected Not Found!")
        end
    end)
    
    plrDD = main:Dropdown("Select User",game.Players:GetPlayers(),function(Value)
        local plrtoTpTo = game.Players:FindFirstChild(Value)
        
        if plrtoTpTo then
            username = Value
            plrLabel:SetText("Selected "..Value)
        else
            plrLabel:SetText("User Selected Not Found!")
        end
    end)
    
    game.Players.ChildAdded:Connect(function()
        plrDD:SetOptions(game.Players:GetPlayers())
    end)
    
    game.Players.ChildRemoved:Connect(function()
        plrDD:SetOptions(game.Players:GetPlayers())
    end)

    tps:Label("-- Main Game --")

    tps:Button("Depths Whirlpool TP",function()
        local part = workspace.DepthsWhirlpool.Center.CFrame
        local player = game:GetService("Players").LocalPlayer.Character
        
        if player then
            player.HumanoidRootPart.CFrame = part
        end
    end)
    
    tps:Button("Primadon Campfire TP",function()
        local part = workspace.NPCs.MonkyCampfire.HumanoidRootPart
        local player = game:GetService("Players").LocalPlayer.Character
        
        if player then
            player.HumanoidRootPart.CFrame = part.CFrame
        end
    end)
    
    tps:Label("-- Depths --")
    
    tps:Button("Depths Elevator TP",function()
        local part = workspace.Mechanisms.TrialElevator.PlatformWood.CFrame
        local player = game:GetService("Players").LocalPlayer.Character
        
        if player then
            player.HumanoidRootPart.CFrame = part
        end
    end)
    
    visuals:Toggle("Player ESP",false,function(Value)
        PlayerESP = Value
        
        if PlayerESP then
            for i,p in next, ps:GetPlayers() do 
                if p ~= lp then
                    p_added(p)
                end
            end
            
            plrESPConnection = ps.PlayerAdded:Connect(p_added)
        else
            if plrESPConnection ~= nil then
               plrESPConnection:Disconnect() 
            end
        end

    end)
    
    return win
end

local function ZO()
    getgenv().ParryDist = 7
    
    if getgenv().AutoParry == nil then
       getgenv().AutoParry = true
    else
        getgenv().AutoParry = not getgenv().AutoParry
    end
    
    game:GetService("StarterGui"):SetCore("SendNotification",{
    	Title = "ZO AUTO PARRY", -- Required
    	Text = "Status: "..tostring(getgenv().AutoParry).."\nRange: "..tostring(ParryDist).."\n Execute again to toggle", -- Required
    })

    game:GetService("StarterGui"):SetCore("SendNotification",{
    	Title = "ZO AUTO PARRY", -- Required
    	Text = "Use Bracket Keys to increase distance [ ]", -- Required
    })
    
    local ParryConnection
    local holding = false
    local Players = game:GetService("Players")
    local oldNamecall
    local oldIndex
    local UIS = game:GetService("UserInputService")
    local UISConnection
    
    UISConnection = UIS.InputBegan:Connect(function(input,chat)
        if chat then return end
        if AutoParry ~= true then UISConnection:Disconnect() return end
        
        if input.KeyCode == Enum.KeyCode.LeftBracket then
            ParryDist = ParryDist + 1
            
            if ParryDist > 30 then
               ParryDist = 30
            end
            game:GetService("StarterGui"):SetCore("SendNotification",{
            	Title = "ZO AUTO PARRY", -- Required
            	Text = "Status: "..tostring(getgenv().AutoParry).."\nRange: "..tostring(ParryDist), -- Required
            })
        elseif input.KeyCode == Enum.KeyCode.RightBracket then
            ParryDist = ParryDist - 1
            
            if ParryDist < 0 then
               ParryDist = 0 
            end
            
            game:GetService("StarterGui"):SetCore("SendNotification",{
            	Title = "ZO AUTO PARRY", -- Required
            	Text = "Status: "..tostring(getgenv().AutoParry).."\nRange: "..tostring(ParryDist), -- Required
            })
        end
    end)
    
    local function GetAllAnims()
       local anims = {}
        
       local function GetSword(v)
       if v.Character:FindFirstChildOfClass("Tool") then
           if v.Character:FindFirstChildOfClass("Tool"):FindFirstChild("SwingAnimations") then
              return v.Character:FindFirstChildOfClass("Tool"):FindFirstChild("SwingAnimations")
           end
       else
           if #v.Backpack:GetChildren() == 1 then
              return v.Backpack:FindFirstChildOfClass("Tool").SwingAnimations
           else
              for i,v in pairs(v.Backpack:GetChildren()) do
                 if v:FindFirstChild("SwingAnimations") then
                    return v:FindFirstChild("SwingAnimations")
                 end
              end
           end
       end
       
       return nil
    end
        
       for i,v in pairs(game.Players:GetPlayers()) do
            if v ~= game.Players.LocalPlayer then
                local theSwordAnims = GetSword(v)
               
                if theSwordAnims ~= nil then
                    for i,v in pairs(theSwordAnims:GetChildren()) do
                        if table.find(anims,tostring(v.AnimationId)) == nil then
                            table.insert(anims,tostring(v.AnimationId))
                        end
                    end
                end
            end
       end
       return anims
    end
    
    local swordSwings = GetAllAnims()
    
    coroutine.resume(coroutine.create(function()
        while getgenv().AutoParry and task.wait(2) do
          pcall(function()
                swordSwings = GetAllAnims()
          end)
        end
    end))

    while task.wait() and getgenv().AutoParry do
         pcall(function()
            for i,v in pairs(game.Players:GetPlayers()) do
               if v.Character ~= nil then
                  local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Character.HumanoidRootPart.Position).Magnitude
                  
                  if distance <= ParryDist then
                      for i,v in pairs(v.Character.Humanoid:GetPlayingAnimationTracks()) do
                           if table.find(swordSwings,v.Animation.AnimationId) and holding == false and game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool") then
                               holding = true
                               local vim = game:GetService("VirtualInputManager")
                                vim:SendMouseButtonEvent(0, 500, 1, true, game, 1)
                                
                                task.spawn(function()
                                    pcall(function()
                                        task.wait(game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").PerfectBlockWindow.Value)
                                        vim:SendMouseButtonEvent(0, 500, 1, false, game, 1)
                                        holding = false
                                    end)
                                end)
                            end
                      end
                    end
               end
            end
        end)
    end
    return nil
end

local function BeyondVolleyBall(name)
    local win = library:Window(name,Color3.fromRGB(36, 209, 171))
    win.PromptDiscord("y7H2qGmNKd")
    
    local main = win:Tab("Main")
    
    local JP = plr.Character.Humanoid.JumpPower
    local FOV = game:GetService("Workspace").Camera.FieldOfView
    local Juggle = false
    local AutoRec = false
    local AutoRecRadius = 10
    local AutoServe = false
    local AutoSpikeBlock = false
    local AutoSpikeBlockRadius = 10
    local RecAnim = nil
    local RecAnimDebounce = false
    local BlockAnim = nil
    local SpikeAnim = nil
    local SpikeBlockAnimDebounce = false
    local Action = string.lower(plr.PlayerGui.PowerStam.Main.TextLabel.Text)
    local BallLanding = false
    local CurrentPWR = 0
    local JPToggle = false
    local BallPredictConnection
    
    local predictor = Instance.new("Part",workspace)

    predictor.Name = "Predictor"
    predictor.Anchored = true
    predictor.CanCollide = false
    predictor.Material = Enum.Material.Neon
    predictor.Size = Vector3.new(4,1,4)
    predictor.Transparency = 1
    
    local landaoe = Instance.new("Part",workspace)
    landaoe.Name = "Landaoe"
    landaoe.Anchored = true
    landaoe.CanCollide = false
    landaoe.Material = Enum.Material.Neon
    landaoe.Size = Vector3.new(3,0.01,3)
    landaoe.Color = Color3.fromRGB(52, 186, 137)
    landaoe.Transparency = 1
    
    local recdist = {
        [1] = 17,
        [2] = 25,
        [3] = 32,
        [4] = 39,
        [5] = 47,
        [6] = 54,
        [7] = 61,
        [8] = 69,
        [9] = 76,
        [10] = 83,
        [11] = 91,
        [12] = 98,
        [13] = 105,
        [14] = 113,
        [15] = 120,
    }
    
    local plr = game.Players.LocalPlayer

    local function ClosestBall()
       if game:GetService("Workspace").Balls:FindFirstChild("Ball") then
          local distances = {}
           
          for i,v in pairs(game:GetService("Workspace").Balls:GetChildren()) do
             if v.Name == "Ball" and v:IsA("Model") then
                table.insert(distances,(v.Ball.Position - plr.Character.HumanoidRootPart.Position).magnitude)
             end
          end

          table.sort(distances)
          
          for i,v in pairs(game:GetService("Workspace").Balls:GetChildren()) do
             if v.Name == "Ball" and v:IsA("Model") and v:FindFirstChild("Marker") == nil then
                if (v.Ball.Position - plr.Character.HumanoidRootPart.Position).magnitude <= distances[1] then
                   return v 
                end
             end
          end
       end
       
       return nil
    end
    
    local animfunc = false
    local function PlayAnim(anim)
        if anim == nil or animfunc then return end
        
        task.spawn(function()
            pcall(function()
                if anim.IsPlaying == false then
                   animfunc = true
                   anim:Play()
                   repeat task.wait() until anim.IsPlaying == false
                   task.wait(0.7)
                   animfunc = false
                end
            end)
        end)
    end
    
    main:Bind("Auto Receive",Enum.KeyCode.Five,function(Value)
        AutoRec = not AutoRec
        
        win.Notify({
            Title = "Auto Receive",
            Text = tostring(AutoRec),
        })
        
        while task.wait() and AutoRec do
            pcall(function()
                if ClosestBall() ~= nil and Juggle == false then
                    if plr.Character.Humanoid.WalkSpeed ~= 0 and (ClosestBall().Ball.Position - plr.Character.HumanoidRootPart.Position).magnitude <= AutoRecRadius and plr.Character.Humanoid.FloorMaterial ~= Enum.Material.Air then
                        PlayAnim(RecAnim)
                        game:GetService("ReplicatedStorage").ChangeStatus:FireServer("Receiving")
                    end
                end
            end)
        end
    end)
    
    main:Slider("Receive Radius",{min = 0, max = 30, def = 10},function(Value)
        AutoRecRadius = Value
    end)
    
    main:Label("(to swap spike/block press 1 like normally)")
    
    local autosetting = "Spike&Block"
    
    local function checksetting(val)
       if not autosetting:find(val) then
          return false
       else
           return true
       end
    end
    
    main:Toggle("Auto Spike/Block",false,function(Value)
        AutoSpikeBlock = Value
        
        while task.wait() and AutoSpikeBlock do
            pcall(function()
                if ClosestBall() ~= nil then
                    Action = string.lower(plr.PlayerGui.PowerStam.Main.TextLabel.Text)
                    if Action == "spike" and plr.Character.Humanoid.WalkSpeed == 0 and (ClosestBall().Ball.Position - plr.Character.HumanoidRootPart.Position).magnitude <= AutoSpikeBlockRadius and checksetting("Spike") then
                        PlayAnim(SpikeAnim)
                        game:GetService("ReplicatedStorage").ChangeStatus:FireServer("Spiking")
                    elseif Action == "block" and plr.Character.Humanoid.WalkSpeed == 0 and (ClosestBall().Ball.Position - plr.Character.HumanoidRootPart.Position).magnitude <= AutoSpikeBlockRadius and checksetting("Block") then
                        PlayAnim(BlockAnim)
                        game:GetService("ReplicatedStorage").ChangeStatus:FireServer("Blocking")
                    end
                end
            end)
        end
    end)
    
    main:Label("-- Spike&Block by default w--")
    
    main:Dropdown("Auto Spike/Block Setting",{"Spike","Block","Spike&Block"},function(Value)
        autosetting = Value
    end)
    
    main:Slider("Spike/Block Radius",{min = 0, max = 30, def = 10},function(Value)
        AutoSpikeBlockRadius = Value
    end)
    
    main:Label("-- Noticable/Risky --")
    
    main:Bind("Auto Juggle",Enum.KeyCode.CapsLock,function(Value)
        Juggle = not Juggle
        
        win.Notify({
            Title = "Auto Juggle",
            Text = tostring(Juggle),
        })
        
        while task.wait() and Juggle do
           pcall(function()
               if ClosestBall() ~= nil then
                   if plr.Character.Humanoid.WalkSpeed ~= 0 and (ClosestBall().Ball.Position - plr.Character.HumanoidRootPart.Position).magnitude <= AutoRecRadius then
                        PlayAnim(RecAnim)
                        game:GetService("ReplicatedStorage").ChangeStatus:FireServer("Diving") 
                   end
               end
           end)
        end
    end)
    
    main:Label("-- Visuals --")
    
    main:Label("(ball landing spot only predicts receiving/bumping the ball)")
    main:Toggle("Ball Landing Spot",false,function(Value)
        BallLanding = Value
        
        if not BallLanding then landaoe.Transparency = 1 landaoe.Anchored = true else landaoe.Transparency = 0 end
        
        while BallLanding and task.wait() do
            local x,y = pcall(function()
                landaoe.CFrame = plr.Character.HumanoidRootPart.CFrame * CFrame.new(0,-2.9,-recdist[tonumber(plr.PlayerGui.PowerStam.Main.Power.TextLabel.Text:split("/")[1])])
                task.wait()
            end)
            
            if not x then
               print(y) 
            end
        end
    end)
    
    main:Toggle("Ball Prediction",false,function(Value)
        BallPredict = Value
        
        if BallPredict then
            local RunService = game:GetService("RunService")
            
            BallPredictConnection = RunService.Heartbeat:Connect(function(dt)
                task.wait()
                if BallPredict then
               if ClosestBall() ~= nil then
                   local Ball = ClosestBall()
                   local Vel = Ball.Velocity
                   local Pos = Ball.Position
            
                   if Vel.Value.X < 1 and Vel.Value.Y < 1 and Vel.Value.Z < 1 then
                      task.wait()
                   elseif Vel.Value.X == 0 and Vel.Value.Y > 0 and Vel.Value.Z == 0 then
                       task.wait()
                   else
                       predictor.Transparency = 0.2
                        
                       local multi = 0.3
                      
                       repeat
                           pcall(function()
                               predictor.Anchored = false
                               task.wait()
                               if Vel.Value.Y <= 7 then multi = 0.1 elseif Vel.Value.Y <= 3 then multi = 0.05 end
                               predictor.Position = Vector3.new(Pos.Value.X,Ball.Shadow.Position.Y,Pos.Value.Z) + Vector3.new(Vel.Value.X, 0, Vel.Value.Z) * multi-- * times shit that will make it go forward to the position of the direction its headed
                               task.wait()
                               predictor.Anchored = true
                            end)
                            task.wait()
                       until Ball:FindFirstChild("Marker")
                       predictor.Transparency = 1
                   end
               end
               end
            end)
        else
            if BallPredictConnection ~= nil then
               BallPredictConnection:Disconnect()
               BallPredictConnection = nil
            end
        end
    end)
    
    main:Slider("Camera FOV",{min = 0, max = 120, def = game:GetService("Workspace").Camera.FieldOfView},function(Value)
        game:GetService("Workspace").Camera.FieldOfView = Value
    end)
    
    task.spawn(function()
        local HumanoidInstance = {}
        
        while task.wait(1) do
           pcall(function()
               if HumanoidInstance[plr.Character.Humanoid] == nil then
                  HumanoidInstance[plr.Character.Humanoid] = true
                  
                  RecAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Receive.Default)
                  BlockAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Block.Default)
                  SpikeAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Spike["Kenny RH"].Spike)
               end
           end)
           
           pcall(function()
                game:GetService("Workspace").Camera.FieldOfView = FOV
            end)
        end
    end)
    
    return win
end

local function Combat_Warriors(name)
    local win = library:Window(name,Color3.fromRGB(129, 32, 214))
    win.PromptDiscord("y7H2qGmNKd")
    
    local combat = win:Tab("Combat")
    local visuals = win:Tab("Visuals")
    local misc = win:Tab("Misc")
    
    local AutoParry
    local AutoParryDistance
    local Three60
    local parryDebounce = false
    local StompAura
    local clapped = {}
    local KillAura
    local airdropESP
    local labelHazards
    local items = {"Lever","OpenBearTrap"}
    local AntiParry
    local AutoSpawn
    local ParryChance
    local CPRange
    local InfStamina
    local stamhooked = false
    local NoRagdoll
    local NoJumpCD
    local HideName
    local AutoEquip
    local RemoveInflictedDMG
    local keycodeMap = {
    	["0"] = 0x30,
    	["1"] = 0x31,
    	["2"] = 0x32,
    	["3"] = 0x33,
    	["4"] = 0x34,
    	["5"] = 0x35,
    	["6"] = 0x36,
    	["7"] = 0x37,
    	["8"] = 0x38,
    	["9"] = 0x39,
    	["a"] = 0x41,
    	["b"] = 0x42,
    	["c"] = 0x43,
    	["d"] = 0x44,
    	["e"] = 0x45,
    	["f"] = 0x46,
    	["g"] = 0x47,
    	["h"] = 0x48,
    	["i"] = 0x49,
    	["j"] = 0x4A,
    	["k"] = 0x4B,
    	["l"] = 0x4C,
    	["m"] = 0x4D,
    	["n"] = 0x4E,
    	["o"] = 0x4F,
    	["p"] = 0x50,
    	["q"] = 0x51,
    	["r"] = 0x52,
    	["s"] = 0x53,
    	["t"] = 0x54,
    	["u"] = 0x55,
    	["v"] = 0x56,
    	["w"] = 0x57,
    	["x"] = 0x58,
    	["y"] = 0x59,
    	["z"] = 0x5A,
    	["enter"] = 0x0D,
    	["shift"] = 0x10,
    	["ctrl"] = 0x11,
    	["alt"] = 0x12,
    	["pause"] = 0x13,
    	["capslock"] = 0x14,
    	["spacebar"] = 0x20,
    	["space"] = 0x20,
    	["pageup"] = 0x21,
    	["pagedown"] = 0x22,
    	["end"] = 0x23,
    	["home"] = 0x24,
    	["left"] = 0x25,
    	["up"] = 0x26,
    	["right"] = 0x27,
    	["down"] = 0x28,
    	["insert"] = 0x2D,
    	["delete"] = 0x2E,
    	["f1"] = 0x70,
    	["f2"] = 0x71,
    	["f3"] = 0x72,
    	["f4"] = 0x73,
    	["f5"] = 0x74,
    	["f6"] = 0x75,
    	["f7"] = 0x76,
    	["f8"] = 0x77,
    	["f9"] = 0x78,
    	["f10"] = 0x79,
    	["f11"] = 0x7A,
    	["f12"] = 0x7B,
    }
    local remotes = {
        ["KA1"] = nil,
        ["KA2"] = nil,
        ["FallDMG"] = nil,
        ["IsCrouching"] = nil,
    }
        
    for i,v in pairs(game.ReplicatedStorage.Communication.Events:GetChildren()) do
    	v.Name = i
    	if i == 39 then
    	   remotes["KA1"] = v
    	elseif i == 40 then
    	    remotes["KA2"] = v    
    	elseif i == 27 then
    	    remotes["FallDMG"] = v
    	elseif i == 18 then
    	    remotes["IsCrouching"] = v
    	end
    end
    
    if getgc then
        pcall(function()
            for i,v in pairs(getgc(true)) do
                if typeof(v) == "table" and rawget(v, "kick") then
                    v.kick =  function()
                        return
                    end
                end
            
                if typeof(v) == 'table' and rawget(v, 'getIsBodyMoverCreatedByGame') then
                    v.getIsBodyMoverCreatedByGame = function()
                        return true
                    end
               end
               if typeof(v) == "table" and rawget(v, "randomDelayKick") then
                    v.randomDelayKick = function()
                        return wait(9e9)
                    end
                end
            end
            
            for i,v in pairs(getgc(true)) do
                    if typeof(v) == "table" and rawget(v, "connectCharacter") then
                        v.connectCharacter = function()
                            return
                        end
                    end
                end
                
                for _, Connection in next, getconnections(game:GetService("ScriptContext").Error) do
                Connection:Disable()
            end
            
            for _, Connection in next, getconnections(game:GetService("LogService").MessageOut) do
                Connection:Disable()
            end
            
            for _, Value in next, getgc(true) do
                if typeof(Value) == "table" and typeof(rawget(Value, "punish")) == "function" then
                    Hook = hookfunction(Value.punish, function(Self, ...)
                        local Arguments     = {...}
            
                        Arguments[2]        = "L"
            
                        return Hook(Self, table.unpack(Arguments))
                    end)
                end
            
                -- if type(Value) == "table" and rawget(Value, "Remote") then
                --     Value.Remote.Name = Value.Name
                -- end
            end
        end)
    end
    
    local function percentchance(x)
        if 100 * math.random() < x then 
            return true 
        else 
            return false 
        end 
    end
    
    local function GetClosestPlayer()
       local bestdistance,player = nil,nil
        
       pcall(function()
           for i,v in pairs(game.Players:GetPlayers()) do
               if v ~= game.Players.LocalPlayer then
               
               local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Character.HumanoidRootPart.Position).magnitude
               if bestdistance == nil and player == nil then
                   bestdistance = distance
                   player = v
               elseif bestdistance > distance then
                   player = v
                   bestdistance = distance
               end
	       end
           end
           
           if bestdistance > AutoParryDistance then
              player = nil 
           end
        end)
       return player
    end
    
    local function GetMainWeapon()
        local haha
        local currentplayer = GetClosestPlayer()
        pcall(function()
            if currentplayer ~= nil then
                local weapon = currentplayer.Character:FindFirstChildOfClass("Tool")
                
                if weapon then
                    local folder = weapon:FindFirstChild("Hitboxes")
                    if folder then
                       haha = folder
                    end
                end
            end
        end)
        return haha,currentplayer
    end
    
    local function GetSurroundingPlayers(size)
        local weapon = game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool")
                
        if weapon then
            local folder = weapon:FindFirstChild("Hitboxes")
            if folder then
                local OV = OverlapParams.new()
    
                local partsInRange = workspace:GetPartBoundsInBox(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame, Vector3.new(size,size,size), OV)
                local players = {}
    
                for i,v in pairs(partsInRange) do
                    if tostring(v) == "Torso" then
                        table.insert(players,v)
                    end
                end
                
                if #players > 0 then
                   return players 
                end
                return nil
            end
        end
    end
    
    local function DrawLibTxt(item)
        local camera = workspace.CurrentCamera
        local runservice = game:GetService("RunService")
        if item:FindFirstChild("MARKED") then return end
    
        local drawTXT = Drawing.new("Text")
        drawTXT.Visible = false
        drawTXT.Center = true
        drawTXT.Outline = true
        drawTXT.Font = 1
        drawTXT.Color = Color3.fromRGB(255,255,255)
        drawTXT.Size = 13
    
        local BV = Instance.new("BoolValue",item)
        BV.Name = "MARKED"
    
        local touchDebounce = false
    
        local renderstepped = true
        task.spawn(function()
            while task.wait() and renderstepped do
                if item and airdropESP then
                    local PosPart
                    
                    if item:IsA("Part") then
                        PosPart = item
                    end
                    
                    workspace.DescendantRemoving:Connect(function(child)
                        if child == PosPart then
                            renderstepped:Disconnect()
                            pcall(function()
                                drawTXT:Remove()
                                game.Debris:AddItem(BV,0.01)
                            end) 
                        end
                    end)
                    
                    local drop_pos, drop_onscreen = camera:WorldToViewportPoint(PosPart.Position)
        
                    if drop_onscreen then
                        drawTXT.Position = Vector2.new(drop_pos.X, drop_pos.Y)
                        if item.Name == "Base" then item.Name = "Airdrop" end
                        drawTXT.Text = item.Name
                        drawTXT.Visible = true
                    else 
                        drawTXT.Visible = false
                    end
                else
                    drawTXT.Visible = false
                    drawTXT:Remove()
                    if BV then
                        BV:Destroy() 
                    end
                    renderstepped = false
                    game.Debris:AddItem(BV,0.01)
                    return
                end
            end
        end)
    end

    if hookmetamethod then
        local LocalPlayer = game.Players.LocalPlayer
    	local oldhmmi
    	local oldhmmnc
    	oldhmmi = hookmetamethod(game, "__index", function(self, method)
    		if self == LocalPlayer and method:lower() == "kick" then
    			return error("Expected ':' not '.' calling member function Kick", 2)
    		end
    		return oldhmmi(self, method)
    	end)
    	oldhmmnc = hookmetamethod(game, "__namecall", function(self, ...)
    		if self == LocalPlayer and getnamecallmethod():lower() == "kick" then
    			return
    		elseif getnamecallmethod():lower() == "fireserver" and self.ClassName:find("Remote") and self.Name == "GotHitRE" and RemoveInflictedDMG or getnamecallmethod():lower() == "fireserver" and self.ClassName:find("Remote") and self == remotes["FallDMG"] and RemoveInflictedDMG then
    		    return
    		
    		end
    		return oldhmmnc(self, ...)
    	end) 
    end
    
    local function Parry()
        if not parryDebounce then
            parryDebounce = true
            local code = keycodeMap["f"]
            local clickDelay = 0.1
            local releaseDelay = 0.1
            keypress(code)
            task.wait(0.1)
            keyrelease(code)
            task.wait(0.1)
            parryDebounce = false
        end
    end
    
    combat:Toggle("Auto Parry",false,function(Value)
        AutoParry = Value
        
        if AutoParry then
            while task.wait() and AutoParry do
                local hitbox,currentplayer = GetMainWeapon()
                local hooked = false
                
                if hitbox ~= nil then
                    while task.wait() and AutoParry do
                        local curhit,curplr = GetMainWeapon()
                        if curhit ~= hitbox or curplr ~= currentplayer then break end
                        if hooked == false then
                            hooked = true
                            for i,v in pairs(hitbox:GetChildren()) do
                                if clapped[v] == nil then
                                    clapped[v] = true
                                    
                                    local RootPart1 = plr.Character.HumanoidRootPart
                                    local RootPart2 = currentplayer.Character.HumanoidRootPart
                                    local ObjectSpace = RootPart2.CFrame:inverse() * RootPart1.CFrame
                                    local connection = v.ChildAdded:Connect(function(child)
                                        if curhit ~= hitbox or curplr ~= currentplayer or AutoParry == false then connection:Disconnect() clapped[v] = nil return end
                                        local distance = (plr.Character.HumanoidRootPart.Position - currentplayer.Character.HumanoidRootPart.Position).magnitude
                                        
                                        if distance > CPRange then
                                            connection:Disconnect()
                                            clapped[v] = nil
                                            return
                                        end
                                        
                                        local ShouldParry = percentchance(ParryChance)
                                        
                                        if ObjectSpace.Z > 0 and Three60 and ShouldParry then
                                           for i = 1, 10 do
                                                lookAt(currentplayer.Character,plr.Character.HumanoidRootPart)
                                           end
                                           
                                        end
                                        
                                        if tonumber(child.Name) ~= nil and ShouldParry then
                                            if ObjectSpace.Z > 0 and Three60 == false then return end
                                            Parry()
                                        end
                                    end)
                                end
                            end
                        end
                    end
                end
            end
        end
    end)
    
    combat:Toggle("360 Parry Mode",false,function(Value)
        Three60 = Value
    end)
    
    combat:Slider("Parry Chance",{min=0,max=100,def=100},function(Value)
        ParryChance = Value
    end)
    
    combat:Slider("ClosestPlayer Range",{min=0,max=20,def=10},function(Value)
        CPRange = Value
    end)
    
    combat:Toggle("Stomp Aura",false,function(Value)
        StompAura = Value
        
        if StompAura then
            while StompAura and task.wait() do
                if GetSurroundingPlayers(CPRange) ~= nil then
                    for i,v in pairs(GetSurroundingPlayers(CPRange)) do
                        if v.Parent.Humanoid.Health <= 20 and v.Parent.Humanoid > 0 then
                            keypress(keycodeMap["q"])
                            task.wait(0.1)
                            keyrelease(keycodeMap["q"])
                            task.wait(0.1) 
                        end
                    end
                end
            end
        end
    end)
    
    combat:Toggle("Kill Aura",false,function(Value)
        KillAura = Value
        
        if KillAura then
            while KillAura and task.wait() do
                if GetSurroundingPlayers(CPRange) ~= nil then
                   for i,v in pairs(GetSurroundingPlayers(CPRange)) do
                        pcall(function()
                            local weapon = game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool")
                           
                            local args = {
                                [1] = weapon,
                                [2] = 1
                            }
                            
                            remotes["KA1"]:FireServer(unpack(args))
                            
                        
                            local args = {
                                [1] = weapon,
                                [2] = v,
                                [3] = weapon.Hitboxes.Hitbox,
                                [4] = game.Players.LocalPlayer.Character.HumanoidRootPart.Position,
                                [5] = CFrame.new(-0.500015259, -0.311161041, -0.136207581, -0.432186365, -0.00502037397, 0.90177083, -0.00317717483, 0.999986887, 0.00404445687, -0.901779115, -0.00111734157, -0.432196587),
                                [6] = Vector3.new(-0.9732194542884827, 1.0414090922949981e-08, -0.2298780232667923),
                                [7] = Vector3.new(-0.7864461541175842, 0.12430082261562347, 0.6050220727920532),
                                [8] = Vector3.new(0.4321863651275635, 0.0050203739665448666, -0.901770830154419)
                            }
                            
                            remotes["KA2"]:FireServer(unpack(args)) 
                            task.wait(tonumber("0."..tostring(math.random(3,5))))
                        end)
                   end
                end
            end
        end
    end)
    
    visuals:Toggle("Airdrop ESP",false,function(Value)
        airdropESP = Value
        
        if airdropESP then
            while airdropESP and task.wait() do
                for i,v in pairs(workspace.Airdrops:GetChildren()) do
                    DrawLibTxt(v.Crate.Base)
                end
            end
        end
    end)
    
    misc:Toggle("Auto Spawn",false,function(Value)
        AutoSpawn = Value
        
        if AutoSpawn then
            while AutoSpawn and task.wait() do
                pcall(function()
                    if game:GetService("Players").LocalPlayer.PlayerGui.RoactUI.MainMenu ~= nil then
                        task.wait(1)
                        SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.RoactUI.MainMenu.PagesScreenGuiContainer.PlayPage_MainMenu.MainButtonsFrameContainer.PlayPage_MainMenu.Button.ButtonDetection,"Function")
                    end
                end)
            end
        end
    end)
    
    misc:Toggle("No Jump Cooldown",false,function(Value)
        NoJumpCD = Value
        
        for i,v in pairs(getgc(true)) do
            if typeof(v) == "table" and rawget(v, "getCanJump") then
                local old = v.getCanJump
                if NoJumpCD then
                    v.getCanJump = function()
                        return true
                    end
                else
                    return old()
                end
            end
        end
    end)
    
    local Old
    misc:Toggle("Inf Stamina",false,function(Value)
       InfStamina = Value
        
        for i,v in pairs(getgc(true)) do
            if typeof(v) == "table" and rawget(v, "_setStamina") then
                local old = v._setStamina
                v._setStamina = function(among, us)
                    if InfStamina then
                        among._stamina = math.huge
                        among._staminaChangedSignal:Fire(150)
                    else
                        return old(among, us)
                    end
                end
            end
         end
    end)
    
    misc:Toggle("No Dash Cooldown",false,function(Value)
        NoDashCD = Value
        
        if NoDashCD then
            local DashConst = require(game:GetService("ReplicatedStorage").Shared.Source.Dash.DashConstants)
            rawset(DashConst, 'DASH_COOLDOWN', 0)
        else
            local DashConst = require(game:GetService("ReplicatedStorage").Shared.Source.Dash.DashConstants)
            rawset(DashConst, 'DASH_COOLDOWN', 3)
        end
    end)

    misc:Toggle("No Ragdoll",false,function(Value)
        NoRagdoll = Value
        
        for i,v in pairs(getgc(true)) do
            if typeof(v) == "table" and rawget(v, "toggleRagdoll") then
                local old = v.toggleRagdoll
                v.toggleRagdoll = function(...)
                    if NoRagdoll then
                        return
                    else
                        return old(...)
                    end
                end
            end
        end
    end)
    
    misc:Toggle("Disable Hazards",false,function(Value)
        RemoveInflictedDMG = Value
    end)
    
    misc:Toggle("Hide Name",false,function(Value)
        HideName = Value
        
        if HideName == false then
           remotes["IsCrouching"]:FireServer(false)
           return 
        end
        
        while HideName and task.wait() do
            remotes["IsCrouching"]:FireServer(true)
        end
    end)
    
    combat:Toggle("Auto Equip",false,function(Value)
        AutoEquip = Value
        
        while AutoEquip and task.wait() do
            pcall(
                function()
                    for i, v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                        if v:IsA("Tool") then
                            if v:FindFirstChild("Hitboxes") ~= nil then
                                if AutoEquip and not game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool") then
                                    v.Parent = game.Players.LocalPlayer.Character
                                end
                            end
                        end
                    end
                end
            ) 
        end
    end)
    
    return win
end

local function Goal(name)
    local win = library:Window(name,Color3.fromRGB(129, 32, 214))
    win.PromptDiscord("y7H2qGmNKd")
    
    local main = win:Tab("Main")
    local visual = win:Tab("Visuals")
    
    local Power
    local InfEnergy,InfStamina = false,false
    local AutoCharge = false
    local vim = game:GetService("VirtualInputManager")
    local sandman = false
    local trail = false
    local BlockHB,BlockRange = false,10
    local ContestHB,ContestRange = false,10
    local AutoGK = false
    local ChargeKickAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.ChargeKick)
    local KickAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Kick)
    local EmuAnims = true
    local STM = 0
    local BetterTackle = false
    local HN = false
    local BallMagDist = 10
    local BallMag = false
    
    local function GetClosestGoal(teamcolor)
        local bestpos,obj = nil,nil
        local teams = {
            ["Away"] = "Cyan",
            ["Home"] = "Persimmon",
        }
        
        if teams[teamcolor] == nil then
           for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
                if v.Name == "Goal" then
                   local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Aimer.Position).magnitude
                    
                   if bestpos == nil and obj == nil then
                        bestpos = distance
                        obj = v
                   elseif distance < bestpos then
                       bestpos = distance
                       obj = v
                   end
                end
           end
        elseif teams[teamcolor] ~= nil then
            for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
                if v.Name == "Goal" and tostring(v:FindFirstChild("Part").BrickColor) == teams[teamcolor] then
                   local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Aimer.Position).magnitude
                    
                   if bestpos == nil and obj == nil then
                        bestpos = distance
                        obj = v
                   elseif distance < bestpos then
                       bestpos = distance
                       obj = v
                   end
                end
            end
        end
       
       return obj
    end
    
    local function GetClosestBall()
        if game.Workspace:FindFirstChild("Bola") ~= nil then
            for i,v in pairs(game.Workspace:GetChildren()) do
                if v.Name == "Bola" then
                    local left = (game.Players.LocalPlayer.Character["Left Leg"].Position - v.Position).magnitude
                    local right = (game.Players.LocalPlayer.Character["Right Leg"].Position - v.Position).magnitude 
                    local choice = "Right Leg"                
                    
                    
                    if left <= BallMagDist and right <= BallMagDist then
                        if left < right then
                            choice = "Left Leg"
                        end
                        return v,choice
                    end
                end
            end
        end
        return nil,nil
    end
    
    main:Toggle("Emulate Animations",true,function(Value)
        EmuAnims = Value
    end)
    
    main:Bind("Legit Aimbot",Enum.KeyCode.Unknown,function(Value)
        if game.Players.LocalPlayer.Character:FindFirstChild("Bola") == nil then return end
        if Value == Enum.KeyCode.Unknown then return end
        
        if EmuAnims then
            ChargeKickAnim:Play()
            task.wait(0.5)
            ChargeKickAnim:Stop()
            KickAnim:Play()
        else
            KickAnim:Play()
        end
        
        local cFrame1 = GetClosestGoal(game.Players.LocalPlayer.Character.Humanoid.Teammate.Value).Aimer.CFrame
        local instance1 = GetClosestGoal(game.Players.LocalPlayer.Character.Humanoid.Teammate.Value)
        local hiddenNil1 = nil -- games can detect if this is missing, but likely won't.
        local hiddenNil2 = nil -- games can detect if this is missing, but likely won't.
        local hiddenNil3 = nil -- games can detect if this is missing, but likely won't.
        
        local remote = game:GetService("ReplicatedStorage").Events.M1B
        remote:FireServer(Power, cFrame1, instance1, false, hiddenNil1, hiddenNil2, hiddenNil3)
    end)
    
    main:Bind("Rage Aimbot",Enum.KeyCode.Unknown,function(Value)
        if game.Players.LocalPlayer.Character:FindFirstChild("Bola") == nil then return end
        if Value == Enum.KeyCode.Unknown then return end
        
        if EmuAnims then
            ChargeKickAnim:Play()
            task.wait(0.5)
            ChargeKickAnim:Stop()
            KickAnim:Play()
        else
            KickAnim:Play()
        end
        
        local ohString1 = "QKick"
        local ohNil2 = nil
        local ohNumber3 = Power
        local ohCFrame4 = GetClosestGoal(game.Players.LocalPlayer.Character.Humanoid.Teammate.Value).Aimer.CFrame
        
        game:GetService("ReplicatedStorage").Events.ClientUpdate:FireServer(ohString1, ohNil2, ohNumber3, ohCFrame4)
    end)
    
    main:Label("Ball Mag: if radius too high it might not work as well")
    
    main:Bind("Ball Magnet",Enum.KeyCode.Unknown,function(Value)
        if Value == Enum.KeyCode.Unknown then return end
        BallMag = not BallMag
        
        win.Notify({
            Title = "Ball Magnet",
            Text = tostring(BallMag)
        })
        
        while task.wait() and BallMag do
            local Ball,Leg = GetClosestBall()
            
            if Ball ~= nil and Leg ~= nil then
                if Ball == GetClosestBall() then
                  Ball.CFrame = game.Players.LocalPlayer.Character[Leg].CFrame 
                end
            end
        end
    end)
    
    main:Slider("Ball Magnet Radius",{min=0,max=30,def=BallMagDist},function(Value)
        BallMagDist = Value
    end)
    
    main:Toggle("Auto Charge to Selected Power",false,function(Value)
        AutoCharge = Value
        
        while task.wait() and AutoCharge do
            getrenv()._G.Power = Power 
        end
    end)
    
    main:Slider("Power",{min=0,max=100,def=100},function(Value)
        Power = Value
    end)
    
    main:Label("PK is used when you get the ball first time")
    main:Label("you can also kick ahead then get it then use PK")
    
    main:Bind("Perfect Kick (PK)",Enum.KeyCode.Unknown,function(Value)
        if game.Players.LocalPlayer.Character:FindFirstChild("Bola") == nil then return end
        if Value == Enum.KeyCode.Unknown then return end
        
        if EmuAnims then
            ChargeKickAnim:Play()
            task.wait(0.5)
            ChargeKickAnim:Stop()
            KickAnim:Play()
        else
            KickAnim:Play()
        end
        
        game.Players.LocalPlayer.PlayerGui.ClickMeter.Manager.RemoteEvent:FireServer("Perfect","Middle")
        game.Players.LocalPlayer.PlayerGui.ClickMeter.BarActivate.Value = true
    end)
    
    main:Bind("Kick Up",Enum.KeyCode.R,function(Value)
        if game.Players.LocalPlayer.Character:FindFirstChild("Bola") == nil then return end

        local ohInstance1 = game:GetService("Players").LocalPlayer
        local ohString2 = "VV"
        local ohBoolean3 = false
        
        game:GetService("ReplicatedStorage").Events.RealisticMovement:FireServer(ohInstance1, ohString2, ohBoolean3)
    end)
    
    main:Toggle("Inf Energy",InfEnergy,function(Value)
        InfEnergy = Value
        
        while InfEnergy and task.wait() do
            getrenv()._G.Energy = 1000 
        end
    end)
    
    main:Toggle("Inf Stamina",InfStamina,function(Value)
        InfStamina = Value

        while InfStamina and task.wait() do
           getrenv()._G.Stamina = 100 
        end
    end)
    
    main:Toggle("Further Slide Tackle",false,function(Value)
        BetterTackle = Value
        
        while task.wait() and BetterTackle do
          pcall(function()
              if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Carrinho") then
                  local bv = game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Carrinho") 
                  bv.Velocity = bv.Velocity * STM
                  repeat task.wait() until game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Carrinho") == nil
              end
          end)
        end
    end)
    
    main:Slider("Slide Tackle Multiplier",{min=0,max=100,def =0},function(Value)
        local newValue = tonumber("1."..tostring(Value))
                
        if Value == 100 then
            newValue = 2 
        end
        
        STM = newValue
    end)
    
    main:Toggle("Block Range Extender",false,function(Value)
        BlockHB = Value
        local oldsize = Vector3.new(4.8, 4.288, 3.92)
        
        if BlockHB == false then plr.Character.BlockRange.Size = oldsize end
        
        while BlockHB and task.wait() do
            if BlockHB then
                pcall(function()
                    plr.Character.BlockRange.Size = Vector3.new(BlockRange,BlockRange,BlockRange)
                end)
            end
        end
    end)
    
    main:Slider("Block Size",{min=0,max=30,def = BlockRange},function(Value)
        BlockRange = Value
    end)
    
    main:Toggle("Contest Range Extender",false,function(Value)
        ContestHB = Value
        local oldsize = Vector3.new(8.5, 8.5, 8.5)
        
        if ContestHB == false then plr.Character.ContestRange.Size = oldsize end
        
        while ContestHB and task.wait() do
            if ContestHB then
                pcall(function()
                    plr.Character.ContestRange.Size = Vector3.new(ContestRange,ContestRange,ContestRange)
                end)
            end
        end
    end)
    
    main:Slider("Contest Size",{min=0,max=30,def = ContestRange},function(Value)
        ContestRange = Value
    end)
    
    main:Bind("GK Spam Block",Enum.KeyCode.Unknown,function(Value)
        if Value == Enum.KeyCode.Unknown then return end
        AutoGK = not AutoGK
        
        win.Notify({
            Title = "GK Spam Block",
            Text = tostring(AutoGK)
        })
        
        local haha = {"A","D"}
        
        if plr.Character.Humanoid:FindFirstChild("GK") == nil and AutoGK then
            game:GetService("ReplicatedStorage").Events.ClientUpdate:FireServer("GK")
        end
        
        while AutoGK and task.wait() do
            local ohString1 = "Block"
            local ohString2 = haha[math.random(1,2)]
            
            game:GetService("ReplicatedStorage").Events.ClientUpdate:FireServer(ohString1, ohString2)
        end
    end)
    
    main:Toggle("Hide Name",false,function(Value)
        HN = Value
        
        while HN and task.wait() do
           pcall(function()
                plr.Character.Head.NameUI:Destroy()
           end)
        end
    end)
    
    local macrodebounce = false
    
    main:Bind("Spin Right",Enum.KeyCode.Z,function(Value)
        if game.Players.LocalPlayer.Character:FindFirstChild("Bola") == nil then return end
        if not macrodebounce then
            macrodebounce = true
            local vim = game:GetService("VirtualInputManager")
            vim:SendKeyEvent(true, "X", false, game)
            task.wait()
            vim:SendKeyEvent(false, "X", false, game)
            task.wait(0.1)
            vim:SendKeyEvent(true, "C", false, game)
            task.wait()
            vim:SendKeyEvent(false, "C", false, game)
            task.wait(0.1)
            vim:SendKeyEvent(true, Enum.KeyCode.Space, false, game)
            task.wait()
            vim:SendKeyEvent(false, Enum.KeyCode.Space, false, game)
            task.wait(0.1)
            macrodebounce = false
        end
    end)
    
    main:Bind("Spin Left",Enum.KeyCode.C,function(Value)
        if game.Players.LocalPlayer.Character:FindFirstChild("Bola") == nil then return end
        
        if not macrodebounce then
            macrodebounce = true
            local vim = game:GetService("VirtualInputManager")
            vim:SendKeyEvent(true, "X", false, game)
            task.wait()
            vim:SendKeyEvent(false, "X", false, game)
            task.wait(0.1)
            vim:SendKeyEvent(true, "Z", false, game)
            task.wait()
            vim:SendKeyEvent(false, "Z", false, game)
            task.wait(0.1)
            vim:SendKeyEvent(true, Enum.KeyCode.Space, false, game)
            task.wait()
            vim:SendKeyEvent(false, Enum.KeyCode.Space, false, game)
            task.wait(0.1)
            macrodebounce = false
        end
    end)
    
    visual:Label("-- Visual (others can see it) --")

    visual:Toggle("White Trail",false,function(Value)
        trail = Value
        
        while task.wait() and trail do
            local hiddenNil1 = nil -- games can detect if this is missing, but likely won't.
        
            local remote = game:GetService("ReplicatedStorage").Events.ClientUpdate
            remote:FireServer("JumpEffect", hiddenNil1)
        end
    end)
    
    task.spawn(function()
        local HumanoidInstance = {}
        
        while task.wait(1) do
           pcall(function()
               if HumanoidInstance[plr.Character.Humanoid] == nil then
                  HumanoidInstance[plr.Character.Humanoid] = true
                  
                  ChargeKickAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.ChargeKick)
                  KickAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Kick)
               end
           end)
        end
    end)
    
    return win
end

local function Neo(name)
    local win = library:Window(name,Color3.fromRGB(220, 20, 60))
    win.PromptDiscord("y7H2qGmNKd")
    
    local enhance = win:Tab("Enhancements")
    local gaming = win:Tab("Fuck Game")
    local misc = win:Tab("Misc")
    
    local ReplicatedStorage = game:GetService("ReplicatedStorage")
    local SharedM = require(ReplicatedStorage.Dependencies.Shared)
    local SkillM = require(ReplicatedStorage.Dependencies.Skills)
    local kickpower = 100
    local skillpower = 100
    local trickCD = true
    local trickDebounce = false
    local BetterS = false
    local BetterM = false
    local ballrape = false
    local fuckamt = 100
    local SilentAim = false
    local SuperLegit = true
    local shatBall = false
    local StepSis = false
    local antistaff = false
    local bgsize = 1000
    local rgsize = 1000
    local rsize = 1000
    local bsize = 1000
    local RedGoal = false
    local BlueGoal = false
    local RedGK = false
    local BlueGK = false
    local gsize = 1000
    local gksize = 1000
    local greach = false
    local gkreach = false
    local oldG = Vector3.new(49.5247, 0.00122438, 12.9519)
    local oldGK = Vector3.new(6.26138, 9.24843, 6.91)
    local nerfed = Vector3.new(0.001,0.001,0.001)
    local CameraFOVToggle
    local FOV

    local function StepSisStuck()
            while StepSis do task.wait()
                pcall(function()
                game:GetService("Workspace").Objects.Balls.PLAIN_BALL.HITBOX_BALL.CFrame = game.Players.LocalPlayer.Character["Left Leg"].CFrame
        local args = {
            [1] = workspace:WaitForChild("Objects"):WaitForChild("Balls"):WaitForChild("PLAIN_BALL"),
            [2] = game.Players.LocalPlayer.Character
        }
        
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Pass"):FireServer(unpack(args))
        end)
        end
    end
    
    local function GetTarget(action)
        local SilentAimOpts
        local SvS = 12767114985
        
        if game.PlaceId ~= SvS then
            SilentAimOpts = {
                ["Blue"] = {Vector3.new(793, 13, -896),game:GetService("Workspace").Map.BlueGoal.GoalZone.Position,Vector3.new(791, 13, -855)},
                ["Red"] = {Vector3.new(131, 13, -854),game:GetService("Workspace").Map.RedGoal.GoalZone.Position,Vector3.new(134, 13, -894)},
            }
        else
            SilentAimOpts = {
                ["Blue"] = {Vector3.new(1088, -34, 2972),game:GetService("Workspace").Map.BlueGoal.GoalZone.Position,Vector3.new(1088, -34, 3013)},
                ["Red"] = {Vector3.new(248, -34, 3013),game:GetService("Workspace").Map.RedGoal.GoalZone.Position,Vector3.new(246, -34, 2971)},
            }
        end
        
        local function GetFarthestPos(color)
            local bestDist
            local bestPos
            local GK = game:GetService("Workspace").Objects.Goalkeepers:FindFirstChild(color.."Goalkeeper")
            
            for _,v in pairs(SilentAimOpts[color]) do
                local distance = (GK.HumanoidRootPart.Position - v).magnitude
                
                if bestDist == nil then
                    bestDist = distance
                    bestPos = v
                elseif distance > bestDist then
                    bestDist = distance
                    bestPos = v
                end
            end
            
            return bestPos
        end
        
        local pos
        
        if SilentAim == false then
           local part = Instance.new("Part")
           part.CFrame = plr.Character.HumanoidRootPart.CFrame * CFrame.new(0,0,-10)
           pos = part.Position
           game.Debris:AddItem(part,0.01)
        else
            for i,v in pairs(workspace.Map:GetChildren()) do
               if v.Name:find("Goal") and v.Name ~= game.Players.LocalPlayer.Character.Team.Value.."Goal" then
                    pos = GetFarthestPos(v.Name:split("Goal")[1])
               end
            end
        end
        
        return pos
    end
    
    local function Kick(opt)
       if trickDebounce and trickCD then return end
       
       if trickCD and trickDebounce == false then
            trickDebounce = true
       end
       
       local args = {
            [1] = SharedM.getNearestBall(plr.Character.HumanoidRootPart),
            [2] = CFrame.lookAt(plr.Character.HumanoidRootPart.Position, GetTarget()),
            [3] = kickpower,
            [4] = "Straight"
        }
        local kickAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Player.Kick)
        local chargeAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Player.KickCharge)
        
           if args[1] == nil then trickDebounce = false return end
           if SuperLegit then
               chargeAnim:Play()
               task.wait(1)
               chargeAnim:Stop()
           end
           kickAnim:Play()
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Kick"):FireServer(unpack(args))
            if trickCD then task.wait(1) end
       
       trickDebounce = false
    end
    
    local function Long_Shot(opt)
       if trickDebounce and trickCD then return end
       
       if trickCD and trickDebounce == false then
            trickDebounce = true
       end
       
       local args = {
            [1] = SharedM.getNearestBall(plr.Character.HumanoidRootPart),
            [2] = CFrame.lookAt(plr.Character.HumanoidRootPart.Position, GetTarget("Long Shot")),
            [3] = skillpower,
            [4] = "Long Shot"
        }
        
           local kickAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Player.Kick)
        local chargeAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Player.KickCharge)
        
           if args[1] == nil then trickDebounce = false return end
           if SuperLegit then
               chargeAnim:Play()
               task.wait(1)
               chargeAnim:Stop()
           end
           kickAnim:Play()
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Kick"):FireServer(unpack(args))
            if trickCD then task.wait(1) end
       
       trickDebounce = false
    end
    
    local function Gyro_Shot(opt)
       if trickDebounce and trickCD then return end
       
       if trickCD and trickDebounce == false then
            trickDebounce = true
       end
       
       local args = {
            [1] = SharedM.getNearestBall(plr.Character.HumanoidRootPart),
            [2] = CFrame.lookAt(plr.Character.HumanoidRootPart.Position, GetTarget("Gyro Shot")),
            [3] = skillpower,
            [4] = "Gyro Shot"
        }
        
           local kickAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Player.Kick)
        local chargeAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Player.KickCharge)
        
           if args[1] == nil then trickDebounce = false return end
           if SuperLegit then
               chargeAnim:Play()
               task.wait(1)
               chargeAnim:Stop()
           end
           kickAnim:Play()
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Kick"):FireServer(unpack(args))
            if trickCD then task.wait(1) end

       
       trickDebounce = false
    end
    
    local function Bicycle_Kick(opt)
        if trickDebounce and trickCD then return end
       
       if trickCD and trickDebounce == false then
            trickDebounce = true
       end
       
      local args = {
            [1] = SharedM.getNearestBall(plr.Character.HumanoidRootPart),
            [2] = CFrame.lookAt(plr.Character.HumanoidRootPart.Position, GetTarget("Left Curved")),
            [3] = skillpower,
            [4] = "Bicycle"
        }
        
    if SilentAim then
       args[2] = args[2] * CFrame.Angles(0,math.rad(180),0) 
    end

      local kickAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Player.BicycleKick)
        local chargeAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Player.BicycleKickCharge)
        
          if args[1] == nil then trickDebounce = false return end
          if SuperLegit then
              chargeAnim:Play()
              task.wait(0.5)
              chargeAnim:Stop()
          end
          kickAnim:Play()
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Kick"):FireServer(unpack(args))
            if trickCD then task.wait(1) end

       
      trickDebounce = false
    end
    
    local function Big_Bang_Drive()
        if trickDebounce and trickCD then return end
       
       if trickCD and trickDebounce == false then
            trickDebounce = true
       end
       
       local args = {
            [1] = SharedM.getNearestBall(plr.Character.HumanoidRootPart),
            [2] = CFrame.lookAt(plr.Character.HumanoidRootPart.Position, GetTarget("Left Curved")),
            [3] = skillpower,
            [4] = "Big Bang Drive"
        }
        

        if SilentAim then
            args[2] = args[2] * CFrame.Angles(0,math.rad(180),0) 
         end

       local kickAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Player.BicycleKick)
        local chargeAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Player.BicycleKickCharge)
        
           if args[1] == nil then trickDebounce = false return end
           if SuperLegit then
               chargeAnim:Play()
               task.wait(0.5)
               chargeAnim:Stop()
           end
           kickAnim:Play()
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Kick"):FireServer(unpack(args))
            if trickCD then task.wait(1) end

       
       trickDebounce = false
    end

    local function Kaiser_Impact()
        if trickDebounce and trickCD then return end
       
       if trickCD and trickDebounce == false then
            trickDebounce = true
       end
       
       local args = {
            [1] = SharedM.getNearestBall(plr.Character.HumanoidRootPart),
            [2] = CFrame.lookAt(plr.Character.HumanoidRootPart.Position, GetTarget("Left Curved")),
            [3] = skillpower,
            [4] = "Kaiser Impact"
        }
        

       local kickAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Player.KaiserImpact)
        local chargeAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Player.KaiserImpactCharge)
        
           if args[1] == nil then trickDebounce = false return end
           if SuperLegit then
               chargeAnim:Play()
               task.wait(0.5)
               chargeAnim:Stop()
           end
           kickAnim:Play()
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Kick"):FireServer(unpack(args))
            if trickCD then task.wait(1) end

       
       trickDebounce = false
    end
    
    local function Left_Curved(opt)
       if trickDebounce and trickCD then return end
       
       if trickCD and trickDebounce == false then
            trickDebounce = true
       end
       
       local args = {
            [1] = SharedM.getNearestBall(plr.Character.HumanoidRootPart),
            [2] = CFrame.lookAt(plr.Character.HumanoidRootPart.Position, GetTarget("Left Curved")),
            [3] = skillpower,
            [4] = "Left Curved"
        }
        

        local chargeAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Player.KickCharge)
        
           if args[1] == nil then trickDebounce = false return end
           if SuperLegit then
               chargeAnim:Play()
               task.wait(1)
               chargeAnim:Stop()
           end
           kickAnim:Play()
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Kick"):FireServer(unpack(args))
            if trickCD then task.wait(1) end

       
       trickDebounce = false
    end
    
    local function Right_Curved(opt)
       if trickDebounce and trickCD then return end
       
       if trickCD and trickDebounce == false then
            trickDebounce = true
       end
       
       local args = {
            [1] = SharedM.getNearestBall(plr.Character.HumanoidRootPart),
            [2] = CFrame.lookAt(plr.Character.HumanoidRootPart.Position, GetTarget("Right Curved")),
            [3] = skillpower,
            [4] = "Right Curved"
        }
        
          local kickAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Player.Kick)
        local chargeAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Player.KickCharge)
        
           if args[1] == nil then trickDebounce = false return end
           if SuperLegit then
               chargeAnim:Play()
               task.wait(1)
               chargeAnim:Stop()
           end
           kickAnim:Play()
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Kick"):FireServer(unpack(args))
            if trickCD then task.wait(1) end
       
       trickDebounce = false
    end
    
    local function Lift()
        if trickDebounce and trickCD then return end
       
       if trickCD and trickDebounce == false then
            trickDebounce = true
       end
        
        local args = {
            [1] = SharedM.getNearestBall(plr.Character.HumanoidRootPart),
            [2] = Vector3.new(0.08331020921468735, 0.75, -0.5171419978141785),
            [3] = true
        }
        
        if args[1] == nil then trickDebounce = false return end
        
        local liftAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Animations.Player.Dribbles["Lift"..math.random(1,4)])
        if SuperLegit then
           liftAnim:Play()
       end
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Dribble"):FireServer(unpack(args))
        if trickCD then task.wait(1) end
       
       trickDebounce = false
    end
    
    local function Balling()
       game:GetService("Workspace").Objects.Balls.PLAIN_BALL.HITBOX_BALL.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
    end
    
    enhance:Label("silent aim: better mechanics on and use kick")
    enhance:Toggle("Silent Aim",false,function(Value)
        SilentAim = Value
    end)
    
    enhance:Toggle("Remulate Anims",true,function(Value)
        SuperLegit = Value
    end)
    
    enhance:Label("Note: keybinds on unknown need to be set yourself")
    
    enhance:Toggle("Trick Cooldown",true,function(Value)
        trickCD = Value
    end)
    
    enhance:Toggle("Better Mechanics",true,function(Value)
        BetterM = Value
    end)
    
    enhance:Toggle("Better Slots",true,function(Value)
        BetterS = Value
    end)
    
    enhance:Label("-- Better Mechanics --")
    
    enhance:Bind("Kick",Enum.UserInputType.MouseButton2,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        if BetterM == false then return end
        
        Kick()
    end)
    
    enhance:Slider("Kick Power",{min=0,max=100,def=kickpower},function(Value)
        kickpower = Value
    end)
    
    enhance:Bind("Tackle",Enum.KeyCode.Unknown,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        p2 = require(game:GetService("Players").LocalPlayer.PlayerScripts.Client.ClientGlobal)
        local l_humanoid__5 = p2.humanoid
        local l__anims__6 = p2.anims
        p2.anims:stopAnims({
        	Sprint = true, 
        	WalkAnim = true
        });
        l__anims__6.Tackle:Play(0.05, nil, 0.7);
        p2.tackling = true;
        delay(1.3, function()
        	p2.tackling = false;
        end);
        wait(0.24);
        local v9 = Instance.new("BodyVelocity");
        v9.Name = "TackleVelocity";
        v9.Velocity = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.LookVector * 65;
        v9.MaxForce = Vector3.new(200000, 0, 200000);
        v9.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart;
        game.Debris:AddItem(v9, 0.9);
        game.Players.LocalPlayer.Character.HumanoidRootPart.Tackle1.ParticleEmitter.Enabled = true;
        game.Players.LocalPlayer.Character.HumanoidRootPart.Tackle2.ParticleEmitter.Enabled = true;
        p2.remotes.Ball.Tackle:FireServer(SharedM.getNearestBall(plr.Character.HumanoidRootPart), game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame);
        wait(0.9);
        game.Players.LocalPlayer.Character.HumanoidRootPart.Tackle1.ParticleEmitter.Enabled = false;
        game.Players.LocalPlayer.Character.HumanoidRootPart.Tackle2.ParticleEmitter.Enabled = false;
    end)
    
    enhance:Bind("Left Dribble",Enum.KeyCode.Unknown,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        local args = {
            [1] = SharedM.getNearestBall(plr.Character.HumanoidRootPart),
            [2] = -game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.RightVector
        }
        
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Dribble"):FireServer(unpack(args))
    end)
    
    enhance:Bind("Right Dribble",Enum.KeyCode.Unknown,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        local args = {
            [1] = SharedM.getNearestBall(plr.Character.HumanoidRootPart),
            [2] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.RightVector
        }
        
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Dribble"):FireServer(unpack(args))
    end)
    
    enhance:Bind("Auto Steal",Enum.KeyCode.Unknown,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        AutoSteal = not AutoSteal
        
        win.Notify({
            Title = "Auto Steal",
            Text = tostring(AutoSteal),
        })
        
        while task.wait() and AutoSteal do
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Tackle"):FireServer(SharedM.getNearestBall(plr.Character.HumanoidRootPart),game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
        end
    end)
    
    enhance:Bind("Lift",Enum.KeyCode.Unknown,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        Lift()
    end)
    
    enhance:Label("Using too many flows may get you kicked for fast")
    
    enhance:Bind("Flow (Stackable)",Enum.KeyCode.Unknown,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        game:GetService("ReplicatedStorage").Remotes.UI.ActivateFlow:FireServer()
    end)
    
    enhance:Label("-- Better Skills --")
    
    enhance:Slider("Skill Power",{min=0,max=100,def=skillpower},function(Value)
        skillpower = Value
    end)
    
    enhance:Bind("Long Shot",Enum.KeyCode.Z,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        
        Long_Shot()
    end)
    
    enhance:Bind("Gyro Shot",Enum.KeyCode.C,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        
        Gyro_Shot()
    end)
    
    enhance:Bind("Bicycle Kick",Enum.KeyCode.T,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        
        Bicycle_Kick()
    end)
    
    enhance:Bind("Big Bang Drive",Enum.KeyCode.Y,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        
        Big_Bang_Drive()
    end)

    enhance:Bind("Kaiser Impact",Enum.KeyCode.N,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        
        Kaiser_Impact()
    end)
    
    enhance:Bind("Left Curved Shot",Enum.KeyCode.V,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        
        local args = {
            [1] = SharedM.getNearestBall(plr.Character.HumanoidRootPart),
            [2] = CFrame.new(plr.Character.HumanoidRootPart.Position, GetTarget("Left Curved")),
            [3] = skillpower,
            [4] = "Left Curved"
        }
        
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Kick"):FireServer(unpack(args))
    end)
    
    enhance:Bind("Right Curved Shot",Enum.KeyCode.B,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        
        local args = {
            [1] = SharedM.getNearestBall(plr.Character.HumanoidRootPart),
            [2] = CFrame.new(plr.Character.HumanoidRootPart.Position, GetTarget("Right Curved")),
            [3] = skillpower,
            [4] = "Right Curved"
        }
        
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Kick"):FireServer(unpack(args))
    end)
    
    enhance:Label("-- Better Slots --")
    
    enhance:Bind("Slot 1",Enum.KeyCode.One,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        if BetterS == false then return end
        
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Skill"):InvokeServer(SharedM.getNearestBall(plr.Character.HumanoidRootPart),1)
    end)
    
    enhance:Bind("Slot 2",Enum.KeyCode.Two,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        if BetterS == false then return end
        
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Skill"):InvokeServer(SharedM.getNearestBall(plr.Character.HumanoidRootPart),2)
    end)
    
    enhance:Bind("Slot 3",Enum.KeyCode.Three,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        if BetterS == false then return end
        
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Skill"):InvokeServer(SharedM.getNearestBall(plr.Character.HumanoidRootPart),3)
    end)
    
    enhance:Bind("Slot 4",Enum.KeyCode.Four,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        if BetterS == false then return end
        
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Skill"):InvokeServer(SharedM.getNearestBall(plr.Character.HumanoidRootPart),4)
    end)
    
    enhance:Bind("Slot 5",Enum.KeyCode.Five,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        if BetterS == false then return end
        
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Skill"):InvokeServer(SharedM.getNearestBall(plr.Character.HumanoidRootPart),5)
    end)
    
    gaming:Label("-- Fun Shit --")
    
    gaming:Bind("Ball Rape",Enum.KeyCode.Unknown,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        
        ballrape = not ballrape

        while ballrape do task.wait()
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Dribble"):FireServer(SharedM.getNearestBall(plr.Character.HumanoidRootPart),Vector3.new(0,0,0))
        end
    end)
    
    gaming:Bind("IFrame Bind",Enum.KeyCode.Unknown,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        local args = {
            [1] = SharedM.getNearestBall(plr.Character.HumanoidRootPart),
            [2] = Vector3.new(100, 20, 100),
            [3] = true
        }
        
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Dribble"):FireServer(unpack(args))
    end)
    
    gaming:Bind("Bring Ball",Enum.KeyCode.Unknown,function(Value)
        if Enum.KeyCode.Unknown == Value then return end
        Balling()
    end)
    
    gaming:Label("ty bbg lofi")
    gaming:Toggle("Shit Ball on Goal",false,function(Value)
        shatBall = Value
        task.spawn(function()
            pcall(function()
        if game.Players.LocalPlayer.Character.Team.Value == "Blue" then
        while shatBall do task.wait(0.05)
            game:GetService("Workspace").Map.RedGoal.GoalZone.Size = Vector3.new(bsize,bsize,bsize)
        task.wait()
        local args = {
            [1] = workspace:WaitForChild("Objects"):WaitForChild("Balls"):WaitForChild("PLAIN_BALL"),
            [2] = CFrame.new(Vector3.new(0, 0, 0), Vector3.new(0, 0, 0)),
            [3] = 0,
            [4] = "Straight"
        }
        
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Kick"):FireServer(unpack(args))
        task.wait(0.1)
        end
        end
        end)
        end)
        task.spawn(function()
            pcall(function()
        if game.Players.LocalPlayer.Character.Team.Value == "Red" then
            while shatBall do task.wait(0.05)
                game:GetService("Workspace").Map.BlueGoal.GoalZone.Size = Vector3.new(rsize,rsize,rsize)
        task.wait()
        local args = {
            [1] = workspace:WaitForChild("Objects"):WaitForChild("Balls"):WaitForChild("PLAIN_BALL"),
            [2] = CFrame.new(Vector3.new(0, 0, 0), Vector3.new(0, 0, 0)),
            [3] = 0,
            [4] = "Straight"
        }
        
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Ball"):WaitForChild("Kick"):FireServer(unpack(args))
        task.wait(0.1)
        end
        end
        end)
        end)
        while task.wait() and shatBall do
            pcall(function()
                game:GetService("Workspace").Objects.Balls.PLAIN_BALL.HITBOX_BALL:FindFirstChild("OwnershipArrow"):Destroy() 
            end)
            end
    end)
    
    gaming:Toggle("Apply Gorilla Glue!",false,function(Value)
        local togglefunc = StepSisStuck
        StepSis = Value
        if StepSis then
            pcall(function()
            togglefunc()
        end)
    end
    end)

    gaming:Label("-- Reach/Hitbox Extenders --")

    gaming:Toggle("Goal Reach",false,function(Value)
        greach = Value
        
        if greach == false then
           pcall(function()
               game:GetService("Workspace").Map.BlueGoal.GoalZone.Size = oldG
               game:GetService("Workspace").Map.RedGoal.GoalZone.Size = oldG
           end)
           return 
        end
        
        while greach and task.wait(0.1) do
            if greach == false then break end
            pcall(function()
                if game.Players.LocalPlayer.Character.Team.Value == "Blue" and greach then
                    game:GetService("Workspace").Map.RedGoal.GoalZone.Size = Vector3.new(gsize,gsize,gsize)
                    game:GetService("Workspace").Map.BlueGoal.GoalZone.Size = nerfed
                elseif game.Players.LocalPlayer.Character.Team.Value == "Red" and greach then
                    game:GetService("Workspace").Map.BlueGoal.GoalZone.Size = Vector3.new(gsize,gsize,gsize)
                    game:GetService("Workspace").Map.RedGoal.GoalZone.Size = nerfed
                end
            end)
        end
    end)
    
    gaming:Slider("Goal Size",{min=0,max=3000,def=1000},function(Value)
        gsize = Value
    end)
    
    gaming:Toggle("Goalie Reach",false,function(Value)
        gkreach = Value
        
        if gkreach == false then
           pcall(function()
               game:GetService("Workspace").Objects.Goalkeepers.BlueGoalkeeper.BlockHitbox.Size = oldGK
               game:GetService("Workspace").Objects.Goalkeepers.RedGoalkeeper.BlockHitbox.Size = oldGK
           end)
           return 
        end
        
        while gkreach and task.wait(0.1) do
            if gkreach == false then break end
            pcall(function()
                if game.Players.LocalPlayer.Character.Team.Value == "Blue" and gkreach then
                    game:GetService("Workspace").Objects.Goalkeepers.BlueGoalkeeper.BlockHitbox.Size = Vector3.new(gsize,gsize,gsize)
                    game:GetService("Workspace").Objects.Goalkeepers.RedGoalkeeper.BlockHitbox.Size = nerfed
                elseif game.Players.LocalPlayer.Character.Team.Value == "Red" and gkreach then
                    game:GetService("Workspace").Objects.Goalkeepers.RedGoalkeeper.BlockHitbox.Size = Vector3.new(gsize,gsize,gsize)
                    game:GetService("Workspace").Objects.Goalkeepers.BlueGoalkeeper.BlockHitbox.Size = nerfed
                end
            end)
        end
    end)

    gaming:Slider("Goal Size",{min=0,max=3000,def=1000},function(Value)
        gksize = Value
    end)

    misc:Toggle("Anti Staff",false,function(Value)
        antistaff = Value
        
        while antistaff do task.wait(3)
            pcall(function()
                for i,v in pairs(game.Players:GetPlayers()) do
                    if v:GetRankInGroup(12600063) >= 2 then
                        game.Players.LocalPlayer:Kick(v:GetRoleInGroup(12600063).." Joined.\n\nGroupID:"..v:GetRankInGroup(12600063))
                    end
                end
            end)
        end
    end)
    
    misc:Button("Spawn Ball (practice)",function()
        game.Players:Chat("/sb")
    end)
    
    misc:Button("Buy all Skills",false,function()
        local remotes = {}
        for i,v in pairs(game:GetService("Players").LocalPlayer.ReplicatedData.SkillTree:GetChildren()) do 
            if v:IsA("BoolValue") then
            table.insert(remotes,v.Name)
            end
        end
        task.wait()
        for _,v in pairs(remotes) do task.wait(1)
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("UI"):WaitForChild("UnlockSkill"):InvokeServer(v) 
        end
    end)
    
    misc:Toggle("Camera FOV",false,function(Value)
        CameraFOVToggle = Value
    end)

    misc:Slider("Camera FOV",{min = 0, max = 120, def = game:GetService("Workspace").Camera.FieldOfView},function(Value)
        FOV = Value
    end)
    
    misc:Label("-- EPIC AURAS --")
    
    local function ToggleFX(Bool,FXType)
        if Bool then
            if FXType:IsA("Part") then
                local E = FXType:Clone()
            
                E.Parent = game.Players.LocalPlayer.Character.Torso
                
                local weld = Instance.new("Weld")
                
                weld.Part0 = E
                
                weld.Part1 = game.Players.LocalPlayer.Character.Torso
                
                
                weld.Part0.CFrame = 
                game.Players.LocalPlayer.Character.Torso.CFrame
                
                weld.Parent = weld.Part1 
            elseif FXType:IsA("Folder") then
                for i,v in pairs(FXType:GetChildren()) do
                    if not v:IsA("Part") then
                        v:Clone().Parent = game.Players.LocalPlayer.Character.Torso
                    else
                        local E = v:Clone()
            
                        E.Parent = game.Players.LocalPlayer.Character.Torso
                        
                        local weld = Instance.new("Weld")
                        
                        weld.Part0 = E
                        
                        weld.Part1 = game.Players.LocalPlayer.Character.Torso
                        
                        
                        weld.Part0.CFrame = 
                        game.Players.LocalPlayer.Character.Torso.CFrame
                        
                        weld.Parent = weld.Part1 
                    end
                end
            end
        else
            for i,v in pairs(game.Players.LocalPlayer.Character.Torso:GetChildren()) do
                if v:IsA("ParticleEmitter") or v:IsA("SpotLight") or v:IsA("Part") then
                    v:Destroy()
                end
            end
        end
    end
    
    for i,v in pairs(game:GetService("ReplicatedStorage").ReplicatedAssets.Effects.Auras:GetChildren()) do
        local hahabool,connection = false,nil
        
        misc:Toggle(v.Name,hahabool,function(Value)
            hahabool = Value
            
            if connection == nil and hahabool then
                connection = game.Players.LocalPlayer.CharacterAdded:Connect(function()
                    if hahabool then
                        repeat task.wait() until game.Players.LocalPlayer.Character:FindFirstChild("Torso") ~= nil
                        ToggleFX(hahabool,v)
                    else
                        connection:Disconnect()
                    end
                end)
            end
            
            ToggleFX(hahabool,v)
        end)
    end
    
    task.spawn(function()
        while task.wait() do
            if game:GetService("Workspace").Camera.FieldOfView ~= FOV and CameraFOVToggle then
               game:GetService("Workspace").Camera.FieldOfView = FOV 
            end
            
            pcall(function()
                if plr.Character.HumanoidRootPart:FindFirstChild("Bypassed") then
                   bypassbool = Instance.new("BoolValue",plr.Character.HumanoidRootPart)
                   bypassbool.Name = "Bypassed"
                   velocity = Instance.new("BodyVelocity")
                    velocity.Name = "TackleVelocity"
                    velocity.Parent = game.Players.LocalPlayer.Character.Torso 
                    velocity.MaxForce = Vector3.new(0,0,0)
                end
            end)
        end
    end)
    
    return win
end

local function Fakewoken(name)
    local win = library:Window(name,Color3.fromRGB(227, 23, 84))
    win.PromptDiscord("y7H2qGmNKd")
    
    getgenv().speed = 35
    
    local combat = win:Tab("Combat")
    local esp = win:Tab("ESP")
    local misc = win:Tab("Misc")
    local tps = win:Tab("Teleports")
    
    local NoStun = false
    local SilentSpeed = false
    local SSMulti = 4
    local AutoParry = false
    local AutoParry = false
    local parryDebounce = false
    local Ignore = {"Parry","Idle","Block","TrueParry1","TrueParry2","Run"}
    local ParryDistance = 13
    local RIOF = false
    
    getgenv().ESP,Settings = true,{
        HealthBar = true,
        Distance = true,
    }
    
    local function round(n)
        return math.floor(n * 10) / 10
    end
    
    local function Parry(length,echar)
       pcall(function()
           if not parryDebounce then
               local hitDB
               local weapon = echar:FindFirstChildOfClass("Model")
               
               if weapon ~= nil then
                  if weapon.Type.Value == "Dagger" then
                      hitDB = round(length/2.1)
                  elseif weapon.Type.Value == "Battleaxe" then
                      hitDB = round(length/1.2)
                  elseif weapon.Type.Value == "Sword" then
                      hitDB = round(length/1.56)
                  elseif weapon.Type.Value == "BaseFist" then
                      hitDB = round(length/1.56)
                  elseif weapon.Type.Value == "Spear" then
                      hitDB = round(length/1.56)
                  else
                      hitDB = round(length/1.56)
                  end
              else
                  return
              end
               parryDebounce = true
        	   
        	   if RIOF == false then
        	        task.wait(hitDB)
                    game:GetService("VirtualInputManager"):SendKeyEvent(true, "F", false, game)
                	task.wait(0.05)
                    game:GetService("VirtualInputManager"):SendKeyEvent(false, "F", false, game)
                    task.wait(0.05)
               else
                   game:GetService("VirtualInputManager"):SendKeyEvent(true, "Q", false, game)
                	task.wait(0.05)
                    game:GetService("VirtualInputManager"):SendKeyEvent(false, "Q", false, game)
                    task.wait(0.05)
        	   end
        	   
        	   parryDebounce = false
            end
        end)
    end
    
    local function GetAllAnims()
        local anims = {}
        pcall(function()
            for i,v in pairs(game:GetService("ReplicatedStorage").Assets.Animations.Weapons:GetDescendants()) do
                if table.find(Ignore,v.Name) == nil and v:IsA("Animation") then
                   table.insert(anims,v.AnimationId)
                end
            end
            
            for i,v in pairs(game:GetService("ReplicatedStorage").Assets.Animations.Mantras:GetDescendants()) do
                if table.find(Ignore,v.Name) == nil and v:IsA("Animation") then
                   table.insert(anims,v.AnimationId)
                end
            end
        end)
        
        return anims
    end
    
    combat:Label("-- Auto Parry (Proudly Skidded from L) --")
    
    combat:Label("Auto Parry doesn't work on monsters and can't be use as one")
    
    combat:Bind("Auto Parry",Enum.KeyCode.Unknown,function(Value)
        if Value == Enum.KeyCode.Unknown then return end
        
        --// Proudly Skidded from L
        AutoParry = not AutoParry
        
        win.Notify({
            Title = "Auto Parry",
            Text = tostring(AutoParry),
        })
        
        local RunService = game:GetService("RunService")
        local Players = game:GetService("Players")
        local ReplicatedStorage = game:GetService("ReplicatedStorage")
        local VirtualInputManager = game:GetService('VirtualInputManager')
        local Player = Players.LocalPlayer
        
        local AnimationIds = GetAllAnims()
        
        local AnimPercentPB = 0
        local AnimPercentMax = 10
        
        local function GetNearby()
            local closest,range = {},ParryDistance
            
            for i,v in pairs(game:GetService("Workspace").Characters:GetChildren()) do
                pcall(function()
                    if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= range then
                        table.insert(closest,v) 
                    end
                end)
            end
            
            return closest
        end
        
        local APConnection
        local function AP()
    
            if AutoParry == false then APConnection:Disconnect() return end
            print(#GetNearby())
            for i,v in pairs(GetNearby()) do
                pcall(function()
                    if game.Players.LocalPlayer.Character ~= v then

                        local PlayingAnimations = v.Humanoid.Animator:GetPlayingAnimationTracks() --Possibly Outdated
            
                        for i,anim in pairs(PlayingAnimations) do
                            if table.find(AnimationIds, anim.Animation.AnimationId) then
                                local AnimationPercent = anim.TimePosition/anim.Length * 100
            
                                local RootPart1 = v.HumanoidRootPart
                                local RootPart2 = game.Players.LocalPlayer.Character.HumanoidRootPart
                                local ObjectSpace = RootPart2.CFrame:inverse() * RootPart1.CFrame
                                local MaxDistance = 3
            
                                if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= ParryDistance then
                                    if ObjectSpace.Z > 0 then
                                        print("Behind Player")
                                    else
                                        if AnimationPercent >= AnimPercentPB and AnimationPercent <= AnimPercentMax and parryDebounce == false then
                                            task.wait()
                                            Parry(anim.Length,v)
                                        end
                                    end
                                end
                            end
                        end
                    end
                end)
            end
        end
        
        APConnection = RunService.RenderStepped:Connect(AP)
    end)
    
    combat:Slider("Auto Parry Range",{min = 0,max = 50,def = 13},function(Value)
        ParryDistance = Value
    end)
    
    combat:Toggle("Roll Instead of Parry",false,function(Value)
        RIOF = Value
    end)
    
    esp:Toggle("ESP",false,function(Value)
        getgenv().ESP = Value
        
        if ESP then 
            local lplr = game.Players.LocalPlayer
            local camera = game:GetService("Workspace").CurrentCamera
            local CurrentCamera = workspace.CurrentCamera
            local worldToViewportPoint = CurrentCamera.worldToViewportPoint
            
            if getgenv().ESPALREADYON == true and ESP == true then
               getgenv().ESPALREADYON = false
               ESP = false
               task.wait(0.01)
               ESP = true
               getgenv().ESPALREADYON = true
            end
            
            local HeadOff = Vector3.new(0, 0.5, 0)
            local LegOff = Vector3.new(0,3,0)
            
            for i,v in pairs(game.Players:GetChildren()) do
                getgenv().ESPALREADYON = true
                local BoxOutline = Drawing.new("Square")
                BoxOutline.Visible = false
                BoxOutline.Color = Color3.new(0,0,0)
                BoxOutline.Thickness = 3
                BoxOutline.Transparency = 1
                BoxOutline.Filled = false
            
                local Box = Drawing.new("Square")
                Box.Visible = false
                Box.Color = Color3.new(1,1,1)
                Box.Thickness = 1
                Box.Transparency = 1
                Box.Filled = false
            
                local HealthBarOutline = Drawing.new("Square")
                HealthBarOutline.Thickness = 5
                HealthBarOutline.Filled = false
                HealthBarOutline.Color = Color3.new(0,0,0)
                HealthBarOutline.Transparency = 1
                HealthBarOutline.Visible = false
            
                local HealthBar = Drawing.new("Square")
                HealthBar.Thickness = 3
                HealthBar.Filled = false
                HealthBar.Transparency = 1
                HealthBar.Visible = false
                
                local Distance = Drawing.new("Text")
                Distance.Visible = false
                Distance.Center = true
                Distance.Outline = true
                Distance.Font = 1
                Distance.Color = Color3.fromRGB(255,255,255)
                Distance.Size = 13
            
                function boxesp()
                    local boxconnection
                    boxconnection = game:GetService("RunService").RenderStepped:Connect(function()
                        pcall(function()
                            if v.Character ~= nil and v.Character:FindFirstChild("Humanoid") ~= nil and v.Character:FindFirstChild("HumanoidRootPart") ~= nil and v ~= lplr and v.Character.Humanoid.Health > 0 then
                                local Vector, onScreen = camera:worldToViewportPoint(v.Character.HumanoidRootPart.Position)
                
                                local RootPart = v.Character.HumanoidRootPart
                                local Head = v.Character.Head
                                local RootPosition, RootVis = worldToViewportPoint(CurrentCamera, RootPart.Position)
                                local HeadPosition = worldToViewportPoint(CurrentCamera, Head.Position + HeadOff)
                                local LegPosition = worldToViewportPoint(CurrentCamera, RootPart.Position - LegOff)
                
                                if onScreen then
                                    BoxOutline.Size = Vector2.new(1000 / RootPosition.Z, HeadPosition.Y - LegPosition.Y)
                                    BoxOutline.Position = Vector2.new(RootPosition.X - BoxOutline.Size.X / 2, RootPosition.Y - BoxOutline.Size.Y / 2)
                                    BoxOutline.Visible = false
                
                                    Box.Size = Vector2.new(1000 / RootPosition.Z, HeadPosition.Y - LegPosition.Y)
                                    Box.Position = Vector2.new(RootPosition.X - Box.Size.X / 2, RootPosition.Y - Box.Size.Y / 2)
                                    Box.Visible = false
                    
                                    if Settings.HealthBar then
                                        HealthBarOutline.Size = Vector2.new(2, HeadPosition.Y - LegPosition.Y)
                                        HealthBarOutline.Position = BoxOutline.Position - Vector2.new(6,0)
                                        HealthBarOutline.Visible = Settings.HealthBar
                    
                                        HealthBar.Size = Vector2.new(2, (HeadPosition.Y - LegPosition.Y) / (v.Character.Humanoid.MaxHealth / math.clamp(v.Character.Humanoid.Health, 0, v.Character.Humanoid.Health)))
                                        HealthBar.Position = Vector2.new(Box.Position.X - 6, Box.Position.Y + (1 / HealthBar.Size.Y))
                                        HealthBar.Color = Color3.fromRGB(255 - 255 / (v.Character.Humanoid.MaxHealth / v.Character.Humanoid.Health), 255 / (v.Character.Humanoid.MaxHealth / v.Character.Humanoid.Health), 0)
                                        HealthBar.Visible = Settings.HealthBar
                                    else
                                        HealthBarOutline.Visible = Settings.HealthBar
                                        HealthBar.Visible = Settings.HealthBar
                                    end
                                    
                                    if Settings.Distance then
                                        Distance.Position = BoxOutline.Position + Vector2.new(0,6)
                                        Distance.Visible = Settings.Distance
                                        Distance.Text = tostring(math.floor((game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Character.HumanoidRootPart.Position).magnitude))
                                    else
                                        Distance.Visible = Settings.Distance
                                    end
                                    
                                    if getgenv().ESP == false then
                                        BoxOutline:Remove()
                                        Box:Remove()
                                        HealthBarOutline:Remove()
                                        HealthBar:Remove()
                                        Distance:Remove()
                                        boxconnection:Disconnect()
                                    end
                                else
                                    BoxOutline.Visible = false
                                    Box.Visible = false
                                    HealthBarOutline.Visible = false
                                    HealthBar.Visible = false
                                    Distance.Visible = false
                                end
                            else
                                BoxOutline.Visible = false
                                Box.Visible = false
                                HealthBarOutline.Visible = false
                                HealthBar.Visible = false
                                Distance.Visible = false
                            end
                        end)
                    end)
                end
                coroutine.wrap(boxesp)()
            end
            
            local addedconnection
            addedconnection = game.Players.PlayerAdded:Connect(function(v)
                local BoxOutline = Drawing.new("Square")
                BoxOutline.Visible = false
                BoxOutline.Color = Color3.new(0,0,0)
                BoxOutline.Thickness = 3
                BoxOutline.Transparency = 1
                BoxOutline.Filled = false
            
                local Box = Drawing.new("Square")
                Box.Visible = false
                Box.Color = Color3.new(1,1,1)
                Box.Thickness = 1
                Box.Transparency = 1
                Box.Filled = false
            
                local HealthBarOutline = Drawing.new("Square")
                HealthBarOutline.Thickness = 5
                HealthBarOutline.Filled = false
                HealthBarOutline.Color = Color3.new(0,0,0)
                HealthBarOutline.Transparency = 1
                HealthBarOutline.Visible = false
            
                local HealthBar = Drawing.new("Square")
                HealthBar.Thickness = 3
                HealthBar.Filled = false
                HealthBar.Transparency = 1
                HealthBar.Visible = false
                
                local Distance = Drawing.new("Text")
                Distance.Visible = false
                Distance.Center = true
                Distance.Outline = true
                Distance.Font = 1
                Distance.Color = Color3.fromRGB(255,255,255)
                Distance.Size = 13
            
                function boxesp()
                    local boxconnection
                    boxconnection = game:GetService("RunService").RenderStepped:Connect(function()
                        pcall(function()
                            if v.Character ~= nil and v.Character:FindFirstChild("Humanoid") ~= nil and v.Character:FindFirstChild("HumanoidRootPart") ~= nil and v ~= lplr and v.Character.Humanoid.Health > 0 then
                                local Vector, onScreen = camera:worldToViewportPoint(v.Character.HumanoidRootPart.Position)
                
                                local RootPart = v.Character.HumanoidRootPart
                                local Head = v.Character.Head
                                local RootPosition, RootVis = worldToViewportPoint(CurrentCamera, RootPart.Position)
                                local HeadPosition = worldToViewportPoint(CurrentCamera, Head.Position + HeadOff)
                                local LegPosition = worldToViewportPoint(CurrentCamera, RootPart.Position - LegOff)
                
                                if onScreen then
                                    BoxOutline.Size = Vector2.new(1000 / RootPosition.Z, HeadPosition.Y - LegPosition.Y)
                                    BoxOutline.Position = Vector2.new(RootPosition.X - BoxOutline.Size.X / 2, RootPosition.Y - BoxOutline.Size.Y / 2)
                                    BoxOutline.Visible = false
                
                                    Box.Size = Vector2.new(1000 / RootPosition.Z, HeadPosition.Y - LegPosition.Y)
                                    Box.Position = Vector2.new(RootPosition.X - Box.Size.X / 2, RootPosition.Y - Box.Size.Y / 2)
                                    Box.Visible = false
                    
                                    if Settings.HealthBar then
                                        HealthBarOutline.Size = Vector2.new(2, HeadPosition.Y - LegPosition.Y)
                                        HealthBarOutline.Position = BoxOutline.Position - Vector2.new(6,0)
                                        HealthBarOutline.Visible = Settings.HealthBar
                    
                                        HealthBar.Size = Vector2.new(2, (HeadPosition.Y - LegPosition.Y) / (v.Character.Humanoid.MaxHealth / math.clamp(v.Character.Humanoid.Health, 0, v.Character.Humanoid.Health)))
                                        HealthBar.Position = Vector2.new(Box.Position.X - 6, Box.Position.Y + (1 / HealthBar.Size.Y))
                                        HealthBar.Color = Color3.fromRGB(255 - 255 / (v.Character.Humanoid.MaxHealth / v.Character.Humanoid.Health), 255 / (v.Character.Humanoid.MaxHealth / v.Character.Humanoid.Health), 0)
                                        HealthBar.Visible = Settings.HealthBar
                                    else
                                        HealthBarOutline.Visible = Settings.HealthBar
                                        HealthBar.Visible = Settings.HealthBar
                                    end
                                    
                                    if Settings.Distance then
                                        Distance.Position = BoxOutline.Position + Vector2.new(0,6)
                                        Distance.Visible = Settings.Distance
                                        Distance.Text = tostring(math.floor((game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Character.HumanoidRootPart.Position).magnitude))
                                    else
                                        Distance.Visible = Settings.Distance
                                    end
                                    
                                    if getgenv().ESP == false then
                                        BoxOutline:Remove()
                                        Box:Remove()
                                        HealthBarOutline:Remove()
                                        HealthBar:Remove()
                                        Distance:Remove()
                                        addedconnection:Disconnect()
                                        boxconnection:Disconnect()
                                    end
                                else
                                    BoxOutline.Visible = false
                                    Box.Visible = false
                                    HealthBarOutline.Visible = false
                                    HealthBar.Visible = false
                                    Distance.Visible = false
                                end
                            else
                                BoxOutline.Visible = false
                                Box.Visible = false
                                HealthBarOutline.Visible = false
                                HealthBar.Visible = false
                                Distance.Visible = false
                            end
                        end)
                    end)
                end
                coroutine.wrap(boxesp)()
            end)
        end
    end)
    
    esp:Label("-- ESP Settings --")
    
    esp:Toggle("Show Health Bar",true,function(Value)
        Settings = {
            HealthBar = Value,
            Distance = Settings.Distance,
        }
    end)
    
    esp:Toggle("Show Distance",true,function(Value)
        Settings = {
            HealthBar = Settings.HealthBar,
            Distance = Value,
        }
    end)
    
    misc:Toggle("No Stun", false,function(Value)
        NoStun = Value
        
        while NoStun and task.wait() do
            pcall(function()
                plr.Character.Humanoid.WalkSpeed = 15
            end)
        end
    end)
    
    misc:Toggle("No Anims", false,function(Value)
        NoAnims = Value
        
        while task.wait() and NoAnims do
           pcall(function()
                if #plr.Character.Humanoid:GetPlayingAnimationTracks() > 0 then
                    for _,track in pairs(plr.Character.Humanoid:GetPlayingAnimationTracks()) do
                        track:Stop()
                    end
                end
           end)
        end
    end)
    
    misc:Bind("Silent Speed", Enum.KeyCode.Unknown,function(Value)
        if Value == Enum.KeyCode.Unknown then return end
        SilentSpeed = not SilentSpeed
        

        repeat
            local delta = game:GetService("RunService").Heartbeat:Wait()
            local x,y = pcall(function()
    		    if game.Players.LocalPlayer.Character.Humanoid.MoveDirection.Magnitude > 0 then
    			    game.Players.LocalPlayer.Character:TranslateBy(game.Players.LocalPlayer.Character.Humanoid.MoveDirection * tonumber(SSMulti) * delta * 10)
    		    end
            end)
        until SilentSpeed == false
    end)
    
    misc:Slider("Multiplier",{min = 0,max = 5, def = 4},function(Value)
        SSMulti = Value
    end)
    
    tps:Slider("Tween Speed",{min = 0, max = 200, def = getgenv().speed},function(Value)
        getgenv().speed = Value
    end)
    
    local fruitLabel = tps:Label("Fruit Status: No Fruits!")
    
    tps:Button("Teleport to Fruit",function(Value)
        if game:GetService("Workspace").DebrisParts:FindFirstChild("Tower2") or game:GetService("Workspace").DebrisParts:FindFirstChild("Tower") then
            local tower = game:GetService("Workspace").DebrisParts:FindFirstChild("Tower2") or game:GetService("Workspace").DebrisParts:FindFirstChild("Tower")
            
            if tower.Storage.Item:FindFirstChildOfClass("Model") ~= nil then
                Tween(tower.Storage.Item.CFrame)
                task.wait()
                if (tower.Storage.Item.Position - plr.Character.HumanoidRootPart.Position) <= 5 then
                    fireproximityprompt(tower.Storage.Item.Attachment.ProximityPrompt)
                    task.wait()
                end
            end
        end
    end)
    
    local plrDD
    
    plrDD = tps:Dropdown("Teleport to Player",game.Players:GetPlayers(),function(Value)
        local plrtoTpTo = game.Players:FindFirstChild(Value)
        
        if plrtoTpTo then
            if plrtoTpTo.Character == nil then return end
            Tween(plrtoTpTo.Character.HumanoidRootPart.CFrame)
        end
    end)
    
    game.Players.ChildAdded:Connect(function()
        plrDD:SetOptions(game.Players:GetPlayers())
    end)
    
    game.Players.ChildRemoved:Connect(function()
        plrDD:SetOptions(game.Players:GetPlayers())
    end)
    
    task.spawn(function()
        while task.wait() do
           pcall(function()
               local tower = game:GetService("Workspace").DebrisParts:FindFirstChild("Tower2") or game:GetService("Workspace").DebrisParts:FindFirstChild("Tower")
               
               if tower ~= nil then
                    local fruit = tower.Storage.Item:FindFirstChildOfClass("Model")
                    
                    if fruit ~= nil then
                        fruitLabel:SetText("Fruit Status: "..fruit.Name)
                        repeat task.wait() until tower.Storage.Item:FindFirstChildOfClass("Model") == nil
                        fruitLabel:SetText("Fruit Status: No Fruits!")
                    else
                        fruitLabel:SetText("Fruit Status: No Fruits!")
                    end
               else
                   fruitLabel:SetText("Fruit Status: No Fruits!")
               end
           end)
        end
    end)
    
    return win
end

local function Volleyball4dot2(name)
    local win = library:Window(name,Color3.fromRGB(36, 209, 171))
    win.PromptDiscord("y7H2qGmNKd")
    
    local main = win:Tab("Main")
    
    local JP = plr.Character.Humanoid.JumpPower
    local FOV = game:GetService("Workspace").Camera.FieldOfView
    local AutoRot = false
    local Juggle = false
    local AutoRec = false
    local AutoRecRadius = 10
    local AutoServe = false
    local AutoSpikeBlock = false
    local AutoSpikeBlockRadius = 10
    local RecAnim = nil
    local RecAnimDebounce = false
    local BlockAnim = nil
    local SpikeAnim = nil
    local SpikeBlockAnimDebounce = false
    local Action = string.lower(plr.PlayerGui.HUD.Bars.Action.Text)
    local BallLanding = false
    local CurrentPWR = 0
    local JPToggle = false
    local BallPredictConnection
    
    local predictor = Instance.new("Part",workspace)

    predictor.Name = "Predictor"
    predictor.Anchored = true
    predictor.CanCollide = false
    predictor.Material = Enum.Material.Neon
    predictor.Size = Vector3.new(4,1,4)
    predictor.Transparency = 1
    
    local landaoe = Instance.new("Part",workspace)
    landaoe.Name = "Landaoe"
    landaoe.Anchored = true
    landaoe.CanCollide = false
    landaoe.Material = Enum.Material.Neon
    landaoe.Size = Vector3.new(3,0.01,3)
    landaoe.Color = Color3.fromRGB(52, 186, 137)
    landaoe.Transparency = 1
    
    local recdist = {
        [1] = 17,
        [2] = 25,
        [3] = 32,
        [4] = 39,
        [5] = 47,
        [6] = 54,
        [7] = 61,
        [8] = 69,
        [9] = 76,
        [10] = 83,
        [11] = 91,
        [12] = 98,
        [13] = 105,
        [14] = 113,
        [15] = 120,
    }
    
    local function ClosestBall()
       if workspace:FindFirstChild("Ball") then
          local distances = {}
           
          for i,v in pairs(workspace:GetChildren()) do
             if v.Name == "Ball" and v:IsA("Model") then
                table.insert(distances,(v.BallPart.Position - plr.Character.HumanoidRootPart.Position).magnitude)
             end
          end
          
          table.sort(distances)
          
          for i,v in pairs(workspace:GetChildren()) do
             if v.Name == "Ball" and v:IsA("Model") and v:FindFirstChild("Marker") == nil then
                if (v.BallPart.Position - plr.Character.HumanoidRootPart.Position).magnitude <= distances[1] then
                   return v 
                end
             end
          end
       end
       
       return nil
    end
    
    local animfunc = false
    local function PlayAnim(anim)
        if anim == nil or animfunc then return end
        
        task.spawn(function()
            pcall(function()
                if anim.IsPlaying == false then
                   animfunc = true
                   anim:Play()
                   repeat task.wait() until anim.IsPlaying == false
                   task.wait(0.7)
                   animfunc = false
                end
            end)
        end)
    end
    
    main:Toggle("Auto Receive",false,function(Value)
        AutoRec = Value
        
        while task.wait() and AutoRec do
            print(ClosestBall())
            pcall(function()
                if ClosestBall() ~= nil and Juggle == false then
                    if plr.Character.Humanoid.WalkSpeed ~= 0 and (ClosestBall().BallPart.Position - plr.Character.HumanoidRootPart.Position).magnitude <= AutoRecRadius then
                        PlayAnim(RecAnim)
                        game:GetService("ReplicatedStorage").Remotes.PlayerAction:FireServer("Receiving") 
                    end
                end
            end)
        end
    end)
    
    main:Slider("Receive Radius",{min = 0, max = 30, def = 10},function(Value)
        AutoRecRadius = Value
    end)
    
    main:Label("(to swap spike/block press 1 like normally)")
    
    main:Toggle("Auto Spike/Block",false,function(Value)
        AutoSpikeBlock = Value
        
        while task.wait() and AutoSpikeBlock do
            pcall(function()
                if ClosestBall() ~= nil then
                    Action = string.lower(plr.PlayerGui.HUD.Bars.Action.Text)
                    if Action == "spike" and plr.Character.Humanoid.WalkSpeed == 0 and (ClosestBall().BallPart.Position - plr.Character.HumanoidRootPart.Position).magnitude <= AutoSpikeBlockRadius then
                        PlayAnim(SpikeAnim)
                        game:GetService("ReplicatedStorage").Remotes.PlayerAction:FireServer("Spiking")
                    elseif Action == "block" and plr.Character.Humanoid.WalkSpeed == 0 and (ClosestBall().BallPart.Position - plr.Character.HumanoidRootPart.Position).magnitude <= AutoSpikeBlockRadius then
                        PlayAnim(BlockAnim)
                        game:GetService("ReplicatedStorage").Remotes.PlayerAction:FireServer("Blocking")
                    end
                end
            end)
        end
    end)
    
    main:Slider("Spike/Block Radius",{min = 0, max = 30, def = 10},function(Value)
        AutoSpikeBlockRadius = Value
    end)
    
    main:Label("-- Noticable/Risky --")
    
    main:Toggle("No Line Fault",false,function(Value)
        local LFdef = Vector3.new(95,1,120)
        local LFmod = Vector3.new(0.001, 1, 0.001)
        
        if Value then
           game.Workspace.ServeLF.Size = LFmod
        else
            game.Workspace.ServeLF.Size = LFdef
        end
    end)
    
    main:Button("Inf Stamina (Perma)",false,function()
        local aux = loadstring(game:HttpGetAsync("https://raw.githubusercontent.com/Upbolt/Hydroxide/revision/ohaux.lua"))()
        local player = game.Players.LocalPlayer.Name
        local scriptPath = workspace[player].CharacterScript
        local closureName = "handleStaminaRegen"
        local upvalueIndex = 2
        local closureConstants = {
            [1] = "Velocity",
            [2] = "Magnitude",
            [3] = 16.5,
            [4] = "Stamina",
            [5] = "tick",
            [7] = 1.5
        }
        
        local closure = aux.searchClosure(scriptPath, closureName, upvalueIndex, closureConstants)
        local value = math.huge
        local elementIndex = "Stamina"
        
        debug.getupvalue(closure, upvalueIndex)[elementIndex] = value
    end)
    
    main:Toggle("JumpPower On/Off",false,function(Value)
        JPToggle = Value
    end)
    
    main:Slider("JumpPower",{min = 0, max = 100, def = 30},function(Value)
        JP = Value
        if JPToggle then
            plr.Character.Humanoid.JumpPower = Value
        end
    end)
    
    main:Bind("Auto Juggle",Enum.KeyCode.CapsLock,function(Value)
        Juggle = not Juggle
        
        win.Notify({
            Title = "Auto Juggle",
            Text = tostring(Juggle),
        })
        
        while task.wait() and Juggle do
           pcall(function()
               if ClosestBall() ~= nil then
                   if plr.Character.Humanoid.WalkSpeed ~= 0 and (ClosestBall().BallPart.Position - plr.Character.HumanoidRootPart.Position).magnitude <= AutoRecRadius then
                        PlayAnim(RecAnim)
                        game:GetService("ReplicatedStorage").Remotes.PlayerAction:FireServer("Diving") 
                   end
               end
           end)
        end
    end)
    
    main:Toggle("Rotate Freely when Jumping",false,function(Value)
        AutoRot = Value
    end)
    
    main:Label("-- Visuals --")
    
    main:Label("(ball landing spot only predicts receiving/bumping the ball)")
    main:Toggle("Ball Landing Spot",false,function(Value)
        BallLanding = Value
        
        if not BallLanding then landaoe.Transparency = 1 landaoe.Anchored = true else landaoe.Transparency = 0 end
        
        while BallLanding and task.wait() do
            pcall(function()
                landaoe.CFrame = plr.Character.HumanoidRootPart.CFrame * CFrame.new(0,-2.9,-recdist[tonumber(plr.PlayerGui.HUD.Bars.Power.Amount.Text:split(" / ")[1])])
                task.wait()
            end)
        end
    end)
    
    main:Toggle("Ball Prediction",false,function(Value)
        BallPredict = Value
        
        if BallPredict then
            local RunService = game:GetService("RunService")
            
            BallPredictConnection = RunService.Heartbeat:Connect(function(dt)
                task.wait()
                if BallPredict then
               if ClosestBall() ~= nil then
                   local Ball = ClosestBall()
                   local Vel = Ball.Velocity
                   local Pos = Ball.Position
            
                   if Vel.Value.X < 1 and Vel.Value.Y < 1 and Vel.Value.Z < 1 then
                      task.wait()
                   elseif Vel.Value.X == 0 and Vel.Value.Y > 0 and Vel.Value.Z == 0 then
                       task.wait()
                   else
                       predictor.Transparency = 0.2
                        
                       local multi = 0.3
                      
                       repeat
                           pcall(function()
                               predictor.Anchored = false
                               task.wait()
                               if Vel.Value.Y <= 7 then multi = 0.1 elseif Vel.Value.Y <= 3 then multi = 0.05 end
                               predictor.Position = Vector3.new(Pos.Value.X,Ball.Shadow.Position.Y,Pos.Value.Z) + Vector3.new(Vel.Value.X, 0, Vel.Value.Z) * multi-- * times shit that will make it go forward to the position of the direction its headed
                               task.wait()
                               predictor.Anchored = true
                            end)
                            task.wait()
                       until Ball:FindFirstChild("Marker")
                       predictor.Transparency = 1
                   end
               end
               end
            end)
        else
            if BallPredictConnection ~= nil then
               BallPredictConnection:Disconnect()
               BallPredictConnection = nil
            end
        end
    end)
    
    main:Slider("Camera FOV",{min = 0, max = 120, def = game:GetService("Workspace").Camera.FieldOfView},function(Value)
        game:GetService("Workspace").Camera.FieldOfView = Value
    end)
    
    task.spawn(function()
        local HumanoidInstance = {}
        
        while task.wait(1) do
           pcall(function()
               if HumanoidInstance[plr.Character.Humanoid] == nil then
                  HumanoidInstance[plr.Character.Humanoid] = true
                  
                  RecAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Assets.Animations.Receive.Default)
                  BlockAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Assets.Animations.Block.Default)
                  SpikeAnim = plr.Character.Humanoid:LoadAnimation(game:GetService("ReplicatedStorage").Assets.Animations.Spike["Tommy RH"].Spike)
                  
                  plr.Character.Humanoid:GetPropertyChangedSignal("JumpPower"):Connect(function()
                     pcall(function()
                         if JPToggle then
                            plr.Character.Humanoid.JumpPower = JP
                         end
                     end)
                  end)
                  
                  plr.Character.Humanoid:GetPropertyChangedSignal("AutoRotate"):Connect(function()
                     pcall(function()
                         if AutoRot then
                            plr.Character.Humanoid.AutoRotate = true
                         end
                     end)
                  end)
               end
           end)
           
           pcall(function()
                if JPToggle then
                    plr.Character.Humanoid.JumpPower = JP
                end
                game:GetService("Workspace").Camera.FieldOfView = FOV
            end)
        end
    end)
    
    return win
end

local function PIXELPENIS(name)
    local win = library:Window(name,Color3.fromRGB(209, 123, 36))
    win.PromptDiscord("y7H2qGmNKd")
    
    local main = win:Tab("Main")
    
    local AntiWaterDamage,hooked = false,false
    local questNPCData = {}
    local LevelFarm = false
    local Enemy = nil
    local QuestGuy = nil
    local vim = game:GetService("VirtualInputManager")
    local AutoClick = false
    local RegularFarm = false
    local Clip = true
    local EnemyDD
    local FastPunch = false
    local EquipDaTool
    local autoequipDD
    
    local teleport_table = {
        spawn_island = Vector3.new(-1790.1414794921875, 601.824951171875, -11963.2978515625),
        central_port = Vector3.new(-4061.7431640625, 606.3749389648438, 769.94970703125),
        baratier = Vector3.new(-1529.8740234375, 592.578369140625, -7277.3994140625),
        jungle_of_caos = Vector3.new(-6615.89111328125, 611.042236328125, -1910.0606689453125),
        longtown = Vector3.new(-1558.120849609375, 596.8983764648438, 8003.40576171875),
        orange_town = Vector3.new(-3093.191650390625, 599.9927978515625, -2049.954833984375),
        arena = Vector3.new(-9251.3173828125, 620.9998779296875, 2230.476806640625),
        shark_park = Vector3.new(754.0820922851562, 596.8936157226562, 1501.08837890625),
        shells_town = Vector3.new(-5755.7109375, 618.7764892578125, -7818.60595703125),
        syrup_island = Vector3.new(3235.392333984375, 659.0364379882812, -4815.6181640625),
        vaill_island = Vector3.new(-6615.65576171875, 611.042236328125, -1911.174560546875),
    }

    local function teleport_bypass(cframe)
       local GetService = game.GetService
    
        local Services = { -- do not remove
            Workspace = GetService(game, "Workspace");
            ReplicatedStorage = GetService(game, "ReplicatedStorage");
            
        }
        
        setmetatable(Services, { -- do not remove
            __index = function(Table, Property)
                local Ret, Service = pcall(GetService, game, Property);
                if (Ret) then
                    Services[Property] = Service
                    return Service
                end
                return nil
            end,
            __mode = "v"
        });
        
        local GetChildren, GetDescendants = game.GetChildren, game.GetDescendants -- do not remove
        local IsA = game.IsA
        local FindFirstChild, FindFirstChildOfClass, FindFirstChildWhichIsA, WaitForChild = 
            game.FindFirstChild,
            game.FindFirstChildOfClass,
            game.FindFirstChildWhichIsA,
            game.WaitForChild
        
        local Inverse, toObjectSpace, components -- do not remove
        do
            local CalledCFrameNew = CFrame.new();
            Inverse = CalledCFrameNew.Inverse
            toObjectSpace = CalledCFrameNew.toObjectSpace
            components = CalledCFrameNew.components
        end
        
        
        local __H = Instance.new("Humanoid"); -- do not remove
        local UnequipTools = __H.UnequipTools
        local ChangeState = __H.ChangeState
        local SetStateEnabled = __H.SetStateEnabled
        local GetState = __H.GetState
        local GetAccessories = __H.GetAccessories
        
        local LocalPlayer = game.Players.LocalPlayer --do not remove
        
        local GetCharacter = GetCharacter or function(Plr) -- do not remove
            return Plr and Plr.Character or LocalPlayer.Character
        end
        
        -- do not remove below
        local Utils = {}
        
        local getrawmetatable = getrawmetatable or function()
            return setmetatable({}, {});
        end
        
        local getnamecallmethod = getnamecallmethod or function()
            return ""
        end
        
        local checkcaller = checkcaller or function()
            return false
        end
        
        local Hooks = {
            AntiKick = false,
            AntiTeleport = false,
            NoJumpCooldown = false,
        }
        
        local mt = getrawmetatable(game);
        local OldMetaMethods = {}
        setreadonly(mt, false);
        for i, v in next, mt do
            OldMetaMethods[i] = v
        end
        setreadonly(mt, true);
        local MetaMethodHooks = {}
        
        local ProtectInstance, SpoofInstance, SpoofProperty;
        local UnSpoofInstance;
        local ProtectedInstances = setmetatable({}, {
            __mode = "v"
        });
        do
            local SpoofedInstances = setmetatable({}, {
                __mode = "v"
            });
            local SpoofedProperties = {}
            Hooks.SpoofedProperties = SpoofedProperties
        
            ProtectInstance = function(Instance_)
                if (not Tfind(ProtectedInstances, Instance_)) then
                    ProtectedInstances[#ProtectedInstances + 1] = Instance_
                end
            end
            
            SpoofInstance = function(Instance_, Instance2)
                if (not SpoofedInstances[Instance_]) then
                    SpoofedInstances[Instance_] = Instance2 and Instance2 or game.Clone(Instance_);
                end
            end
        
            UnSpoofInstance = function(Instance_)
                if (SpoofedInstances[Instance_]) then
                    SpoofedInstances[Instance_] = nil
                end
            end
            
            local ChangedSpoofedProperties = {}
            SpoofProperty = function(Instance_, Property, NoClone)
                if (SpoofedProperties[Instance_]) then
                    local SpoofedPropertiesForInstance = SpoofedProperties[Instance_]
                    local Properties = map(SpoofedPropertiesForInstance, function(i, v)
                        return v.Property
                    end)
                    if (not Tfind(Properties, Property)) then
                        SpoofedProperties[Instance_][#SpoofedPropertiesForInstance + 1] = {
                            SpoofedProperty = SpoofedPropertiesForInstance.SpoofedProperty,
                            Property = Property,
                        };
                    end
                else
                    local Cloned;
                    if (not NoClone and IsA(Instance_, "Instance") and not Services[tostring(Instance_)] and Instance_.Archivable) then
                        local Success, Ret = pcall(Clone, Instance_);
                        if (Success) then
                            Cloned = Ret
                        end
                    end
                    SpoofedProperties[Instance_] = {{
                        SpoofedProperty = Cloned and Cloned or {[Property]=Instance_[Property]},
                        Property = Property,
                    }}
                    ChangedSpoofedProperties[Instance_] = {}
                end
            end
        end
        
        local ReplaceCharacter = function()
            local Char = game.Players.LocalPlayer.Character
            local Model = Instance.new("Model");
            game.Players.LocalPlayer.Character = Model
            game.Players.LocalPlayer.Character = Char
            game.Destroy(Model);
            return Char
        end
        
        local GetRoot = function(Plr, Char)
            local LCharacter = GetCharacter();
            local Character = Char or GetCharacter(Plr);
            return Plr and Character and (FindFirstChild(Character, "HumanoidRootPart") or FindFirstChild(Character, "Torso") or FindFirstChild(Character, "UpperTorso")) or LCharacter and (FindFirstChild(LCharacter, "HumanoidRootPart") or FindFirstChild(LCharacter, "Torso") or FindFirstChild(LCharacter, "UpperTorso"));
        end
        
        local GetHumanoid = function(Plr, Char)
            local LCharacter = GetCharacter();
            local Character = Char or GetCharacter(Plr);
            return Plr and Character and FindFirstChildWhichIsA(Character, "Humanoid") or LCharacter and FindFirstChildWhichIsA(LCharacter, "Humanoid");
        end
        
        local ReplaceHumanoid = function(Hum, R)
            local Humanoid = Hum or GetHumanoid();
            local NewHumanoid = game.Clone(Humanoid);
            if (R) then
                NewHumanoid.Name = "1"
            end
            NewHumanoid.Parent = Humanoid.Parent
            NewHumanoid.Name = Humanoid.Name
            game:GetService("Workspace").Camera.CameraSubject = NewHumanoid
            game.Destroy(Humanoid);
            wait(0.01)
            SpoofInstance(NewHumanoid);
            return NewHumanoid
        end
        
        local OldPos = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
        ReplaceCharacter();
        wait(game.Players.RespawnTime - 0.03);
        ReplaceHumanoid()
        game.Loaded.Wait(game.Players.LocalPlayer.CharacterAdded)
        WaitForChild(game.Players.LocalPlayer.Character, "HumanoidRootPart").CFrame = cframe 
    end
    
    local function findtarget(Enemy)
      if Enemy == nil then return end
      
      for i,v in pairs(game:GetService("Workspace").Terrain.World.TargetFilter.Characters.Enemys:GetChildren()) do
        if v.Name == (Enemy) and v.EnemyHumanoid.Health > 0 and v:FindFirstChild("Torso") ~= nil then
            return v
        end
      end
      return
   end
    
    local function GetQuest(npc)
        if npc == nil then return end
        
        local maxtime = 15
        
        if (npc.HumanoidRootPart.Position - plr.Character.HumanoidRootPart.Position).magnitude / getgenv().speed >= 15 then
            teleport_bypass(npc.HumanoidRootPart.CFrame * CFrame.new(0,0,-4))
        else
            Tween(npc.HumanoidRootPart.CFrame * CFrame.new(0,0,-4))
        end
        
        repeat
            vim:SendKeyEvent(true, "E", false, game)
            task.wait(1)
            vim:SendKeyEvent(false, "E", false, game)
            task.wait(1)
        until plr.PlayerGui.PlayerHUD.Interface.Others.DialogUI.Visible == true
        
        repeat task.wait() until plr.PlayerGui.PlayerHUD.Interface.Others.DialogUI.Theme.AcceptButton.Visible == true
        SimulateClick(game.Players.LocalPlayer.PlayerGui.PlayerHUD.Interface.Others.DialogUI.Theme.AcceptButton,"Function")
    end
    
    local function GetEnemyName()
        local npcName = ""
        local amount = nil
        for i,v in pairs(game.Players.LocalPlayer.PlayerGui.PlayerHUD.Interface.Others.QuestUI.Handle.TemplateText.Label.Text:split("Defeat")[2]:split("of")[1]:split(" ")) do
            if tonumber(v) == nil then
                if v ~= "" then
                    if npcName == "" then
                       npcName = v
                    else
                        npcName = npcName.." "..v
                    end
                end
            elseif i == 2 then
                amount = tonumber(v)
            end
        end
        if amount > 1 then
            if npcName:find("(s)") then
                local stringcache = ""
            
                for i = 1, #npcName do
                    local c = npcName:sub(i,i)
            
                    
                    if c == "(" then
                        break
                    else
                        stringcache = stringcache .. c
                    end
                end
                
                npcName = stringcache
            else
                local stringcache = ""
            
                for i = 1, #npcName do
                    local c = npcName:sub(i,i)
            
                    
                    if #npcName == i and c == "s" then
                        break
                    else
                        stringcache = stringcache .. c
                    end
                end
                
                npcName = stringcache
            end
        end
        return npcName
    end
    
    local function GetQuestNPC(npcname)
        if #questNPCData == 0 then
            for _,islandF in next, game:GetService("Workspace").Terrain.World.Islands:GetChildren() do
              if islandF:FindFirstChild("NPCs") then
                    for i,v in pairs(islandF.NPCs:GetChildren()) do
                        if v:FindFirstChild("Head") then
                            if v.Head:FindFirstChild("Overhead") then
                              if v.Head.Overhead.LevelReq.Text:find("Level") then
                                  table.insert(questNPCData,v.Name.." | "..v.Head.Overhead.LevelReq.Text) 
                              end
                            end
                        end
                    end 
              end
            end
        end
        
        if npcname ~= nil then
            for _,islandF in next, game:GetService("Workspace").Terrain.World.Islands:GetChildren() do
               if islandF:FindFirstChild("NPCs") then
                    for i,v in pairs(islandF.NPCs:GetChildren()) do
                        if v.Head:FindFirstChild("Overhead") then
                            if v.Name == npcname then
                                return v
                            end
                        end
                    end 
               end
            end
            return
        end
        local bestoption,level = nil,nil
        local myLevel = plr.Data.States.Info.Level.Value
        
        for _,islandF in next, game:GetService("Workspace").Terrain.World.Islands:GetChildren() do
           if islandF:FindFirstChild("NPCs") then
                for i,v in pairs(islandF.NPCs:GetChildren()) do
                    if v:FindFirstChild("Head") then
                        if v.Head:FindFirstChild("Overhead") then
                            if v.Head.Overhead.LevelReq.Text:find("Level") then
                                local numLevel = tonumber(v.Head.Overhead.LevelReq.Text:split("Level")[2]:split("+")[1])

                                if myLevel >= numLevel then
                                    if bestoption == nil and level == nil then
                                        bestoption = v
                                        level = numLevel
                                    elseif level < numLevel then
                                        bestoption = v
                                        level = numLevel
                                    end
                                end
                            end
                        end
                    end
                end 
           end
        end
        
        return bestoption
    end
    
    GetQuestNPC()
    
    local function GetEnemys()
       local cache = {}
       local alreadyadded = {}
    
       for i,v in pairs(game:GetService("Workspace").Terrain.World.TargetFilter.Characters.Enemys:GetChildren()) do
           if table.find(alreadyadded,v.Name) == nil then
                table.insert(cache,v)
                table.insert(alreadyadded,v.Name) 
           end
       end
       
       return cache
    end
    
    local islandtpthing = {}
    
    for i,v in pairs(teleport_table) do
        table.insert(islandtpthing,tostring(i))
    end
    
    main:Toggle("Regular Farm",false,function(Value)
        RegularFarm = Value
        
        if RegularFarm then
            Clip = false
            while task.wait(0.1) and RegularFarm do
                pcall(function()
                    if plr.PlayerGui.PlayerHUD.Interface.Others.QuestUI.Visible == false then
                        GetQuest(QuestGuy)
                        task.wait()
                    else
                       local NPC = findtarget(Enemy)
                       
                       if NPC ~= nil and RegularFarm then
                           if NPC.EnemyHumanoid.Health > 0 then
                               task.spawn(function()
                                   if (NPC.Torso.Position - plr.Character.Torso.Position).magnitude / getgenv().speed >= 15 then
                                        teleport_bypass(NPC.Torso.CFrame * CFrame.new(0,0,6))
                                        task.wait(0.5)
                                    else
                                        repeat
                                            task.spawn(function()
                                                Tween(NPC.Torso.CFrame * CFrame.new(0,0,6))
                                            end)
                                            task.wait()
                                            if EquipDaTool ~= nil then
                                                if plr.Backpack:FindFirstChild(EquipDaTool) then
                                                    plr.Backpack:FindFirstChild(EquipDaTool).Parent = plr.Character
                                                    task.wait()
                                                end
                                            end
                                        until NPC.EnemyHumanoid.Health <= 0 or plr.Character.Humanoid.Health <= 0 or RegularFarm == false or plr.PlayerGui.PlayerHUD.Interface.Others.QuestUI.Visible == false
                                    end
                               end)
                           end
                       end
                    end
                end)
            end
        else
            Clip = true
        end
    end)
    
    EnemyDD = main:Dropdown("Enemy (Reg)",GetEnemys(),function(Value,Index)
        Enemy = Value
    end)
    
    main:Dropdown("Quest (Reg)",questNPCData,function(Value)
        local name,leveltxt = unpack(Value:split(" | "))
        local questChar = nil
        
        for _,islandF in next, game:GetService("Workspace").Terrain.World.Islands:GetChildren() do
           if islandF:FindFirstChild("NPCs") then
                for i,v in pairs(islandF.NPCs:GetChildren()) do
                    if v.Head:FindFirstChild("Overhead") then
                        if v.Head.Overhead.LevelReq.Text:find("Level") then
                            if v.Name == name and v.Head.Overhead.LevelReq.Text == leveltxt then
                                questChar = v
                            end
                        end
                    end
                end 
           end
        end
        
        if questChar == nil then return end

        QuestGuy = questChar
    end)
    
    autoequipDD = main:Dropdown("Auto Equip (Farms)",game.Players.LocalPlayer.Backpack:GetChildren(),function(Value)
        EquipDaTool = Value
    end)
    
    main:Toggle("Level Farm",false,function(Value)
        LevelFarm = Value
        
        if LevelFarm then
           Clip = false
        
           while task.wait(1) and LevelFarm do
               pcall(function()
                   if plr.PlayerGui.PlayerHUD.Interface.Others.QuestUI.Visible == false then
                       GetQuest(GetQuestNPC())
                       task.wait(0.5)
                   else
                       local NPC = findtarget(GetEnemyName())
                       
                       if NPC ~= nil and LevelFarm then
                           if NPC.EnemyHumanoid.Health > 0 then
                               task.spawn(function()
                                   if (NPC.Torso.Position - plr.Character.Torso.Position).magnitude / getgenv().speed >= 15 then
                                        teleport_bypass(NPC.Torso.CFrame * CFrame.new(0,0,6))
                                        task.wait(0.5)
                                    else
                                        repeat
                                            task.spawn(function()
                                                Tween(NPC.Torso.CFrame * CFrame.new(0,0,6))
                                            end)
                                            task.wait()
                                            if EquipDaTool ~= nil then
                                                if plr.Backpack:FindFirstChild(EquipDaTool) then
                                                    plr.Backpack:FindFirstChild(EquipDaTool).Parent = plr.Character
                                                    task.wait()
                                                end
                                            end
                                        until NPC.EnemyHumanoid.Health <= 0 or plr.Character.Humanoid.Health <= 0 or LevelFarm == false or plr.PlayerGui.PlayerHUD.Interface.Others.QuestUI.Visible == false
                                    end
                               end)
                           end
                       end
                   end
               end)
           end
        else
            Clip = true
        end
    end)
    
    main:Slider("Tween Speed",{def = getgenv().speed, min = 0, max = 500},function(Value)
        getgenv().speed = Value
    end)
    
    main:Bind("Autoclicker",Enum.KeyCode.J,function()
        AutoClick = not AutoClick
        
        win.Notify({
            Title = "AutoClicker",
            Text = tostring(AutoClick),
        })
        
        if AutoClick then
            task.spawn(function()
                while AutoClick and task.wait() do
                    pcall(function()
                        vim:SendMouseButtonEvent(0, 500, 0, true, game, 1)
                        task.wait()
                        vim:SendMouseButtonEvent(0, 500, 0, true, game, 1)
                        task.wait() 
                    end)
                end
            end)
        end
    end)
    
    main:Dropdown("Island TP",islandtpthing,function(Value)
        local pos = teleport_table[Value]
        teleport_bypass(CFrame.new(pos.X,pos.Y,pos.Z))
    end)
    
    main:Toggle("Anti Drown",false,function(Value)
        AntiWaterDamage = Value
        
        if hooked == false and AntiWaterDamage then
           local mt = getrawmetatable(game)
            local namecall = mt.__namecall
            setreadonly(mt,false)
            mt.__namecall = newcclosure(function(self,...) -- self ( the instance )  and args 
                if getnamecallmethod() == 'FireServer' and tostring(self) == 'RequestEvent' then -- checking if we're firing a remote
                    local args = {...} 
                    if typeof(args[2]) == "table" then
                           if args[1] == "Water" and AntiWaterDamage then
                                   return
                           end
                    end
                end
                return namecall(self,...)
            end)
            setreadonly(mt,true) 
        end
    end)
    
    main:Button("Unlock Geppo",function()
        local lolthisgamelikesclientdetection = game:GetService("Players").LocalPlayer.Data.States.Info.Habilitys
        lolthisgamelikesclientdetection:SetAttribute("Geppo", true)
    end)
    
    plr.Backpack.ChildAdded:Connect(function()
        autoequipDD:SetOptions(plr.Backpack:GetChildren())
    end)
    
    game:GetService("Workspace").Terrain.World.TargetFilter.Characters.Enemys.ChildAdded:Connect(function()
        EnemyDD:SetOptions(game:GetService("Workspace").Terrain.World.TargetFilter.Characters.Enemys:GetChildren())
    end)

    return win
end

local function EGO(name)
    local win = library:Window(name,Color3.fromRGB(50, 36, 209))
    win.PromptDiscord("y7H2qGmNKd")
    win.Notify({
        Title = "Welcome back!",
        Text = "Your a OG m1kecorp buyer!\nSuggest more stuff to add to egoist! Thank you"
    })
    
    local main = win:Tab("Main")
    local risky = win:Tab("Risky")
    local tricks = win:Tab("Tricks")
    
    --// Vars \\--
    local GAB = false
    local GABStyle = "Closest"
    local PAB = false
    local ABOnScreen = false
    local Power = false
    local AutoGK = false
    local AutoReflect = false
    local ARDist = 10
    local AutoHup = false
    local GKAction = "ShootGoal"
    local GKDist = 10
    local BallLock = false
    local HupRape = false
    local hupRapeBool = false
    local FrontBK = false
    local ADStats
    local AutoDribble = false
    local ADMultiplier = 0.078
    local ADInterval = 0.1
    local NewAutoDribble = false
    local StrongDash = false
    local DashPower = false
    local WalkSpeedTog = false
    local SpeedVal = false
    local JumpPowerTog = false
    local JumpVal = false
    local PassPower = false
    local CurvePower = false
    local CurveDirect = "Right"
    local CurveHeight = false
    local DSPower = false
    local KickUpPower = false
    local HighKickPower = false
    local DribblePower = false
    
    local goalintrepter = {
        ["Goal2"] = {"11967283138","11967296511"},
        ["Goal1"] = {"11988090225","11988080314"}
    }
    
    local SvS = 12159833555
    
    local goalpos = {
        ["Goal1"] = {game:GetService("Workspace").BigArena.Goal1.Position,Vector3.new(-94, 11, -1643),Vector3.new(-93, 11, -1660)},
        ["Goal2"] = {game:GetService("Workspace").BigArena.Goal2.Position, Vector3.new(133, 11, -1660),Vector3.new(133, 11, -1642)}
    }
    
    if game.PlaceId == SvS then
        goalpos = {
            ["Goal1"] = {Vector3.new(-203, 11, -3325),Vector3.new(-203, 11, -3300),Vector3.new(-204, 11, -3312)},
            ["Goal2"] = {Vector3.new(244, 11, -3300),Vector3.new(243, 11, -3325),Vector3.new(244, 11, -3312)}
        }
    end
    
    local function GetBestGoal(goalName)
        local postable = goalpos[goalName]
        local distances = {}
        
        for i,v in pairs(postable) do
            table.insert(distances,(game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v).magnitude) 
        end
        
        table.sort(distances)
        
        for i,v in pairs(postable) do
            if GKAction == "Farthest" then
              if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v).magnitude >= distances[#distances] then
                  return v 
              end 
            elseif GKAction == "Closest" then
                if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v).magnitude <= distances[1] then
                  return v 
                end
            else
                if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v).magnitude <= distances[1] then
                  return v 
                end
            end
        end
    end
    
    local function GetClosestBall(client)
      local cache = {}
        
      if client == nil then
          for i,v in pairs(game.Workspace:GetChildren()) do
              if v.Name == "Ball" then
                  table.insert(cache,#cache+1,(game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Position).magnitude) 
              end
          end 
        else
            for i,v in pairs(game.Workspace.ClientBalls:GetChildren()) do
                table.insert(cache,#cache+1,(game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Position).magnitude) 
          end
      end
       
      table.sort(cache)
       
      for i,v in pairs(game.Workspace:GetChildren()) do
          if v.Name == "Ball" then
              if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Position).magnitude <= cache[1] then
                  return v
              end
          end
      end
    end
    
    local function GetEnemyGoal()
        for i,v in pairs(goalintrepter) do
            local ShirtID = tostring(game:GetService("Players").LocalPlayer.UniformShirtId.Value)
            local PantID = tostring(game:GetService("Players").LocalPlayer.UniformPantsId.Value)
            
            if table.find(v,ShirtID) and table.find(v,PantID) then
                if i == "Goal2" then
                    return GetBestGoal("Goal1")
                else
                    return GetBestGoal("Goal2")
                end
            end
        end
    end
    
    local goalpos2 = {
        ["Goal1"] = {game:GetService("Workspace").BigArena.Goal1.Position,Vector3.new(-94, 15, -1643),Vector3.new(-93, 15, -1660)},
        ["Goal2"] = {game:GetService("Workspace").BigArena.Goal2.Position, Vector3.new(133, 15, -1660),Vector3.new(133, 15, -1642)}
    }
    
    if game.PlaceId == SvS then
        goalpos2 = {
            ["Goal1"] = {Vector3.new(-203, 15, -3325),Vector3.new(-203, 15, -3300),Vector3.new(-204, 11, -3312)},
            ["Goal2"] = {Vector3.new(244, 15, -3300),Vector3.new(243, 15, -3325),Vector3.new(244, 15, -3312)}
        }
    end
    
    local function GetBestGoal2(goalName)
        local postable = goalpos2[goalName]
        local distances = {}
        
        for i,v in pairs(postable) do
            table.insert(distances,(game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v).magnitude) 
        end
        
        table.sort(distances)
        
        for i,v in pairs(postable) do
            if GKAction == "Farthest" then
              if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v).magnitude >= distances[#distances] then
                  return v 
              end 
            elseif GKAction == "Closest" then
                if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v).magnitude <= distances[1] then
                  return v 
                end
            else
                if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v).magnitude <= distances[1] then
                  return v 
                end
            end
        end
    end
    
    local function GetEnemyGoal2()
        for i,v in pairs(goalintrepter) do
            local ShirtID = tostring(game:GetService("Players").LocalPlayer.UniformShirtId.Value)
            local PantID = tostring(game:GetService("Players").LocalPlayer.UniformPantsId.Value)
            
            if table.find(v,ShirtID) and table.find(v,PantID) then
                if i == "Goal2" then
                    return GetBestGoal2("Goal1")
                else
                    return GetBestGoal2("Goal2")
                end
            end
        end
    end
    
    local function modecheck()
        if game.Players.LocalPlayer.Character.Head:FindFirstChild("Health") then
            if game.Players.LocalPlayer.Character.Head.Health.Background:FindFirstChild("Health1").Image == "rbxassetid://11624929070" then
                return true
            else
                return false
            end
        end
        return false
    end
    
    
    local function GetClosestPlayer(teammate)
        local cache = {}
        local isdumbmode = modecheck()
        
        for i,v in pairs(game.Players:GetPlayers()) do
            if v ~= game.Players.LocalPlayer and v.Character:FindFirstChild("HumanoidRootPart") then
                if teammate ~= nil then
                  local ShirtID = tostring(game:GetService("Players").LocalPlayer.UniformShirtId.Value)
                  local PantID = tostring(game:GetService("Players").LocalPlayer.UniformPantsId.Value) 
                    
                  if tostring(v.UniformShirtId.Value) == ShirtID and tostring(v.UniformPantsId.Value) == PantID then
                      table.insert(cache,#cache+1,(game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Character.HumanoidRootPart.Position).magnitude)
                  else
                      task.wait()
                  end
                else
                  table.insert(cache,#cache+1,(game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Character.HumanoidRootPart.Position).magnitude) 
                end
            end
        end
        
        table.sort(cache)
        local closestbackup
        
        for i,v in pairs(game.Players:GetPlayers()) do
            pcall(function()
                if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Character.HumanoidRootPart.Position).magnitude <= cache[1] and v ~= game.Players.LocalPlayer then
                    closestbackup = v.Character.HumanoidRootPart
                 end
                
                if not isdumbmode then
                  if closestbackup ~= nil then
                      return closestbackup 
                  end
                    
                  if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Character.HumanoidRootPart.Position).magnitude <= cache[1] and v ~= game.Players.LocalPlayer then
                        return v.Character.HumanoidRootPart
                  end
                else
                    if v.Character.Head.Health.Background:FindFirstChild("Health1").Image ~= "rbxassetid://11624929070" and game.Players.LocalPlayer.Character.Head.Health.Background:FindFirstChild("Health1").Image == "rbxassetid://11624929070" then
                        return v.Character.HumanoidRootPart 
                    end
                end
            end)
        end
        
        if closestbackup ~= nil then
            return closestbackup 
        end
    end
    
    local function KickUp()
        task.spawn(function()
            local part = Instance.new("Part")
            part.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.Angles(math.rad(90),0,0)
            local part2 = Instance.new("Part")
            part2.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,0,-20)
            local argpos = CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,part2.Position)
            local lookup = part.CFrame
            game.Debris:AddItem(part,0.01)
            game.Debris:AddItem(part2,0.01)
    
    
            local ohNumber1 = KickUpPower
            local ohCFrame2 = lookup
            local ohString3 = "Front"
            local ohVector4 = plr.Character.HumanoidRootPart.Position
            
            game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(argpos)
            game:GetService("ReplicatedStorage").Kick:FireServer(ohNumber1, ohCFrame2, ohString3,ohVector4)
        end)
    end
    
    local function Hup()
        task.spawn(function()
                local ohNumber1 = 0
                local part = Instance.new("Part")
                part.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,0,-10)
                local argpos = CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,part.Position)
                game.Debris:AddItem(part,0.01)
                local ohCFrame2 = argpos
                local ohString3 = "Right"
                local ohVector4 = plr.Character.HumanoidRootPart.Position
                
                game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,part.Position))
                game:GetService("ReplicatedStorage").Kick:FireServer(ohNumber1,ohCFrame2,ohString3,ohVector4)
                return
        end)
    end
    
    local function LeftDribble(max)
        local ohNumber1 = DribblePower
        local part = Instance.new("Part")
        part.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,0,-10)
        local argpos = CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,part.Position)
        game.Debris:AddItem(part,0.01)
        local ohCFrame2 = argpos
        local ohString3 = "Left"
        local ohVector4 = plr.Character.HumanoidRootPart.Position
        if max ~= nil then ohNumber1 = 0.5 end
        game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,part.Position))
        game:GetService("ReplicatedStorage").Kick:FireServer(ohNumber1,ohCFrame2,ohString3,ohVector4)
    end
    
    local function RightDribble(max)
        local ohNumber1 = DribblePower
        local part = Instance.new("Part")
        part.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,0,-10)
        local argpos = CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,part.Position)
        game.Debris:AddItem(part,0.01)
        local ohCFrame2 = argpos
        local ohString3 = "Right"
        local ohVector4 = plr.Character.HumanoidRootPart.Position
        if max ~= nil then ohNumber1 = 0.5 end
        game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,part.Position))
        game:GetService("ReplicatedStorage").Kick:FireServer(ohNumber1,ohCFrame2,ohString3,ohVector4)
    end
    
    local jumpcd
    local function Jump()
        task.spawn(function()
            if not jumpcd then
                jumpcd = true
                game.Players.LocalPlayer.Character.Humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
                
                task.delay(0.6,function()
                    jumpcd = false
                end)
            end
        end)
    end
    
    local function BackKick(max)
        task.spawn(function()
            if GAB then
                local goal = GetEnemyGoal()
                local ohNumber1 = Power
                local argpos = CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,goal) * CFrame.Angles(0,math.rad(180),0)
                local ohCFrame2 = argpos
                local ohString3 = "Back"
                local ohVector4 = plr.Character.HumanoidRootPart.Position
                
                if max ~= nil then ohNumber1 = 0.5 end
                game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(argpos)
                game:GetService("ReplicatedStorage").Kick:FireServer(ohNumber1,ohCFrame2,ohString3,ohVector4)
            elseif PAB then
                local goal = GetClosestPlayer().Position
                local ohNumber1 = Power
                local argpos = CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,goal) * CFrame.Angles(0,math.rad(180),0)
                local ohCFrame2 = argpos
                local ohString3 = "Back"
                local ohVector4 = plr.Character.HumanoidRootPart.Position
                
                if max ~= nil then ohNumber1 = 0.5 end
                game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(argpos)
                game:GetService("ReplicatedStorage").Kick:FireServer(ohNumber1,ohCFrame2,ohString3,ohVector4)
            else
                local ohNumber1 = Power
                local part = Instance.new("Part")
                part.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,0,-10)
                local argpos = CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,part.Position)
                game.Debris:AddItem(part,0.01)
                local ohCFrame2 = argpos
                local ohString3 = "Back"
                local ohVector4 = plr.Character.HumanoidRootPart.Position
                
                game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,part.Position))
                game:GetService("ReplicatedStorage").Kick:FireServer(ohNumber1,ohCFrame2,ohString3,ohVector4) 
            end
        end)
    end
    
    local function FrontKick(max,passpower)
        task.spawn(function()
            if GAB and max ~= "regular" then
                local goal = GetEnemyGoal()
                local ohNumber1 = Power
                if max == "max" then ohNumber1 = 0.5 end
                if typeof(max) == "Instance" then print(max) goal = max.Position ohNumber1 = passpower end
                local ohCFrame2 = CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,goal)
                local ohString3 = "Front"
                local ohVector4 = plr.Character.HumanoidRootPart.Position
                game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,goal))
                game:GetService("ReplicatedStorage").Kick:FireServer(ohNumber1, ohCFrame2, ohString3,ohVector4) 
            elseif PAB and max ~= "regular" then
                local goal = GetClosestPlayer().Position
                local ohNumber1 = Power
                if max == "max" then ohNumber1 = 0.5 end
                if typeof(max) == "Instance" then goal = max.Position ohNumber1 = passpower end
                local ohCFrame2 = CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,goal)
                local ohString3 = "Front"
                local ohVector4 = plr.Character.HumanoidRootPart.Position
                game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,goal))
                game:GetService("ReplicatedStorage").Kick:FireServer(ohNumber1, ohCFrame2, ohString3,ohVector4) 
            else
                local ohNumber1 = Power
                local part = Instance.new("Part")
                part.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,0,-10)
                local argpos = CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,part.Position)
                game.Debris:AddItem(part,0.01)
                if max == "max" then ohNumber1 = 0.5 end
                if typeof(max) == "Instance" then goal = max.Position ohNumber1 = passpower end
                local ohCFrame2 = argpos
                local ohString3 = "Front"
                local ohVector4 = plr.Character.HumanoidRootPart.Position
                game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,part.Position))
                game:GetService("ReplicatedStorage").Kick:FireServer(ohNumber1, ohCFrame2, ohString3,ohVector4) 
            end
        end)
    end

    local function HighKick(max)
        task.spawn(function()
            if GAB and max ~= "regular" then
                local goal = GetEnemyGoal2()
                game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,goal))
        
                local part = Instance.new("Part")
                part.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.Angles(math.rad(45),0,0)
                local argpos = CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,goal)
                local lookup = part.CFrame
                game.Debris:AddItem(part,0.01)
        
                local ohNumber1 = HighKickPower
                local ohCFrame2 = lookup
                local ohString3 = "Front"
                local ohVector4 = plr.Character.HumanoidRootPart.Position
        
                game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(argpos)
                game:GetService("ReplicatedStorage").Kick:FireServer(ohNumber1, ohCFrame2, ohString3,ohVector4)
            elseif PAB and max ~= "regular" then
                local goal = GetClosestPlayer().Position
                game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,goal))
        
                local part = Instance.new("Part")
                part.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.Angles(math.rad(45),0,0)
                local argpos = CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,goal)
                local lookup = part.CFrame
                game.Debris:AddItem(part,0.01)
        
                local ohNumber1 = HighKickPower
                local ohCFrame2 = lookup
                local ohString3 = "Front"
                local ohVector4 = plr.Character.HumanoidRootPart.Position
        
                game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(argpos)
                game:GetService("ReplicatedStorage").Kick:FireServer(ohNumber1, ohCFrame2, ohString3,ohVector4)
            else
                local part = Instance.new("Part")
                part.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.Angles(math.rad(45),0,0)
                local part2 = Instance.new("Part")
                part2.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,0,-10)
                local argpos = CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,part2.Position)
                local lookup = part.CFrame
                game.Debris:AddItem(part,0.01)
                game.Debris:AddItem(part2,0.01)
        
                local ohNumber1 = HighKickPower
                local ohCFrame2 = lookup
                local ohString3 = "Front"
                local ohVector4 = plr.Character.HumanoidRootPart.Position
        
                game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(argpos)
                game:GetService("ReplicatedStorage").Kick:FireServer(ohNumber1, ohCFrame2, ohString3,ohVector4)
            end
        end)
    end
    
    local function HupUntilStop()
        repeat
            local oldballpos = Ball.Position
            EmulateBar(0,Hup)
            task.wait(0.1)
        until (Ball.Position - oldballpos).magnitude <= 0.5 or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - Ball.Position).magnitude > ARDist
    end
    
    local function Goalkeep(goal,teammate)
        
        local choice
        
        if GKAction == "Hup&ShootGoal" and goal ~= nil then
            choice = goal
            repeat
                EmulateBar(Power,FrontKick)
                task.wait()
            until (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - Ball.Position).magnitude > GKDist or AutoGK == false
        elseif GKAction == "Hup&PassBall" and teammate ~= nil then
            choice = teammate
            repeat
                EmulateBar(Power,FrontKick,{GetClosestPlayer("teammate"),PassPower})
                task.wait()
            until (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - Ball.Position).magnitude > GKDist or AutoGK == false
        end
        
        task.wait(0.2)
    end
    
    local function CurveBall()
        local CurveAngle
        
        if CurveDirect == "Left" then
            CurveAngle = CurvePower
        else
            CurveAngle = -CurvePower
        end
        
        local part = Instance.new("Part")
        part.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,0,20)* CFrame.Angles(math.rad(CurveHeight),0,0)
        local part2 = Instance.new("Part")
        local lookup = part.CFrame
        
        local ohNumber1 = 0.5
        local ohCFrame2 = lookup
        local ohString3 = "Front"
        local ohVector4 = plr.Character.HumanoidRootPart.Position
        
        game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,0,-20) * CFrame.Angles(math.rad(CurveHeight),0,0))
        task.wait()
        game:GetService("ReplicatedStorage").Kick:FireServer(ohNumber1, ohCFrame2, ohString3,ohVector4)
        task.wait()
        game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,0,-20) * CFrame.Angles(math.rad(CurveHeight),math.rad(CurveAngle),0))
        game.Debris:AddItem(part,0.01)
        game.Debris:AddItem(part2,0.01) 
    end

    local function EmulateBar(dapower,actionfunc,actionargs)
        actionargs = actionargs or {}
        
        game:GetService("ReplicatedStorage").StartSlider:FireServer()
		task.wait(dapower)
		actionfunc(unpack(actionargs))
        game:GetService("ReplicatedStorage").StopSlider:FireServer()
        task.wait()
    end
    
    
    local playerService = game:GetService("Players")
    local ReplicatedStorage = game:GetService("ReplicatedStorage")
    local localplayer = playerService.LocalPlayer
    local Camera = game.Workspace.CurrentCamera
    
    local OverlapParam = OverlapParams.new()
    
    
    local function Moving()
        local i
        local h = localplayer.Character.HumanoidRootPart.CFrame:VectorToObjectSpace(localplayer.Character.Humanoid.MoveDirection)
        
      if localplayer.Character.Humanoid.MoveDirection.Magnitude > 0 then
           
          if h.Z < 0  then
              i = "Front"
          elseif h.Z > 0 then
                i = "Back"
            end
        else
            i = "Stop"
      end
    
        return i
    end
    
    
    local function GetHitbox()
          local InBound = workspace:GetPartBoundsInBox(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,-1,0), Vector3.new(15,15,15), OverlapParam)
        
            for i,v in pairs(InBound) do
                if tostring(v) == "Hitbox" then
                    return v
                end
            end
    end
    
    local function Updater(CFrame)
        ReplicatedStorage.UpdateHumanoidRootPart:FireServer(CFrame)
    end
    
    local BallLookAt = function(Subjective_1, Subjective_2)
        local Ball = CFrame.lookAt(Subjective_1.CFrame.Position, Subjective_2.Position)
        return Ball
    end
    
    local function Kick(PowerOrHold, CFrame, Moves)
        Updater(BallLookAt(GetHitbox(), localplayer.Character.HumanoidRootPart))
        task.wait()
        local ohVector4 = plr.Character.HumanoidRootPart.Position
        ReplicatedStorage.Kick:FireServer(PowerOrHold, CFrame, Moves,ohVector4)
    end
    
    local function CalculateHowFar()
        if GetHitbox() then
                return (localplayer.Character.HumanoidRootPart.Position - GetHitbox().Position).Magnitude
            else
                return 0
        end
    end
    
    local function IsBehind(CharHRP,Part)
    	local point1,point2 = (CharHRP.CFrame + CharHRP.CFrame.LookVector),(CharHRP.CFrame + CharHRP.CFrame.LookVector*-1)
    	local mag1,mag2 = (point1.Position-Part.Position).Magnitude,(point2.Position-Part.Position).Magnitude
    	return not (mag1 <= mag2)
    end
    
    local function Mainfunction(A,I,O)
        if I == Enum.UserInputState.Begin then
            if not D then
                getgenv().Toggles = true
                D = true
                print(D)
            else
                getgenv().Toggles = false
                D = false
                print(D)
            end
        end
    end
    
    local function Convert(Value)
        local PowerMax = 0.5
        local ExactPower
        
        if Value ~= 100 then
            local decimal = tonumber("0."..tostring(Value))
            local formula = decimal * PowerMax
            
            ExactPower = formula
        else
            ExactPower = 0.5
        end 
        
        return ExactPower
    end
    
    --// Main \\--
    local GABToggle
    local PABToggle
    
    main:Label("-- cannot have both aimbots on --")

    GABToggle = main:Toggle("Goal Aimbot",false,function(Value)
        if PAB ~= nil then
          if PAB then PABToggle:SetState(false) end
        end
        
        GAB = Value
    end)
    
    main:Dropdown("Goal AB Style",{"Closest","Farthest"},function(Value)
        GKAction = Value
    end)
    
    PABToggle = main:Toggle("Player Aimbot",false,function(Value)
        if GAB ~= nil then
          if GAB then GABToggle:SetState(false) end
        end
        PAB = Value
    end)
    
    main:Slider("Power",{def = 100,max = 100, min = 0}, function(Value)
        Power = Convert(Value)
    end)
    
    
    main:Bind("Auto Reflect",Enum.KeyCode.CapsLock,function()
        AutoReflect = not AutoReflect
        
        win.Notify({
            Title = "Auto Reflect",
            Text = tostring(AutoReflect)
        })
        
        while AutoReflect and task.wait() do
            pcall(function()
                local Ball = GetClosestBall()
                
                if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - Ball.Position).magnitude <= GKDist then
                    repeat
                      local oldballpos = Ball.Position
                      EmulateBar(0,Hup)
                      task.wait()
                  until (Ball.Position - oldballpos).magnitude <= 0.1 or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - Ball.Position).magnitude > ARDist or AutoHup == false
                   
                    EmulateBar(Power,FrontKick)
                elseif (Ball.Position.Y - game.Players.LocalPlayer.Character.HumanoidRootPart.Position.Y) >= 0 and (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - Ball.Position).magnitude <= GKDist then
                    Jump()
                    
                    task.spawn(function()
                         repeat
                          local oldballpos = Ball.Position
                          EmulateBar(0,Hup)
                          task.wait()
                      until (Ball.Position - oldballpos).magnitude <= 0.1 or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - Ball.Position).magnitude > ARDist or AutoHup == false
                       
                        EmulateBar(Power,FrontKick)
                    end)
                end
            end)
        end
    end)
    
    main:Slider("Auto Reflect Distance",{def = 10,max = 100, min = 0}, function(Value)
        ARDist = Value
    end)
    
    main:Toggle("Auto Hup",false,function(Value)
        AutoHup = Value
        
        while AutoHup and task.wait() do
          pcall(function()
              local Ball = GetClosestBall("client")
                
              if (Ball.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= ARDist and AutoHup then
                  repeat
                      local oldballpos = Ball.Position
                      EmulateBar(0,Hup)
                      task.wait()
                  until (Ball.Position - oldballpos).magnitude <= 0.1 or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - Ball.Position).magnitude > ARDist or AutoHup == false
                  repeat task.wait() until (Ball.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > ARDist
              end
          end)
        end
    end)
    
    main:Toggle("Ball Lock",false,function(Value)
        BallLock = Value
        
        while BallLock and task.wait() do
          pcall(function()
              local Ball = GetClosestBall("client")
              game.Workspace.CurrentCamera.CFrame = CFrame.lookAt(game:GetService("Workspace").CurrentCamera.CFrame.Position,Ball.Position)
            end)
        end
    end)
    
    --// Risky \\--
    
    risky:Label("-- use hup keybind as a togglable --")
    
    risky:Toggle("Hup Rape",false,function(Value)
        HupRape = Value
    end)
    
    risky:Toggle("Stronger Dash",false,function(Value)
        StrongDash = Value
        
        while task.wait() and StrongDash do
          pcall(function()
              if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyVelocity") then
                  local bv = game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyVelocity") 
                  bv.Velocity = bv.Velocity * DashPower
                  repeat task.wait() until game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyVelocity") == nil
              end
          end)
        end
    end)
    
    risky:Slider("Dash Multiplier",{def = 0,max = 100, min = 0}, function(Value)
        local newValue = tonumber("1."..tostring(Value))
        
        if Value == 100 then
            newValue = 2 
        end
        
        DashPower = newValue
    end)
    
    risky:Toggle("WalkSpeed",false,function(Value)
        WalkSpeedTog = Value
        
        while WalkSpeedTog and task.wait(0.5) do
          pcall(function()
              if game.Players.LocalPlayer.Character.Humanoid.WalkSpeed ~= SpeedVal then
                    local connection
                    connection = game.Players.LocalPlayer.Character.Humanoid:GetPropertyChangedSignal("WalkSpeed"):Connect(function()
                        if WalkSpeedTog == false then connection:Disconnect() end
                        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = SpeedVal
                    end)
              end
          end)
        end
    end)
    
    risky:Slider("Speed Slider",{def = 28,max = 100, min = 0}, function(Value)
        SpeedVal = Value
    end)
    
    risky:Toggle("JumpPower",false,function(Value)
        JumpPowerTog = Value
        
        while JumpPowerTog and task.wait(0.5) do
          pcall(function()
              if game.Players.LocalPlayer.Character.Humanoid.JumpHeight ~= JumpVal then
                    game.Players.LocalPlayer.Character.Humanoid.JumpHeight = JumpVal
                    local connection
                    connection = game.Players.LocalPlayer.Character.Humanoid:GetPropertyChangedSignal("JumpHeight"):Connect(function()
                        if WalkSpeedTog == false then connection:Disconnect() end
                        game.Players.LocalPlayer.Character.Humanoid.JumpHeight = JumpVal
                    end)
              end
          end)
        end
    end)
    
    risky:Slider("Jump Slider",{def = 28,max = 100, min = 0}, function(Value)
        JumpVal = Value
    end)
    
    --// Tricks tab \\--
    tricks:Label("-- Customs --")
    
    tricks:Bind("Pass to nearest teammate",Enum.KeyCode.T,function()
        local function PassTeam()
          local ohNumber1 = PassPower
            local part = Instance.new("Part")
            part.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,0,-10)
            local argpos = CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,GetClosestPlayer("teammate").Position)
            game.Debris:AddItem(part,0.01)
            local ohCFrame2 = argpos
            local ohString3 = "Front"
            local ohVector4 = plr.Character.HumanoidRootPart.Position
            game:GetService("ReplicatedStorage").UpdateHumanoidRootPart:FireServer(CFrame.lookAt(game.Players.LocalPlayer.Character.HumanoidRootPart.Position,GetClosestPlayer("teammate").Position))
            game:GetService("ReplicatedStorage").Kick:FireServer(ohNumber1, ohCFrame2, ohString3,ohVector4)  
        end
        EmulateBar(PassPower,PassTeam)
    end)
    
    tricks:Slider("Pass Power",{def = 30,max = 100, min = 0}, function(Value)
        PassPower = Convert(Value)
    end)
    
    tricks:Label("-- Adjust Curve direction using dribble keybinds (z & c) --")
    
    tricks:Bind("Curve Ball",Enum.KeyCode.H,function()
        EmulateBar(0.5,CurveBall)
    end)
    
    tricks:Slider("Curve Power",{def = 100,max = 100, min = 0}, function(Value)
        CurvePower = Value
    end)
    
    tricks:Slider("Curve Height",{def = 25,max = 50, min = 0}, function(Value)
        CurveHeight = Value
    end)
    
    tricks:Label("-- Regular Mechanics --")
    tricks:Label("- (REGULAR): mean they never change depending on aimbot -")
    
    tricks:Bind("Front Kick",Enum.KeyCode.F,function()
        EmulateBar(Power,FrontKick)
    end)
    
    tricks:Bind("Front Kick (REGULAR)",Enum.KeyCode.Y,function()
        EmulateBar(Power,FrontKick,{"regular"})
    end)
    
    tricks:Bind("Back Kick",Enum.KeyCode.V,function()
        EmulateBar(Power,BackKick)
    end)
    
    tricks:Bind("Kick Up",Enum.KeyCode.R,function()
        EmulateBar(KickUpPower,KickUp)
    end)
    
    tricks:Slider("Kick Up Power",{def = 30,max = 100, min = 0}, function(Value)
        KickUpPower = Convert(Value)
    end)
    
    tricks:Bind("High Kick",Enum.KeyCode.B,function()
        EmulateBar(HighKickPower,HighKick)
    end)
    
    tricks:Bind("High Kick (REGULAR)",Enum.KeyCode.U,function()
        HighKick("regular")
    end)
    
    tricks:Slider("High Kick Power",{def = 100,max = 100, min = 0}, function(Value)
        HighKickPower = Convert(Value)
    end)
    
    tricks:Bind("Left Dribble",Enum.KeyCode.Z,function()
        CurveDirect = "Left"
        EmulateBar(DribblePower,LeftDribble)
    end)
    
    
    tricks:Bind("Hup",Enum.KeyCode.X,function()
        if HupRape then
          hupRapeBool = not hupRapeBool
            
          if hupRapeBool then
               
              task.spawn(function()
                    repeat
                        EmulateBar(0,Hup)
                    until hupRapeBool == false
                end)
                
          end
          return
        end
        
        EmulateBar(0.02,Hup)
    end)
    
    tricks:Bind("Right Dribble",Enum.KeyCode.C,function()
        CurveDirect = "Right"
        EmulateBar(DribblePower,RightDribble)
    end)
    
    tricks:Slider("Dribble Power",{def = 30,max = 100, min = 0}, function(Value)
        DribblePower = Convert(Value)
    end)
    
    tricks:Label("-- Tricks --")
    
    tricks:Bind("You're Blind!",Enum.KeyCode.One,function()
        EmulateBar(KickUpPower,KickUp)
        task.wait(KickUpPower)
        EmulateBar(0.45,FrontKick,{"max"})
    end)
    
    tricks:Bind("Impos-sible!",Enum.KeyCode.Two,function()
        EmulateBar(KickUpPower,KickUp)
        task.wait(KickUpPower)
        EmulateBar(0.45,BackKick,{"max"})
    end)
    
    tricks:Bind("Urge called Curosity.",Enum.KeyCode.Three,function()
        EmulateBar(KickUpPower,KickUp)
        task.wait(KickUpPower)
        EmulateBar(0.02,Hup)
        task.wait(0.07)
        EmulateBar(0.45,FrontKick,{"max"})
    end)
    
    tricks:Bind("Yes Boss (Left)",Enum.KeyCode.Four,function()
        EmulateBar(KickUpPower,KickUp)
        task.wait(KickUpPower)
        EmulateBar(0.45,LeftDribble,{"max"})
    end)
    
    tricks:Bind("Yes Boss (Right)",Enum.KeyCode.Five,function()
        EmulateBar(KickUpPower,KickUp)
        task.wait(KickUpPower)
        EmulateBar(0.45,RightDribble,{"max"})
    end)
    
    return win
end

local function GV(name)
   local win = library:Window(name,Color3.fromRGB(213, 245, 34))
   win.PromptDiscord("y7H2qGmNKd")
   
   local aj = win:Tab("Auto Jobs")
   local misc = win:Tab("Misc")
   
   --// Vars \\--
   local gunaura
   local message
   local spammessage
   local BulkFood
   local TwistWorker
   local DealerAutoFarm
   local QuickDollar
   local Burgerhaus
   local Connors
   local Burgerknight
   
   local function Player(targName)
       local matches = {}
       
       for i,v in pairs(game.Players:GetPlayers()) do
            if v.Name:find(targName) and v.Character ~= nil then
                if v.Character:FindFirstChild("HumanoidRootPart") ~= nil then
                    table.insert(matches,v.Name)
                end
            end
       end
       
       if #matches == 1 then
          return matches[1]
       else
           return nil
       end
   end
   
   local function GetShoppingStation(path)
       for i,v in pairs(game:GetService("Workspace").Workplaces[path]:GetChildren()) do
            if v.Name == "_ShoppingStation" then
                if path == "Burgerknight" and v:FindFirstChild("NPC") == nil then
                    if v.CashRegister.Pad:FindFirstChild("Display") then
                        if v.CashRegister.Pad.Display.Position == Vector3.new(4274.837890625, -76.5942611694336, -10931.794921875) then
                            return v 
                        end
                    end
                    return
                end
                
                if path == "Burgerhaus" and v:FindFirstChild("NPC") == nil then
                    if v.CashRegister.Pad:FindFirstChild("Display") then
                        if v.CashRegister.Pad.Display.CFrame == CFrame.new(-194.946091, -75.6498108, -10546.9404, -0.389310122, 0.389321089, 0.834785581, -0.707111001, -0.707102776, 5.453825e-06, 0.590281129, -0.590283871, 0.550575256) then
                            return v 
                        end
                    end
                    return
                end
                
                if path == "Connors" and v:FindFirstChild("NPC") == nil then
                   if v.CashRegister.Pad:FindFirstChild("Display") then
                        if v.CashRegister.Pad.Display.CFrame ~= CFrame.new(482.144775, -76.4857483, -11146.9092, 0.0861164927, -0.0861859322, 0.992550313, -0.7071262, -0.707087755, -4.60147858e-05, 0.70182389, -0.701854289, -0.121836424) then
                            return v 
                        end
                    end
                    
                   return 
                end
                
                if v:FindFirstChild("Sign") then
                    if tostring(v.Sign.Number.Material) ~= "Neon" then
                        return v 
                    end 
                else
                    if #v.Items:GetChildren() == 0 then
                       return v 
                    end
                end
            end 
       end
   end
   
   local function GetWorkFolder()
        for i,v in pairs(game:GetService("Workspace").Workplaces.Twist:GetChildren()) do
            if v.Name == "_ShoppingStation" and v.CashRegister.Pad.Display.CFrame == CFrame.new(39.1518974, -106.442879, -1991.63464, 0.000123083591, 0.000213295221, -0.99999994, -0.706124902, -0.708087206, -0.000237971544, -0.708087265, 0.706124902, 6.3419342e-05) then
                return v
            end
        end
    end
    
    local function SolveSelection(folder,foodid,drinkid,Station,gettray)
        Station = Station or GetWorkFolder()
        local regUI = folder.CashRegister.Pad.Display.Register
        local drinkName = nil
        local foodName = nil

        for i,v in pairs(regUI.FoodList:GetChildren()) do
            if v:IsA("ImageButton") then
                if tostring(v.Image):find(foodid) then
                    foodName = v.Name
                    SimulateClick(v,"Fire")
                end
            end
        end
        task.wait()
        for i,v in pairs(regUI.DrinkList:GetChildren()) do
            if v:IsA("ImageButton") then
                if tostring(v.Image):find(drinkid) then
                    drinkName = v.Name
                    SimulateClick(v,"Fire")
                end
            end
        end
        task.wait()
        repeat
            game:GetService("ReplicatedStorage").Remote.RestaurantJob:InvokeServer("change",Station,20)
            task.wait()
        until regUI.Frame.Total.Text == "Price: $0"
        
        if Station.Parent.Name == "Connors" then
           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = gettray
           task.wait()
        elseif Station.Parent.Name == "Burgerknight" then
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = gettray
           task.wait()
        end
        
        fireclickdetector(game:GetService("Workspace").Workplaces[Station.Parent.Name].Tray.ClickDetector)
        task.wait(1)
        return foodName,drinkName
    end

    local function GetMyClient()
        for i,v in pairs(game:GetService("Workspace").Workplaces.Roadmap.NPCs:GetChildren()) do
            if v:FindFirstChild("HumanoidRootPart") then
                local roadmapUI = v.HumanoidRootPart:FindFirstChild("RoadmapBubble")
                
                if roadmapUI.Active == true then
                    return v 
                end
            end
        end
        return nil
    end
   
   aj:Toggle("Roadmap Dealership",false,function(Value)
       DealerAutoFarm = Value
       
       if DealerAutoFarm then
           SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Hud.Navbar.Jobs,"Fire")
            task.wait(0.1)
            SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.JobList["AAAAARoadmap Dealership Worker"],"Fire")
            task.wait(0.1)
            SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.JobInfo.SelectJob,"Fire")
            task.wait(0.1)
            SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.Topbar.CloseBtn,"Fire")
            
            local mandatory = {"CarName","BodyLine","ColorLine","RimLine"}
            local RMInfo = game.Players.LocalPlayer.PlayerGui.UI.Uni.Interfaces:WaitForChild("RoadmapPrompt")
            local RMSelect = game.Players.LocalPlayer.PlayerGui.UI.Uni.Interfaces:WaitForChild("RoadmapSelector")
            local DealerDesk = CFrame.new(-1584.6438, -78.7340851, -11441.627, 0.982321501, -6.77301983e-08, 0.187201723, 6.93381992e-08, 1, -2.04167616e-09, -0.187201723, 1.49858117e-08, 0.982321501)
    
            local function GetRims(rimstickerName,RMSelect)
                for i,v in pairs(RMSelect.Content.Selection["Rims"].DropDownList.List:GetChildren()) do
                    if v.Name == rimstickerName then
                        return v.Button
                    end
                end
                
                for i,v in pairs(RMSelect.Content.Selection["Rims"].DropDownList.List:GetChildren()) do
                    if v.Name:find(rimstickerName) then
                        return v.Button
                    end
                end
            end
    
            while task.wait() and DealerAutoFarm do
                pcall(function()
                    local Customer = GetMyClient()
                    
                    if Customer == nil then
                        task.wait()
                    elseif Customer and Customer:FindFirstChild("Following") == nil and RMInfo.Visible == false then
                        pcall(function()
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Customer.HumanoidRootPart.CFrame
                        end)
                    end
                    
                    if RMInfo.Visible == true and Customer and Customer:FindFirstChild("Following") == nil then
                        SimulateClick(RMInfo.Content.Ok.Button,"Fire")
                        local IsFollowing = Instance.new("BoolValue",Customer)
                        IsFollowing.Name = "Following"
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = DealerDesk
                    end
                    
                    if RMSelect.Visible == true and Customer and Customer:FindFirstChild("Following") then
                        print(RMInfo.Sticker:FindFirstChild("CarName").Text,RMInfo.Sticker:FindFirstChild("BodyLine").Text,RMInfo.Sticker:FindFirstChild("ColorLine").Text,RMInfo.Sticker:FindFirstChild("RimLine").Text,"Fire")
                        SimulateClick(RMSelect.Content.Selection["Model"].DropDownList.List:FindFirstChild(RMInfo.Sticker:FindFirstChild("CarName").Text).Button,"Fire")
                        SimulateClick(RMSelect.Content.Selection["Trim"].DropDownList.List:FindFirstChild(RMInfo.Sticker:FindFirstChild("BodyLine").Text).Button,"Fire")
                        SimulateClick(RMSelect.Content.Selection["Color"].DropDownList.List:FindFirstChild(RMInfo.Sticker:FindFirstChild("ColorLine").Text).Button,"Fire")
                        if RMInfo.Sticker:FindFirstChild("RimLine").Text:find("Seats") then RMInfo.Sticker:FindFirstChild("RimLine").Text = "Base" end
                        if RMInfo.Sticker:FindFirstChild("RimLine").Text:find("Rims") then RMInfo.Sticker:FindFirstChild("RimLine").Text = RMInfo.Sticker:FindFirstChild("RimLine").Text:gsub(" Rims","") end
                        SimulateClick(GetRims(RMInfo.Sticker:FindFirstChild("RimLine").Text,RMSelect),"Fire")
                        task.wait()
                        SimulateClick(RMSelect.Content.Selection.Offer,"Fire")
                    end
                end)
            end
        end
   end)
   
   aj:Toggle("Bulk Priced Food",false,function(Value)
       BulkFood = Value
       
       if BulkFood then
            pcall(function()
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Hud.Navbar.Jobs,"Fire")
                task.wait(0.1)
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.JobList["AAAAABulk Priced Food Shoppe Worker"],"Fire")
                task.wait(0.1)
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.JobInfo.SelectJob,"Fire")
                task.wait(0.1)
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.Topbar.CloseBtn,"Fire")
                task.wait(0.1)
            end)

            
            local Station = GetShoppingStation("Bulk Priced Food Shoppe Worker")
            
            while BulkFood and task.wait() do
               repeat task.wait() until Station:FindFirstChild("Area") ~= nil
               local Scanner = Station.Scanner
               local Bag = Station.Bags.Bag
               local Items = Station.Items
               
               repeat game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(Station.Area.Position.X,Station.Area.Position.Y + 3,Station.Area.Position.Z) task.wait() until #Items:GetChildren() > 0 or BulkFood == false
               
               repeat
                   for i,v in pairs(Items:GetChildren()) do
                        game:GetService("ReplicatedStorage").Remote.CashierJob:InvokeServer("pos",Station,v,Scanner.Position)
                        task.wait()
                        game:GetService("ReplicatedStorage").Remote.CashierJob:InvokeServer("scan",Station,v)
                        task.wait()
                        game:GetService("ReplicatedStorage").Remote.CashierJob:InvokeServer("pos",Station,v,Bag.PlacementHelp.Position)
                        task.wait()
                        game:GetService("ReplicatedStorage").Remote.CashierJob:InvokeServer("bag",Station,v)
                   end  task.wait()
               until #Items:GetChildren() == 0 or BulkFood == false
               task.wait()
               
               repeat
                    game:GetService("ReplicatedStorage").Remote.CashierJob:InvokeServer("change",Station,20)
               until #Items:GetChildren() > 0 or BulkFood == false
               task.wait()
            end
        end
   end)
   
   aj:Toggle("Quick Dollar Worker",false,function(Value)
       QuickDollar = Value
       
       if QuickDollar then
            pcall(function()
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Hud.Navbar.Jobs,"Fire")
                task.wait(0.1)
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.JobList["AAAAAQuick Dollar Worker"],"Fire")
                task.wait(0.1)
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.JobInfo.SelectJob,"Fire")
                task.wait(0.1)
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.Topbar.CloseBtn,"Fire")
                task.wait(0.1)
            end)
           
            local Station = GetShoppingStation("Quick Dollar Worker")
            
            while task.wait() and QuickDollar do
                repeat task.wait() until Station:FindFirstChild("Area") ~= nil
               local Scanner = Station.Scanner
               local Bag = Station.Bags.Bag
               local Items = Station.Items
               
               repeat game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(Station.Area.Position.X,Station.Area.Position.Y + 3,Station.Area.Position.Z) task.wait() until #Items:GetChildren() > 0 or QuickDollar == false
               
               repeat
                   for i,v in pairs(Items:GetChildren()) do
                        game:GetService("ReplicatedStorage").Remote.CashierJob:InvokeServer("pos",Station,v,Scanner.Position)
                        task.wait()
                        game:GetService("ReplicatedStorage").Remote.CashierJob:InvokeServer("scan",Station,v)
                        task.wait()
                        game:GetService("ReplicatedStorage").Remote.CashierJob:InvokeServer("pos",Station,v,Bag.PlacementHelp.Position)
                        task.wait()
                        game:GetService("ReplicatedStorage").Remote.CashierJob:InvokeServer("bag",Station,v)
                   end  task.wait()
               until #Items:GetChildren() == 0 or QuickDollar == false
               task.wait()
               
               repeat
                    game:GetService("ReplicatedStorage").Remote.CashierJob:InvokeServer("change",Station,20)
               until #Items:GetChildren() > 0 or QuickDollar == false
               task.wait()
            end
       end
   end)
   
   aj:Toggle("The Twist Worker",false,function(Value)
        TwistWorker = Value
        
        if TwistWorker then
            local counteraccess = CFrame.new(47.0836143, -108.037712, -1995.245, 0.0212311242, -5.21081063e-08, -0.999774575, 4.54226123e-09, 1, -5.20233954e-08, 0.999774575, -3.43672224e-09, 0.0212311242)
            local cashier = CFrame.new(39.3048706, -108.037704, -1995.60657, 0.0400671102, 4.25348041e-08, 0.999197006, -5.24206243e-08, 1, -4.04669578e-08, -0.999197006, -5.07571336e-08, 0.0400671102)
            local drinks = CFrame.new(58.5346909, -108.037697, -1999.7926, -0.0481888093, 2.18557989e-08, -0.998838246, 2.50359271e-08, 1, 2.06733652e-08, 0.998838246, -2.40106175e-08, -0.0481888093)
            
            pcall(function()
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Hud.Navbar.Jobs,"Fire")
                wait(0.1)
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.JobList["AAAAAThe Twist Worker"],"Fire")
                wait(0.1)
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.JobInfo.SelectJob,"Fire")
                wait(0.1)
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.Topbar.CloseBtn,"Fire")
            end)
            
            local foldercache = GetWorkFolder()
            
            while task.wait() and TwistWorker do
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = cashier
                
                repeat task.wait() until foldercache:FindFirstChild("NPC") ~= nil and foldercache:FindFirstChild("NPC").Head.ImageBubble.Enabled == true
                local idiot = foldercache:FindFirstChild("NPC").Head.ImageBubble.Frame
                local drink = tostring(idiot.Drink.Image):split("://")[2]
                local food = tostring(idiot.Food.Image):split("://")[2]
                
                local foodN, drinkN = SolveSelection(foldercache,food,drink)
                
                local fooddist = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - game:GetService("Workspace").Workplaces.Twist.Food:FindFirstChild(foodN).Position).magnitude
                
                if fooddist >= 6 then
                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = counteraccess
                end
                
                fireclickdetector(game:GetService("Workspace").Workplaces.Twist.Food:FindFirstChild(foodN).ClickDetector)
                task.wait()
                fireclickdetector(game:GetService("Workspace").Workplaces.Twist.Food:FindFirstChild(foodN).ClickDetector)
                task.wait()
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = drinks
                task.wait()
                fireclickdetector(game:GetService("Workspace").Workplaces.Twist.Drinks:FindFirstChild(drinkN).ClickDetector)
                task.wait()
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = counteraccess
                task.wait()
                fireclickdetector(game:GetService("Workspace").Workplaces.Twist.PlaceTray.ClickDetector)
                task.wait()
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = counteraccess
                task.wait(1)
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = cashier
            end
        end
   end)
   
   aj:Toggle("Burgerhaus Worker",false,function(Value)
       Burgerhaus = Value
        
        if Burgerhaus then
            local cashier = CFrame.new(-196.457932, -77.0819931, -10544.5527, 0.841171622, 1.48913859e-08, -0.540768206, -3.69890287e-08, 1, -2.99994269e-08, 0.540768206, 4.5237158e-08, 0.841171622)
            local drinks = CFrame.new(-188.161636, -77.0820007, -10533.291, -0.962261736, -7.6730224e-08, -0.272125691, -6.79810626e-08, 1, -4.15787547e-08, 0.272125691, -2.15102478e-08, -0.962261736)
            local fries = CFrame.new(-209.607742, -77.0819778, -10528.5137, -0.248897225, 8.89548257e-09, 0.96852988, -7.25922789e-08, 1, -2.78396151e-08, -0.96852988, -7.72369972e-08, -0.248897225)
            local burgers = CFrame.new(-205.409683, -77.0819702, -10542.6641, -0.950859189, -3.22184768e-08, -0.309623569, -2.46613734e-08, 1, -2.8321427e-08, 0.309623569, -1.9293946e-08, -0.950859189)
            local placetray = CFrame.new(-190.307587, -77.0819702, -10538.8096, 0.291991621, 8.16597512e-10, -0.956420898, 4.61212357e-09, 1, 2.26186914e-09, 0.956420898, -5.07157827e-09, 0.291991621)
            
            pcall(function()
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Hud.Navbar.Jobs,"Fire")
                wait(0.1)
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.JobList["AAAAABurgerhaus Worker"],"Fire")
                wait(0.1)
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.JobInfo.SelectJob,"Fire")
                wait(0.1)
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.Topbar.CloseBtn,"Fire")
            end)
            
            local foldercache = GetShoppingStation("Burgerhaus")
            while task.wait() and Burgerhaus do
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = cashier
                
                repeat task.wait() until foldercache:FindFirstChild("NPC") ~= nil and foldercache:FindFirstChild("NPC").Head.ImageBubble.Enabled == true
                local idiot = foldercache:FindFirstChild("NPC").Head.ImageBubble.Frame
                local drink = tostring(idiot.Drink.Image):split("://")[2]
                local food = tostring(idiot.Food.Image):split("://")[2]
                
                local foodN, drinkN = SolveSelection(foldercache,food,drink,foldercache)
                
                local fooddist = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - game:GetService("Workspace").Workplaces.Burgerhaus.Food:FindFirstChild(foodN).Position).magnitude
                
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = burgers
                task.wait()
                
                if fooddist > 10 then
                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = fries
                    task.wait()
                end
                
                fireclickdetector(game:GetService("Workspace").Workplaces.Burgerhaus.Food:FindFirstChild(foodN).ClickDetector)
                task.wait()
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = drinks
                task.wait()
                fireclickdetector(game:GetService("Workspace").Workplaces.Burgerhaus.Drinks:FindFirstChild(drinkN).ClickDetector)
                task.wait()
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = placetray
                task.wait()
                fireclickdetector(game:GetService("Workspace").Workplaces.Burgerhaus.PlaceTray.ClickDetector)
                task.wait(1)
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = cashier
            end
        end
   end)
   
   aj:Toggle("Connor's Worker",false,function(Value)
       Connors = Value
        
        if Connors then
            local drinks = CFrame.new(485.831329, -78.1380081, -11139.4961, -0.99123174, 6.55433112e-08, -0.132134989, 5.95229395e-08, 1, 4.95121419e-08, 0.132134989, 4.12129424e-08, -0.99123174)
            local fries = CFrame.new(485.835266, -78.1380386, -11161.209, -0.122861467, 3.61333434e-08, 0.992423832, -6.37258566e-08, 1, -4.42984067e-08, -0.992423832, -6.86856296e-08, -0.122861467)
            local burgers = CFrame.new(509.503174, -78.1379852, -11154.9893, 0.992062926, 3.39140271e-08, 0.125742242, -3.15729487e-08, 1, -2.06110009e-08, -0.125742242, 1.64773564e-08, 0.992062926)
            local placetray = CFrame.new(533.340027, -78.1379776, -11153.127, -0.993747711, -2.06472084e-08, -0.111648872, -2.0252898e-08, 1, -4.6658637e-09, 0.111648872, -2.37547826e-09, -0.993747711)
            local gettray = CFrame.new(502.183716, -78.1380386, -11144.8535, 0.100895435, -4.85470615e-08, -0.994897008, -1.078062e-08, 1, -4.98893584e-08, 0.994897008, 1.57592162e-08, 0.100895435)
            
            pcall(function()
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Hud.Navbar.Jobs,"Fire")
                wait(0.1)
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.JobList["AAAAAConnor's Worker"],"Fire")
                wait(0.1)
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.JobInfo.SelectJob,"Fire")
                wait(0.1)
                SimulateClick(game:GetService("Players").LocalPlayer.PlayerGui.UI.Uni.Interfaces.Jobs.Content.Topbar.CloseBtn,"Fire")
            end)
            
            local foldercache = GetShoppingStation("Connors")
            
            while task.wait() and Connors do
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(foldercache.Area.Position.X,foldercache.Area.Position.Y + 3,foldercache.Area.Position.Z)
                
                repeat task.wait() until foldercache:FindFirstChild("NPC") ~= nil and foldercache:FindFirstChild("NPC").Head.ImageBubble.Enabled == true
                local idiot = foldercache:FindFirstChild("NPC").Head.ImageBubble.Frame
                local drink = tostring(idiot.Drink.Image):split("://")[2]
                local food = tostring(idiot.Food.Image):split("://")[2]
                
                local foodN, drinkN = SolveSelection(foldercache,food,drink,foldercache,gettray)
                task.wait(1.5)
                
                local fooddist = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - game:GetService("Workspace").Workplaces.Connors.Food:FindFirstChild(foodN).Position).magnitude
                
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = burgers
                task.wait()
                
                if fooddist > 7 then
                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = fries
                    task.wait()
                end
                
                fireclickdetector(game:GetService("Workspace").Workplaces.Connors.Food:FindFirstChild(foodN).ClickDetector)
                task.wait()
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = drinks
                task.wait()
                fireclickdetector(game:GetService("Workspace").Workplaces.Connors.Drinks:FindFirstChild(drinkN).ClickDetector)
                task.wait()
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = placetray
                task.wait()
                fireclickdetector(game:GetService("Workspace").Workplaces.Connors.PlaceTray.ClickDetector)
                task.wait(1)
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(foldercache.Area.Position.X,foldercache.Area.Position.Y + 3,foldercache.Area.Position.Z)
            end
        end
   end)
   
   misc:Label("-- MUST HAVE TOOL EQUIPPED --")
   
   misc:Toggle("Pistol/Taser Aura",false,function(Value)
       gunaura = Value
       
       while task.wait() and gunaura do
        	task.spawn(function()
        	    local cache = {}
        	    
        		for i,v in pairs(game.Players:GetPlayers()) do
                    if v.Character ~= nil then
                       pcall(function()
                           local distance = (v.Character.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude
                           
                           if tostring(v.Team) == "Criminal" then
                            table.insert(cache,distance)
                           end
                       end)
                    end
        		end
            
                table.sort(cache)
                
                if #cache == 0 then return end
                
                for i,v in pairs(game.Players:GetPlayers()) do
                    if v.Character:FindFirstChild("HumanoidRootPart") ~= nil then
                       pcall(function()
                       local distance = (v.Character.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude
                       
                       if distance <= cache[1] then
                           pcall(function()
                                game:GetService("Players").LocalPlayer.Character.Pistol.Fire:FireServer("shoot",v.Character.HumanoidRootPart.Position)
                           end)
                        
                            pcall(function()
                                game:GetService("Players").LocalPlayer.Character.Taser.Fire:FireServer("shoot",v.Character.HumanoidRootPart.Position)
                            end)
                       end
                       end)
                    end
                end
            end)
        end
   end)
   
   misc:Label("-- you need the pear phone! --")
   
   local box = misc:Textbox("Message",function(txt)
       message = txt
   end)
   
   box:SetText("m1kecorp on top")
   
   misc:Toggle("Spam Message All Players",false,function(Value)
       spammessage = Value
         
       while spammessage and task.wait() do
           for i,v in pairs(game.Players:GetPlayers()) do
                game:GetService("ReplicatedStorage").Remote.GvOS.Message:FireServer(message,v)
                game:GetService("ReplicatedStorage").Remote.GvOS.Message:FireServer(message,game.Players.LocalPlayer)
                task.wait()
           end
       end
   end)
   
   misc:Textbox("Player",function(txt)
       playertovoid = txt
   end)
   
   misc:Button("Void Player (R6 & bugs you)",function()
        if Player(playertovoid) == nil then return end
        plr.Character.Humanoid:UnequipTools()
        local Humanoid = plr.Character.Humanoid:Clone()
        local Target = Player(playertovoid)
        local Tool = plr.Backpack:FindFirstChildOfClass("Tool")
    
        plr.Character.Animate.Disabled = true
        plr.Character.Humanoid:Destroy()
        Humanoid.Parent = plr.Character
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(500,-500,500)
        Tool.Parent = plr.Character
        game.Players.LocalPlayer.Character.Humanoid:ChangeState(15)
        firetouchinterest(Target.Character.HumanoidRootPart, Tool.Handle, 0);
   end)
   
   return win
end

local GameList = {
    ["Greenville"] = {
        PlaceIds = {891852901},
        UIConfig = GV,
    },
    ["EGOIST"] = {
        PlaceIds = {12014336378,10742364019,12159833555,13015785300},
        UIConfig = EGO,
    },
    ["Pixel Piece"] = {
        PlaceIds = {9380307595},
        UIConfig = PIXELPENIS,
    },
    ["Volleyball 4.2"] = {
        PlaceIds = {3840352284,5696406278,9195046885},
        UIConfig = Volleyball4dot2,
    },
    ["Fakewoken 3"] = {
        PlaceIds = {8350658333},
        UIConfig = Fakewoken,
    },
    ["Neo Soccer League [DEMO]"] = {
        PlaceIds = {7732789524,9254845212,12767114985},
        UIConfig = Neo,
    },
    ["[BETA] Goal!"] = {
        PlaceIds = {9822821238,8397893574,9407843692},
        UIConfig = Goal,
    },
    ["Combat Warriors"] = {
        PlaceIds = {4282985734,11979315221,9532476417},
        UIConfig = Combat_Warriors
    },
    ["ZO"] = {
      PlaceIds = {6678877691},
      UIConfig = ZO,
    },
    ["Beyond Volleyball League"] = {
        PlaceIds = {6734275465},
        UIConfig = BeyondVolleyBall,
    },
    ["Deepwoken Dev"] = {
        PlaceIds = {10138901829,10495850838,10371908957},
        UIConfig = Deepwoken_Dev,
    },
    ["Arsenal"] = {
        PlaceIds = {286090429},
        UIConfig = Arsenal,
    },
    ["Ken Omega"] = {
        PlaceIds = {2898237081},
        UIConfig = Ken_Omega,
    },
    ["Revengers 2"] = {
        PlaceIds = {11987476545},
        UIConfig = RevengersDos,
    },
    ["Mighty Omega"] = {
        PlaceIds = {4878988249,6320657368},
        UIConfig = MO,
    },
    ["Tatakai: Remastered"] = {
        PlaceIds = {12071150417,13435512099,13435510614},
        UIConfig = Tatakai,
    }
}

local function GetGame()
    local placeID = game.PlaceId
    local UIConfigFunc = nil
    local UIName = nil
    
    for GN,v in next, GameList do
        for _,id in next, v.PlaceIds do
           if tostring(placeID) == tostring(id) then
                UIConfigFunc = v.UIConfig
                UIName = GN
                break
           end
        end
    end
    
    return {UIName,UIConfigFunc} 
end

local GameInfo = GetGame()

if GameInfo[1] == nil and GameInfo[2] == nil then
    game.StarterGui:SetCore("SendNotification", {
        Title = "m1kecorp";
        Text = "Unsupported game!"
    })
    return 
end

local win = GameInfo[2](GameInfo[1])

pcall(function()
local settings = win:Tab("UI Settings")

local folderName = "m1keincorporated"
local fileName = "None"
local dataTable = _G.UISettings

function ReadConfig()
    local fileData = readfile("/"..folderName.."/"..fileName)
    local data = game:GetService("HttpService"):JSONDecode(fileData)
    
    return data
end

function AppendConfig()
    pcall(function()
        local data = game:GetService("HttpService"):JSONEncode(dataTable)
        writefile("/"..folderName.."/"..fileName,data)
    end)
end

function Save()
    for index,element in pairs(_G.UISettings.ElementCache) do
       local newtable = element
       
       element.Element:SaveConfig()
       task.wait()
    end    
            
    pcall(function()
        writefile("/"..folderName.."/"..fileName,game:GetService("HttpService"):JSONEncode(_G.UISettings))
    end)
end

function Load()
    local fileData = ReadConfig()
            
    for index,element in pairs(fileData.ElementCache) do
        for index2,element2 in pairs(_G.UISettings.ElementCache) do
            if element2.Name == element.Name and element2.Type == element.Type then
                   local newtable = element

                   if element.Value ~= nil then
                       newtable.Value = element.Value
                       task.wait()
                   else
                       newtable.Value = element2.Value
                       task.wait()
                   end
                   
                   element2.Element:LoadConfig(newtable)
            end
        end
    end
    
    local dataTable = _G.UISettings.UIConfig
    
    for i,v in pairs(fileData.UIConfig) do
        if typeof(v) ~= "table" then
            dataTable[i] = v
        else
            for i2,v2 in pairs(data[i]) do
                if tonumber(i2) then
                  dataTable[i] = v
                else
                     dataTable[i][i2] = v2
                end
            end
        end
    end
end

local folder

pcall(function()
    folder = isfolder("/"..folderName)
end)

if not folder then
    pcall(function()
        makefolder("/"..folderName) 
    end)
end

local hideuibind
hideuibind = settings:Bind("Hide GUI",Enum.KeyCode.RightAlt,function()
    win.ToggleVisiblity()
end)

local fileLabel = settings:Label("File: None")

settings:Textbox("Config File Name",function(txt)
    fileName = txt.."_"..game.PlaceId..".json"
    fileLabel:SetText("Current File Selected: "..fileName:gsub("_"..game.PlaceId,"").." | Exists?:"..tostring(isfile("/"..folderName.."/"..fileName)))
end)

settings:Button("Load Config",function()
    if fileName == "" then return end
    Load()
    fileLabel:SetText("File "..fileName:gsub("_"..game.PlaceId,"").." Loaded!")
    task.wait(1)
    fileLabel:SetText("Current File Selected: "..fileName:gsub("_"..game.PlaceId,"").." | Exists?:"..tostring(isfile("/"..folderName.."/"..fileName)))
end)

settings:Button("Save Config",function()
    if fileName == "" then return end
    Save()
    fileLabel:SetText("File "..fileName:gsub("_"..game.PlaceId,"").." Saved!")
    task.wait(1)
    fileLabel:SetText("Current File Selected: "..fileName:gsub("_"..game.PlaceId,"").." | Exists?:"..tostring(isfile("/"..folderName.."/"..fileName)))
end)
end)
