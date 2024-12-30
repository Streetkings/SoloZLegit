local allowedIPs = {
    "69.243.129.235",
    "another_ip_here"
}

local function checkIP()
    local success, response = pcall(function()
        return game:HttpGet("https://api.ipify.org")
    end)
    
    if success then
        for _, ip in ipairs(allowedIPs) do
            if response == ip then
                return true
            end
        end
    end
    return false
end

-- Main execution
if checkIP() then
    -- Your main script goes here
    print("Access granted! Running script...")
else
    -- Better way to handle unauthorized access
    local GUI = Instance.new("ScreenGui")
    local Frame = Instance.new("Frame")
    local Text = Instance.new("TextLabel")
    
    GUI.Parent = game.CoreGui
    
    Frame.Size = UDim2.new(0, 200, 0, 100)
    Frame.Position = UDim2.new(0.5, -100, 0.5, -50)
    Frame.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
    Frame.Parent = GUI
    
    Text.Size = UDim2.new(1, 0, 1, 0)
    Text.Text = "IP Not Whitelisted!"
    Text.Parent = Frame
    
    wait(3)
    GUI:Destroy()
end

-- Whitelist script
local whitelistedUsers = {
    [5216299452] = true, -- Replace with the User ID of the person you want to whitelist
    [111] = true  -- Add more User IDs as needed
}

-- Get the player's User ID (in most exploit environments, `game.Players.LocalPlayer` is used)
local userId = game.Players.LocalPlayer.UserId

-- Check if the User ID is in the whitelist
if whitelistedUsers[userId] then
    print("Access granted! You're whitelisted.")
    -- Place your main script code here
else
    print("Access denied! You're not whitelisted.")
    -- You can add additional actions, like terminating the script
    return
end

local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")

-- Set up the ScreenGui
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

-- Create and style the black square frame
Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(0, 0, 0) -- Black color
Frame.Position = UDim2.new(0.5, -100, 0.5, -100) -- Center position
Frame.Size = UDim2.new(0, 200, 0, 200) -- 200x200 pixels

-- Make it draggable (optional)
Frame.Active = true
Frame.Draggable = true
