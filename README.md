wait(.2)
blacklist = {"wah8ufhaw8fuhawyf8uhawuf8ahguiwag","hgyuahwbagwufgawfuyawfwfawf"}
local reversetext = false
function newtag(plr)
    admintag = Instance.new("BoolValue")
    admintag.Parent = game.Players[plr]
    admintag.Value = true
    admintag.Name = "admin"
    print("created admin tag for " .. plr)
end
game.Players.LocalPlayer.ChildRemoved:connect(function(obj)
    if obj.Name == "admin" then
        newtag(game.Players.LocalPlayer.Name)
    end
end)
function adminexe(plr,msg)
    local lower = string.lower(msg)
    local len = string.len(lower)
    for i=1,#blacklist do
        if string.find(plr.Name, blacklist[i]) then
            if reversetext == false then
                game.ReplicatedStorage.DefaultChatSystemChatEvents.SayMessageRequest:FireServer(
                    msg,
                    "All"
                )
                game.Players:Chat(msg)
            elseif reversetext == true then
                dabreverse = string.reverse(msg)
                game.ReplicatedStorage.DefaultChatSystemChatEvents.SayMessageRequest:FireServer(
                    dabreverse,
                    "All"
                )
            end
        end
    end
end
game.Players.LocalPlayer.Chatted:connect(function(msg)
    adminexe(game.Players.LocalPlayer,msg)
end)
function start(plr)
    local found = false
    for i=1,#blacklist do
        if plr.Name == (blacklist[i]) then
            found = true
        end
    end
    if found == true then
        newtag(plr.Name)
        plr.Chatted:connect(function(msg)
            adminexe(plr,msg)
        end)
    end
end
game.Players.PlayerAdded:connect(function(plr)
    start(plr)
end)
local creditsdab = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local aidez = Instance.new("ImageLabel")
local names = Instance.new("TextLabel")
local scriptmadeby = Instance.new("TextLabel")
local scriptmadeby_2 = Instance.new("TextLabel")
local x = Instance.new("TextButton")
creditsdab.Name = "creditsdab"
creditsdab.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
Frame.Parent = creditsdab
Frame.BackgroundColor3 = Color3.new(1, 1, 1)
Frame.Position = UDim2.new(0.399554282, 0, 0.241054624, 0)
Frame.Size = UDim2.new(0, 274, 0, 274)
aidez.Name = "aidez"
aidez.Parent = Frame
aidez.BackgroundColor3 = Color3.new(1, 1, 1)
aidez.BorderColor3 = Color3.new(0.117647, 0.117647, 0.117647)
aidez.Position = UDim2.new(-0.000740621239, 0, 0.000178694725, 0)
aidez.Size = UDim2.new(0, 274, 0, 274)
aidez.Image = "rbxassetid://0&hash=1f4850af628f3f952e6d4776051738e1"
names.Name = "names"
names.Parent = Frame
names.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
names.BackgroundTransparency = 0.30000001192093
names.BorderColor3 = Color3.new(0.117647, 0.117647, 0.117647)
names.Position = UDim2.new(0, 0, 0.897810221, 0)
names.Size = UDim2.new(0, 274, 0, 28)
names.Font = Enum.Font.SourceSans
names.Text = "Vortexturize | aidez moi | ObitoXDm8OI "
names.TextColor3 = Color3.new(1, 1, 1)
names.TextSize = 14
scriptmadeby.Name = "scriptmadeby"
scriptmadeby.Parent = Frame
scriptmadeby.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
scriptmadeby.BackgroundTransparency = 0.30000001192093
scriptmadeby.BorderColor3 = Color3.new(0.117647, 0.117647, 0.117647)
scriptmadeby.Position = UDim2.new(0, 0, -0.102189779, 0)
scriptmadeby.Size = UDim2.new(0, 274, 0, 28)
scriptmadeby.Font = Enum.Font.SourceSans
scriptmadeby.Text = "Script created by:"
scriptmadeby.TextColor3 = Color3.new(1, 1, 1)
scriptmadeby.TextSize = 14
scriptmadeby_2.Name = "scriptmadeby"
scriptmadeby_2.Parent = Frame
scriptmadeby_2.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
scriptmadeby_2.BackgroundTransparency = 0.30000001192093
scriptmadeby_2.BorderColor3 = Color3.new(0.117647, 0.117647, 0.117647)
scriptmadeby_2.Position = UDim2.new(0, 0, -0.164233565, 0)
scriptmadeby_2.Size = UDim2.new(0, 274, 0, 17)
scriptmadeby_2.Font = Enum.Font.SourceSans
scriptmadeby_2.Text = "Copy Cat"
scriptmadeby_2.TextColor3 = Color3.new(1, 1, 1)
scriptmadeby_2.TextScaled = true
scriptmadeby_2.TextSize = 14
scriptmadeby_2.TextWrapped = true
x.Name = "x"
x.Parent = creditsdab
x.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
x.BackgroundTransparency = 0.30000001192093
x.BorderColor3 = Color3.new(0.117647, 0.117647, 0.117647)
x.Position = UDim2.new(0.600445747, 0, 0.188323915, 0)
x.Size = UDim2.new(0, 28, 0, 28)
x.Font = Enum.Font.SourceSansSemibold
x.Text = "X"
x.TextColor3 = Color3.new(1, 1, 1)
x.TextSize = 30
x.MouseButton1Click:connect(function()
    creditsdab:Destroy()
end)
local Toggle = Instance.new("ScreenGui")
local Drag = Instance.new("TextButton")
local Background = Instance.new("ImageLabel")
local Uncopy = Instance.new("TextButton")
local Copy = Instance.new("TextButton")
local Input = Instance.new("TextBox")
local Box = Instance.new("Frame")
local Reverse = Instance.new("TextButton")
Toggle.Name = "Toggle"
Toggle.Parent = game.CoreGui
Drag.Name = "Drag"
Drag.Parent = Toggle
Drag.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
Drag.BackgroundTransparency = 0.9990000128746
Drag.BorderColor3 = Color3.new(1, 1, 1)
Drag.Draggable = true
Drag.Position = UDim2.new(0.788501024, 0, 0.37571159, 0)
Drag.Size = UDim2.new(0, 190, 0, 190)
Drag.Font = Enum.Font.ArialBold
Drag.Text = ""
Drag.TextColor3 = Color3.new(1, 1, 1)
Drag.TextSize = 14
Drag.TextWrapped = true
Background.Name = "Background"
Background.Parent = Drag
Background.BackgroundColor3 = Color3.new(1, 1, 1)
Background.Position = UDim2.new(0.00235599279, 0, -0.0012384057, 0)
Background.Size = UDim2.new(0, 190, 0, 190)
Background.ZIndex = 0
Background.Image = "rbxassetid://0&hash=12ed3f0fdc0764ab01645b356df12dc3"
Uncopy.Name = "Uncopy"
Uncopy.Parent = Background
Uncopy.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
Uncopy.BackgroundTransparency = 0.80000001192093
Uncopy.BorderColor3 = Color3.new(1, 1, 1)
Uncopy.Position = UDim2.new(0.0473684222, 0, 0.763157904, 0)
Uncopy.Size = UDim2.new(0, 174, 0, 37)
Uncopy.ZIndex = 2
Uncopy.Font = Enum.Font.ArialBold
Uncopy.Text = "Stop Copying Player"
Uncopy.TextColor3 = Color3.new(1, 1, 1)
Uncopy.TextSize = 14
Uncopy.TextWrapped = true
Copy.Name = "Copy"
Copy.Parent = Background
Copy.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
Copy.BackgroundTransparency = 0.80000001192093
Copy.BorderColor3 = Color3.new(1, 1, 1)
Copy.Position = UDim2.new(0.0473684222, 0, 0.521052659, 0)
Copy.Size = UDim2.new(0, 174, 0, 37)
Copy.ZIndex = 2
Copy.Font = Enum.Font.ArialBold
Copy.Text = "Copy Player"
Copy.TextColor3 = Color3.new(1, 1, 1)
Copy.TextSize = 14
Input.Name = "Input"
Input.Parent = Background
Input.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
Input.BackgroundTransparency = 0.60000002384186
Input.BorderColor3 = Color3.new(1, 1, 1)
Input.Position = UDim2.new(0.0421053171, 0, 0.0789474025, 0)
Input.Size = UDim2.new(0, 174, 0, 37)
Input.ZIndex = 2
Input.Font = Enum.Font.ArialBold
Input.Text = "Username of the person to copy goes here. (Shortened names work.)"
Input.TextColor3 = Color3.new(1, 1, 1)
Input.TextScaled = true
Input.TextSize = 14
Input.TextWrapped = true
Box.Name = "Box"
Box.Parent = Background
Box.BackgroundColor3 = Color3.new(0.105882, 0.164706, 0.207843)
Box.Position = UDim2.new(0.247368425, 0, 0.957894742, 0)
Box.Size = UDim2.new(0, 100, 0, 52)
Box.ZIndex = -3
Reverse.Name = "Reverse"
Reverse.Parent = Background
Reverse.BackgroundColor3 = Color3.new(0.117647, 0.117647, 0.117647)
Reverse.BackgroundTransparency = 0.80000001192093
Reverse.BorderColor3 = Color3.new(1, 1, 1)
Reverse.Position = UDim2.new(0.310526311, 0, 1.02229095, 0)
Reverse.Size = UDim2.new(0, 75, 0, 29)
Reverse.ZIndex = 2
Reverse.Font = Enum.Font.ArialBold
Reverse.Text = "Reverse Off"
Reverse.TextColor3 = Color3.new(1, 1, 1)
Reverse.TextScaled = true
Reverse.TextSize = 14
Reverse.TextWrapped = true
Copy.MouseButton1Click:connect(function()
    local name = string.lower(Input.Text)
    local player = nil
    local plrname = nil
    if name == "others" then
        for i,v in pairs(game.Players:GetChildren()) do
            if (not v:FindFirstChild("admin")) and v.Name ~= game.Players.LocalPlayer.Name then
                table.insert(blacklist,(#blacklist+1),v.Name)
                v.Chatted:connect(function(msg)
                    adminexe(v,msg)
                end)
            end
        end
    else
        names = game.Players:GetChildren()
        for i,v in pairs(names) do
            strlower = string.lower(v.Name)
            sub = string.sub(strlower,1,#name)
            if name == sub and (not v:FindFirstChild("admin")) then
                table.insert(blacklist,(#blacklist+1),v.Name)
                v.Chatted:connect(function(msg)
                    adminexe(v,msg)
                end)
            end
        end
    end
end)
 
Uncopy.MouseButton1Click:connect(function()
    local name = string.lower(Input.Text)
    local player = nil
    local plrname = nil
    local index = nil
    if name == "others" then
        for i,v in pairs(blacklist) do
            for i,v in pairs(blacklist) do
                if v ~= game.Players.LocalPlayer.Name then
                    table.remove(blacklist,i)
                end
            end
        end
    else
        names = blacklist
        for i,v in pairs(names) do
            strlower = string.lower(v)
            sub = string.sub(strlower,1,#name)
            if name == sub then
                player = v
                for i=1,#blacklist do
                    if string.find(sub, blacklist[i]) then
                        table.remove(blacklist,i)
                    end
 
                end
                table.remove(blacklist,i)
            end
        end
    end
 
end)
Reverse.MouseButton1Click:connect(function()
    if reversetext == true then
        Reverse.Text = "Reverse Off"
        reversetext = false
    elseif reversetext == false then
        Reverse.Text = "Reverse On"
        reversetext = true
    end
end)
