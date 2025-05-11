-- Invisible Fling GUI
-- Compatible with JJsploit
-- Based on Fe Invisible Fling By Diemiers#4209

-- GUI Creation
local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local Title = Instance.new("TextLabel")
local StatusText = Instance.new("TextLabel")
local InvisibleFlingButton = Instance.new("TextButton")
local RespawnButton = Instance.new("TextButton")
local CloseButton = Instance.new("TextButton")
local InfoFrame = Instance.new("Frame")
local InfoText = Instance.new("TextLabel")

-- Properties
ScreenGui.Parent = game.CoreGui
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
ScreenGui.DisplayOrder = 999

MainFrame.Name = "MainFrame"
MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
MainFrame.BorderSizePixel = 0
MainFrame.Position = UDim2.new(0.5, -150, 0.5, -125)
MainFrame.Size = UDim2.new(0, 300, 0, 250)
MainFrame.Active = true
MainFrame.Draggable = true

Title.Name = "Title"
Title.Parent = MainFrame
Title.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
Title.BorderSizePixel = 0
Title.Size = UDim2.new(1, 0, 0, 30)
Title.Font = Enum.Font.SourceSansBold
Title.Text = "Invisible Fling GUI - By KILASIK"
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.TextSize = 18.000

StatusText.Name = "StatusText"
StatusText.Parent = MainFrame
StatusText.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
StatusText.BorderSizePixel = 0
StatusText.Position = UDim2.new(0, 10, 0, 40)
StatusText.Size = UDim2.new(1, -20, 0, 30)
StatusText.Font = Enum.Font.SourceSans
StatusText.Text = "Status: Ready"
StatusText.TextColor3 = Color3.fromRGB(255, 255, 255)
StatusText.TextSize = 16.000
StatusText.TextXAlignment = Enum.TextXAlignment.Left

InvisibleFlingButton.Name = "InvisibleFlingButton"
InvisibleFlingButton.Parent = MainFrame
InvisibleFlingButton.BackgroundColor3 = Color3.fromRGB(60, 120, 60)
InvisibleFlingButton.BorderSizePixel = 0
InvisibleFlingButton.Position = UDim2.new(0.5, -125, 0, 80)
InvisibleFlingButton.Size = UDim2.new(0, 250, 0, 40)
InvisibleFlingButton.Font = Enum.Font.SourceSansBold
InvisibleFlingButton.Text = "Activate Invisible Fling"
InvisibleFlingButton.TextColor3 = Color3.fromRGB(255, 255, 255)
InvisibleFlingButton.TextSize = 16.000

RespawnButton.Name = "RespawnButton"
RespawnButton.Parent = MainFrame
RespawnButton.BackgroundColor3 = Color3.fromRGB(60, 60, 120)
RespawnButton.BorderSizePixel = 0
RespawnButton.Position = UDim2.new(0.5, -125, 0, 130)
RespawnButton.Size = UDim2.new(0, 250, 0, 40)
RespawnButton.Font = Enum.Font.SourceSansBold
RespawnButton.Text = "Respawn"
RespawnButton.TextColor3 = Color3.fromRGB(255, 255, 255)
RespawnButton.TextSize = 16.000

CloseButton.Name = "CloseButton"
CloseButton.Parent = MainFrame
CloseButton.BackgroundColor3 = Color3.fromRGB(180, 60, 60)
CloseButton.BorderSizePixel = 0
CloseButton.Position = UDim2.new(1, -25, 0, 5)
CloseButton.Size = UDim2.new(0, 20, 0, 20)
CloseButton.Font = Enum.Font.SourceSansBold
CloseButton.Text = "X"
CloseButton.TextColor3 = Color3.fromRGB(255, 255, 255)
CloseButton.TextSize = 16.000

InfoFrame.Name = "InfoFrame"
InfoFrame.Parent = MainFrame
InfoFrame.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
InfoFrame.BorderSizePixel = 0
InfoFrame.Position = UDim2.new(0, 10, 0, 180)
InfoFrame.Size = UDim2.new(1, -20, 0, 60)

InfoText.Name = "InfoText"
InfoText.Parent = InfoFrame
InfoText.BackgroundTransparency = 1
InfoText.Position = UDim2.new(0, 5, 0, 5)
InfoText.Size = UDim2.new(1, -10, 1, -10)
InfoText.Font = Enum.Font.SourceSans
InfoText.Text = "Controls:\nWASD - Movement when flying\nZ - Activate invisible fling\nX - Respawn"
InfoText.TextColor3 = Color3.fromRGB(255, 255, 255)
InfoText.TextSize = 14.000
InfoText.TextXAlignment = Enum.TextXAlignment.Left
InfoText.TextYAlignment = Enum.TextYAlignment.Top

-- Variables
local player = game.Players.LocalPlayer
local mouse = player:GetMouse()
local isInvisibleFlingActive = false
local groot = nil

-- Create Credit Label
local CreditLabel = Instance.new("TextLabel")
CreditLabel.Name = "CreditLabel"
CreditLabel.Parent = MainFrame
CreditLabel.BackgroundTransparency = 1
CreditLabel.Position = UDim2.new(0, 10, 1, -15)
CreditLabel.Size = UDim2.new(1, -20, 0, 20)
CreditLabel.Font = Enum.Font.SourceSansItalic
CreditLabel.Text = "Discord: https://discord.gg/PHxN8nadgk"
CreditLabel.TextColor3 = Color3.fromRGB(180, 180, 180)
CreditLabel.TextSize = 12.000
CreditLabel.TextXAlignment = Enum.TextXAlignment.Center

-- Notification function with position option
local notificationIndex = 0
local function showNotification(text, duration, position)
    duration = duration or 2
    position = position or 0  -- Default top position
    
    notificationIndex = notificationIndex + 1
    local currentIndex = notificationIndex
    
    local message = Instance.new("Message", workspace)
    message.Text = text
    
    -- If there's a position specified, create a different type of notification
    if position > 0 then
        -- Create a screen GUI notification instead
        local notifGui = Instance.new("ScreenGui", game:GetService("CoreGui"))
        notifGui.Name = "Notification_" .. currentIndex
        
        local frame = Instance.new("Frame", notifGui)
        frame.Size = UDim2.new(0, 300, 0, 50)
        frame.Position = UDim2.new(0.5, -150, 0, 50 + (position * 60))
        frame.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
        frame.BorderSizePixel = 0
        
        local text = Instance.new("TextLabel", frame)
        text.Size = UDim2.new(1, -10, 1, -10)
        text.Position = UDim2.new(0, 5, 0, 5)
        text.BackgroundTransparency = 1
        text.Font = Enum.Font.SourceSans
        text.TextSize = 16
        text.TextColor3 = Color3.fromRGB(255, 255, 255)
        text.Text = message.Text
        text.TextWrapped = true
        
        message:Destroy() -- Remove the default message and just use our custom one
        
        spawn(function()
            wait(duration)
            notifGui:Destroy()
        end)
    else
        -- Use the default message
        spawn(function()
            wait(duration)
            message:Destroy()
        end)
    end
end

-- Invisible Fling function
local function activateInvisibleFling()
    if isInvisibleFlingActive then
        showNotification("Invisible Fling is already active!", 2)
        return
    end
    
    StatusText.Text = "Status: Activating invisible fling..."
    isInvisibleFlingActive = true
    InvisibleFlingButton.BackgroundColor3 = Color3.fromRGB(120, 60, 60)
    InvisibleFlingButton.Text = "Deactivate Invisible Fling"
    
    showNotification("Fe Invisible Fling Loading (wait 5 seconds)", 5)
    showNotification("Use WASD to fly and move around", 5, 1)
    
    -- Create temporary character
    local ch = player.Character
    local prt = Instance.new("Model", workspace)
    local z1 = Instance.new("Part", prt)
    z1.Name = "Torso"
    z1.CanCollide = false
    z1.Anchored = true
    local z2 = Instance.new("Part", prt)
    z2.Name = "Head"
    z2.Anchored = true
    z2.CanCollide = false
    local z3 = Instance.new("Humanoid", prt)
    z3.Name = "Humanoid"
    z1.Position = Vector3.new(0, 9999, 0)
    z2.Position = Vector3.new(0, 9991, 0)
    player.Character = prt
    wait(3)
    player.Character = ch
    wait(2)
    
    -- Setup invisible character
    local plr = player
    mouse = plr:GetMouse()
    
    local Hum = Instance.new("Humanoid")
    Hum.Parent = player.Character
    
    local root = player.Character.HumanoidRootPart
    
    for i, v in pairs(plr.Character:GetChildren()) do
        if v ~= root and v.Name ~= "Humanoid" then
            v:Destroy()
        end
    end
    
    workspace.CurrentCamera.CameraSubject = root
    
    local se = Instance.new("SelectionBox", root)
    se.Adornee = root
    
    -- Prevent collisions
    game:GetService('RunService').Stepped:connect(function()
        player.Character.HumanoidRootPart.CanCollide = false
    end)
    game:GetService('RunService').RenderStepped:connect(function()
        player.Character.HumanoidRootPart.CanCollide = false
    end)
    
    -- Add fling force
    local power = 999999 -- fling power
    power = power * 10
    
    wait(0.1)
    local bambam = Instance.new("BodyThrust")
    bambam.Parent = player.Character.HumanoidRootPart
    bambam.Force = Vector3.new(power, 0, power)
    bambam.Location = player.Character.HumanoidRootPart.Position
    
    -- Flying setup
    local plr = player
    local torso = root
    local flying = true
    local deb = true
    local ctrl = {f = 0, b = 0, l = 0, r = 0}
    local lastctrl = {f = 0, b = 0, l = 0, r = 0}
    local maxspeed = 120
    local speed = 15
    
    groot = root
    
    -- Improved fly function with better control
    function Fly()
        local bg = Instance.new("BodyGyro", torso)
        bg.P = 9e4
        bg.maxTorque = Vector3.new(0, 0, 0)
        bg.cframe = torso.CFrame
        
        local bv = Instance.new("BodyVelocity", torso)
        bv.velocity = Vector3.new(0, 0, 0)
        bv.maxForce = Vector3.new(9e9, 9e9, 9e9)
        
        -- Keep references for cleanup
        local bgRef = bg
        local bvRef = bv
        
        -- Main flying loop
        spawn(function()
            repeat 
                wait()
                -- Always update velocity based on current camera direction
                if (ctrl.l + ctrl.r) ~= 0 or (ctrl.f + ctrl.b) ~= 0 then
                    -- Moving - use current direction
                    bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (ctrl.f + ctrl.b)) + 
                                 ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(ctrl.l + ctrl.r, (ctrl.f + ctrl.b) * 0.2, 0).p) - 
                                 game.Workspace.CurrentCamera.CoordinateFrame.p)) * speed
                    lastctrl = {f = ctrl.f, b = ctrl.b, l = ctrl.l, r = ctrl.r}
                else
                    -- Not moving - hover
                    bv.velocity = Vector3.new(0, 0.1, 0)
                end
            until not flying
            
            -- Reset everything when done
            ctrl = {f = 0, b = 0, l = 0, r = 0}
            lastctrl = {f = 0, b = 0, l = 0, r = 0}
            speed = 0
            
            -- Destroy body movers
            if bgRef and bgRef.Parent then bgRef:Destroy() end
            if bvRef and bvRef.Parent then bvRef:Destroy() end
        end)
    end
    
    -- Improved flying controls with better movement system
    local function updateMovement()
        if flying then
            if ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0 then
                speed = speed + 0.5
                if speed > maxspeed then
                    speed = maxspeed
                end
            else
                speed = 0 -- Reset speed when no keys are pressed
            end
        end
    end
    
    -- Connect a continuous loop to update movement
    spawn(function()
        while true do
            wait(0.1)
            updateMovement()
        end
    end)
    
    -- Key down handler
    mouse.KeyDown:connect(function(key)
        if key:lower() == "w" then
            ctrl.f = 1
        elseif key:lower() == "s" then
            ctrl.b = -1
        elseif key:lower() == "a" then
            ctrl.l = -1
        elseif key:lower() == "d" then
            ctrl.r = 1
        end
    end)
    
    -- Key up handler 
    mouse.KeyUp:connect(function(key)
        if key:lower() == "w" then
            ctrl.f = 0
        elseif key:lower() == "s" then
            ctrl.b = 0
        elseif key:lower() == "a" then
            ctrl.l = 0
        elseif key:lower() == "d" then
            ctrl.r = 0
        end
    end)
    
    -- Start flying automatically
    flying = true
    Fly()
    
    StatusText.Text = "Status: Invisible Fling Active"
end

-- Respawn function with complete character reset
local function respawnCharacter()
    if not groot then
        showNotification("You need to activate invisible fling first!", 2)
        return
    end
    
    StatusText.Text = "Status: Respawning..."
    showNotification("Completely respawning your character...", 2)
    
    -- Save position before respawn
    local saved = groot.Position
    
    -- Reset status flags
    isInvisibleFlingActive = false
    InvisibleFlingButton.BackgroundColor3 = Color3.fromRGB(60, 120, 60)
    InvisibleFlingButton.Text = "Activate Invisible Fling"
    
    -- Create a new temporary character to force reset
    local ch = player.Character
    local prt = Instance.new("Model", workspace)
    local z1 = Instance.new("Part", prt)
    z1.Name = "Torso"
    z1.CanCollide = false
    z1.Anchored = true
    local z2 = Instance.new("Part", prt)
    z2.Name = "Head"
    z2.Anchored = true
    z2.CanCollide = false
    local z3 = Instance.new("Humanoid", prt)
    z3.Name = "Humanoid"
    z1.Position = Vector3.new(0, 9999, 0)
    z2.Position = Vector3.new(0, 9991, 0)
    
    -- Force character change to reset
    player.Character = prt
    wait(0.5)
    player.Character = ch
    
    -- Update status immediately
    StatusText.Text = "Status: Ready"
    
    -- Reset character using a more drastic method
    local humanoid = player.Character:FindFirstChildOfClass("Humanoid")
    if humanoid then
        humanoid.Health = 0  -- Kill the character to force a respawn
    end
    
    -- Wait for the character to fully respawn
    spawn(function()
        local newCharacter = nil
        
        repeat
            wait()
            newCharacter = player.Character
        until newCharacter and newCharacter.Parent and newCharacter ~= ch
        
        -- Wait for essential parts to load
        repeat
            wait()
        until newCharacter:FindFirstChild("HumanoidRootPart") and newCharacter:FindFirstChild("Humanoid")
        
        -- Move to the saved position
        wait(0.5)
        if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            player.Character.HumanoidRootPart.CFrame = CFrame.new(saved)
            StatusText.Text = "Status: Ready"
            showNotification("Successfully respawned with a new character!", 2)
        end
    end)
    
    -- Reset the groot reference
    groot = nil
end

-- Button Functions
InvisibleFlingButton.MouseButton1Click:Connect(function()
    if isInvisibleFlingActive then
        showNotification("Deactivation is only possible through respawning.", 3)
    else
        activateInvisibleFling()
    end
end)

RespawnButton.MouseButton1Click:Connect(function()
    respawnCharacter()
end)

CloseButton.MouseButton1Click:Connect(function()
    ScreenGui:Destroy()
end)

-- Key Bindings (Keep original keybinds working)
local originalKeyDown = mouse.KeyDown
mouse.KeyDown:connect(function(key)
    if key:lower() == "z" then
        activateInvisibleFling()
    elseif key:lower() == "x" then
        respawnCharacter()
    end
end)

-- Add death detection
player.CharacterAdded:Connect(function(character)
    if isInvisibleFlingActive then
        isInvisibleFlingActive = false
        InvisibleFlingButton.BackgroundColor3 = Color3.fromRGB(60, 120, 60)
        InvisibleFlingButton.Text = "Activate Invisible Fling"
        StatusText.Text = "Status: Ready (Reset due to death)"
        showNotification("Invisible Fling was reset due to character respawn", 3)
        groot = nil
    end
end)

-- Initial notification
showNotification("Invisible Fling GUI Loaded! Press Z to activate, X to respawn", 3)
StatusText.Text = "Status: Ready"
