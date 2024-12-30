--[[
WARNING: Heads up! This script has not been verified by ScriptBlox. Use at your own risk!
]]
local currentip = game:HttpGet("api.ipify.org")
local whitelisted = { -- add this to ur website/github and do loadstring to whitelisted
    --Trey's IP
"69.243.129.235",
}

if currentip == unpack(whitelisted) then
print"script load"
else
game.Players.LocalPlayer:Kick("non whitelist")
end

-- Whitelist script
local whitelistedUsers = {
    --Trey's accounts
    [5216299452] = true, -- Replace with the User ID of the person you want to whitelist

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

ocal ScreenGui = Instance.new("ScreenGui")
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
