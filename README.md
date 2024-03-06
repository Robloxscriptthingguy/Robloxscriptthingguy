-- Get all the players in the game
local players = game:GetService("Players"):GetPlayers()

-- Define the color you want to highlight the players with
local highlightColor = Color3.fromRGB(255, 255, 0)  -- Yellow color

-- Loop through each player and highlight their character
for _, player in ipairs(players) do
    local character = player.Character
    if character and character:FindFirstChild("Humanoid") then
        local torso = character:FindFirstChild("HumanoidRootPart")
        if torso then
            local highlight = torso:Clone()
            highlight.Transparency = 0
            highlight.BrickColor = BrickColor.new(highlightColor)
            highlight.Parent = torso
        end
    end
end
