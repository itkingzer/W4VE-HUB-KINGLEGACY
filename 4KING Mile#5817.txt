if game:GetService("CoreGui"):FindFirstChild("ui") then
    game:GetService("CoreGui"):FindFirstChild("ui"):Destroy()
end

local lib = loadstring(game:HttpGet"https://raw.githubusercontent.com/dawid-scripts/UI-Libs/main/Vape.txt")()

local win = lib:Window("4KING 🛠 By Mile#5817",Color3.fromRGB(44, 120, 224), Enum.KeyCode.RightControl)

local tab = win:Tab("🛠 4KING Superpower  ")

local tab2 = win:Tab("🏫 Tp Shcool")

local tab3 = win:Tab("👦 Tp Players")
----bypass---

game:GetService("Players").LocalPlayer.PlayerScripts["Anti-Cheats (Speed Hacks - Jump Hacks)"].Disabled = true

game:GetService("Players").LocalPlayer.PlayerScripts.AntiAutoClicker.Executors.Main.Disabled = true
game.Players.LocalPlayer.Character["Anti-Fly"].Disabled = true

tab:Toggle("🏃️ วัยรุ่นวิ่ง",false,function(a)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = a
    speed = a
end)

tab:Slider("👟 เลือกความเร็ว", 0, 500,1,function(t)
    sspeed = t
end)

spawn(function()
    while wait() do
        if speed then
            game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = sspeed
        end
    end
end)

tab:Toggle("♿ ตกที่สูงไม่เจ็บ",false,function(a)
    game.Players.LocalPlayer.Character["Fall Damage"].Disabled = a
    Fall = a
end)

tab2:Button("🔪 ซื้อปากฉลาม", function()
    game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2819.94385, -28.400053, 392.892334, 0, 0, -1, 0, 1, 0, 1, 0, 0)
end)


tab2:Button("🏫 เทคโนโลยี", function()
    game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-3426.67896, -26.9244213, 363.864166, 0.785497785, 0.20883657, -0.582563758, -0.00947014242, 0.945288956, 0.326096803, 0.618791997, -0.250631362, 0.744500041)
end)

tab2:Button("🏫 กนก", function()
    game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2282.13794, -27.338089, 512.891907, 0.980432749, -3.31636265e-08, -0.196854249, 4.42197283e-08, 1, 5.17684633e-08, 0.196854249, -5.94603407e-08, 0.980432749)
end)

tab2:Button("🏫 อินทร", function()
    game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-3612.03882, -25.6397705, 1734.64136, -0.668182135, -1.13342082e-08, 0.743997753, 1.8098353e-08, 1, 3.14882733e-08, -0.743997753, 3.45050353e-08, -0.668182135)
end)

tab2:Button("🏫 บุรณพนธ์", function()
    game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-3158.18823, -27.6397591, -253.21817, -0.935020566, -3.93504358e-08, 0.354593515, -2.84347781e-08, 1, 3.59942618e-08, -0.354593515, 2.35725874e-08, -0.935020566)
end)

----------tpplayer------------

tab3:Toggle("👁 ดูคนอื่น",false,function(bool)
	Sp = bool
	local plr1 = game.Players.LocalPlayer.Character.Humanoid
	local plr2 = game.Players:FindFirstChild(SelectedKillPlayer)
	repeat wait(.1)
		game.Workspace.Camera.CameraSubject = plr2.Character.Humanoid
	until Sp == false 
	game.Workspace.Camera.CameraSubject = game.Players.LocalPlayer.Character.Humanoid
end)



PlayerName = {}
for i,v in pairs(game.Players:GetChildren()) do  
	table.insert(PlayerName ,v.Name)
end

SelectedKillPlayer = ""
local Player = tab3:Dropdown("👆 เลือกผู้เล่น",PlayerName,function(plys) --true/false, replaces the current title "Dropdown" with the option that t
	SelectedKillPlayer = plys
	SelectedPly:Refresh("Selected Player : "..SelectedKillPlayer)
end)

tab3:Button("👦 วาปหาคนอื่น",function()
	local plr1 = game.Players.LocalPlayer.Character
	local plr2 = game.Players:FindFirstChild(SelectedKillPlayer)
	plr1.HumanoidRootPart.CFrame = plr2.Character.HumanoidRootPart.CFrame
end)

tab3:Button("🔄 Refrsh",function()
	PlayerName = {}
	Player:Clear()
	for i,v in pairs(game.Players:GetChildren()) do  
		Player:Add(v.Name)
	end
end)



tab:Label("Mile#5817")

local changeclr = win:Tab("💠 Misc")

changeclr:Colorpicker("Change UI Color",Color3.fromRGB(44, 120, 224), function(t)
lib:ChangePresetColor(Color3.fromRGB(t.R * 255, t.G * 255, t.B * 255))
end)