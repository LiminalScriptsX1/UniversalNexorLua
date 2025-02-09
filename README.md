local plr = game.Players.LocalPlayer
local char = plr.Character
local hum = char.Humanoid
local root = char.HumanoidRootPart

-- Nexor
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/bloodball/-back-ups-for-libs/main/wizard"))()
local Window = Library:NewWindow("Nexor Hub")

local ctab = Window:NewSection("<<Local Player>>")
ctab:CreateButton("SpeedBoost", function()
    hum.WalkSpeed = 100
end)

ctab:CreateButton("JumpBoost", function()
    hum.JumpPower = 567
end)

ctab:CreateButton("gravity", function()
    game.Workspace.Gravity = 56
end)

ctab:CreateButton("Reset", function()
    game.Workspace.Gravity = 196.2
    hum.WalkSpeed = 16
    hum.JumpPower = 50
end)

ctab:CreateTextbox("Speed", function(text)
    hum.WalkSpeed = tonumber(text) 
end)

ctab:CreateTextbox("Jp", function(text)
 hum.JumpPower = tonumber(text)
  end)

ctab:CreateTextbox("grav", function(text)
 Workspace.Gravity = tonumber(text)
  end)

local htab = Window:NewSection("Metas<<antikick etc>>")
htab:CreateButton("AntiKick__METHOD1(onclient)", function()
    local f
    f = hookmetamethod(game.Players.LocalPlayer, "__namecall", function(...)
        if getnamecallmethod() == "Kick" then
            return
        end
        return f(...)
    end)
end)

htab:CreateButton("antikick_METHOD2(onclient)", function()
    local f
    f = hookmetamethod("game", "__namecall", function(self, ...)
        local args = {...}
        local method = getnamecallmethod()
        if method == "FireServer" and tostring(self) == "Kick" then
            return
        end
        return f(self, ...)
    end)
end)

htab:CreateButton("NoRoot,WalkSpeed AntiCheat_Bypass", function()
    local player = game:GetService('Players').LocalPlayer
    local character = player.Character
    if character and character:FindFirstChild("HumanoidRootPart") then
        character.Parent = nil
        character.HumanoidRootPart:Destroy()
        character.Parent = workspace
    end
end)

htab:CreateButton("AntiKick,OnClient", function()
    local player = game:GetService("Players").LocalPlayer
    local old

    old = hookmetamethod(game, "__namecall", function(self, ...)
        local method = getnamecallmethod()
        if method == "kick" or method == 'kick' then
            return 
        end
        return old(self, ...)
    end)
end)

local stab = Window:NewSection("Scripts")
 stab:CreateButton("Inf yield", function()

loadstring(game:HttpGet("https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source"))()

end)

stab:CreateButton("dex", function()
 loadstring(game:HttpGet("https://raw.githubusercontent.com/infyiff/backup/main/dex.lua"))()
 end)

 stab:CreateButton("Universal Chat Byppass", function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/hellohellohell012321/KAWAII-BYPASS/main/kawaii-bypass",true))()
end)

 stab:CreateButton("Jerk", function()
  loadstring(game:HttpGet("https://pastefy.app/wa3v2Vgm/raw"))("Spider Script")
end)



