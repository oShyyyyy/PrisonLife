local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()

local Window = Library.CreateLib("DevX | Prison Life", "DarkTheme")

local Tab = Window:NewTab("Character")
local GunMod = Window:NewTab("Gun Mods")
local Section = Tab:NewSection("Walkspeed & Jumppower")
local SectionMod = GunMod:NewSection("Gun Mods")
local Other = Window:NewTab("Others")
local OtherSection = Other:NewSection("Other")
local Settings = Window:NewTab("Settings")

Section:NewSlider("WalkSpeed", "Set's users walkspeed", 500, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)

Section:NewSlider("JumpPower", "Set's users jumppower", 500, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.JumpPower = s
end)

local Section = Tab:NewSection("Other")
Section:NewButton("NoClip", "NoClip made by LeviTheOtaku", function()
game:getService("RunService"):BindToRenderStep("",0,function()
if not game.Players.LocalPlayer.Character:findFirstChildOfClass("Humanoid") then return end
if game:getService("UserInputService"):IsKeyDown(Enum.KeyCode.V) then
game.Players.LocalPlayer.Character:findFirstChildOfClass("Humanoid"):ChangeState(11)
end
end)
end)


Section:NewButton("Reset", "Reset Character", function()
    game.Players.LocalPlayer.Character.Humanoid.Health = 0
end)

--//GunMods Section\\--


SectionMod:NewButton("Full Gun Mod", "Give's person full mods on their gun", function()
   for i,v in pairs(game.Players.LocalPlayer.Backpack:GetDescendants()) do
	if v:IsA("ModuleScript") then
		local item = require(v)
		if item.CurrentAmmo then
		item.AutoFire = true
		item.CurrentAmmo = math.huge
		item.MaxAmmo = math.huge
		item.Bullets = 40
		item.FireRate = 0.00001
		item.Range = 10000
		item.Spread = 0
		end
		end
		end
end)

local SectionMod = GunMod:NewSection("Other")
SectionMod:NewButton("Guns | No Gamepass", "Give's all non gamepass guns to player", function()
    Workspace.Remote.ItemHandler:InvokeServer(Workspace.Prison_ITEMS.giver["Remington 870"].ITEMPICKUP)
    Workspace.Remote.ItemHandler:InvokeServer(Workspace.Prison_ITEMS.giver["AK-47"].ITEMPICKUP)
    Workspace.Remote.ItemHandler:InvokeServer(Workspace.Prison_ITEMS.giver.M9.ITEMPICKUP)
end)
SectionMod:NewButton("Guns | With Gamepass", "Give's all gamepass/non gamepass guns to player", function()
    Workspace.Remote.ItemHandler:InvokeServer(Workspace.Prison_ITEMS.giver["Remington 870"].ITEMPICKUP)
    Workspace.Remote.ItemHandler:InvokeServer(Workspace.Prison_ITEMS.giver["Riot Shield"].ITEMPICKUP)
    Workspace.Remote.ItemHandler:InvokeServer(Workspace.Prison_ITEMS.giver["AK-47"].ITEMPICKUP)
    Workspace.Remote.ItemHandler:InvokeServer(Workspace.Prison_ITEMS.giver.M9.ITEMPICKUP)
    Workspace.Remote.ItemHandler:InvokeServer(Workspace.Prison_ITEMS.giver.M4A1.ITEMPICKUP)
end)

--//Other Section\\--
OtherSection:NewButton("Remove All Doors", "Remove's all doors from workspace", function()
	game:GetService("Workspace").Doors:Destroy()
end)

--//Settings Section\\--

local Setting = Settings:NewSection("Settings")
Setting:NewKeybind("Set Keybind", "Set your keybind to open n close gui", Enum.KeyCode.X, function()
	Library:ToggleUI()
end)
