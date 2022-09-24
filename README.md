if game.PlaceId == 10714365287 then

    local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
    local Window = OrionLib:MakeWindow({Name = "Taha My Pet", HidePremium = false, IntroEnabled = false,IntroText = "WLC TO Taha Gay Hub", SaveConfig = true, ConfigFolder = "OrionTest"})

--Value
_G.autoTab = true
_G.autoHatch = true
_G.selectEgg = "Star1"
_G.equipbest = true
_G.shor = true
_G.TP = true


--Functions

function autoTab()
    while _G.autoTab == true do
        game:GetService("ReplicatedStorage").Knit.Services.ClickerService.RF.PlayerClick:InvokeServer()
        wait(.0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001)
     end
    end


function autoHatch()
    while _G.autoHatch == true do
local args = {
    [1] = _G.selectEgg,
    [2] = 1,
    [3] = {}
}

    game:GetService("ReplicatedStorage").Knit.Services.StarEggService.RF.OpenEggs:InvokeServer(unpack(args))
    wait(.000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001)
end
end

function equipbest()
    game:GetService("ReplicatedStorage").Knit.Services.PetInventoryService.RF.EquipBest:InvokeServer()
end

function shor()
	if _G.shor == true then
		for i,v in pairs(game:GetDescendants()) do
			if _G.shor == true then
				if v.Name == "Checkpoint" then
					game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
					wait(3)
				end
			end
		end
	end
end

function TP()
	local teleport_table = {
		location1 = Vector3.new(501.118, 3, 780059), -- your desired position
		location2 = Vector3.new(744.975, 3, 12.9116)  -- your desired position
	}
	
	local tween_s = game:GetService('TweenService')
	local tweeninfo = TweenInfo.new(1,Enum.EasingStyle.Linear)
	
	local lp = game.Players.LocalPlayer
	
	function bypass_teleport(v)
		if lp.Character and 
		lp.Character:FindFirstChild('HumanoidRootPart') then
			local cf = CFrame.new(v)
			local a = tween_s:Create(lp.Character.HumanoidRootPart,tweeninfo,{CFrame=cf})
			a:Play()
			-- a.Completed:Wait()
			-- print('Teleporting Done!')
		end
	end
	
	bypass_teleport(teleport_table.location1)
end

--Tabs
local FarmTab = Window:MakeTab({
	Name = "Auto Farm",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

local MiscTab = Window:MakeTab({
	Name = "Misc",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

local CreaditsTab = Window:MakeTab({
	Name = "Credit",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})


--Toggles
FarmTab:AddToggle({
	Name = "Fast Click",
	Default = false,
	Callback = function(Value)
		_G.autoTab = Value
        autoTab()
	end    
})

FarmTab:AddToggle({
	Name = "Farm Shurikens",
	Default = false,
	Callback = function(Value)
		_G.shor = Value
        shor()
	end    
})

MiscTab:AddLabel("Lazm Tkon Jnb Bida To Work")
MiscTab:AddToggle({
	Name = "Auto Open Star",
	Default = false,
	Callback = function(Value)
        _G.autoHatch = Value
        autoHatch()
	end    
})

MiscTab:AddButton({
	Name = "Equip Best",
	Callback = function()
            equipbest()
  	end    
})

FarmTab:AddButton({
	Name = "Tp To The End, Wait 10sc And Enter",
	Callback = function()
            TP()
  	end    
})


--Dropdowns

MiscTab:AddDropdown({
	Name = "Select Star Egg",
	Default = "Star1",
	Options = {"Star1", "Star2", "Star3", "Star4", "Star5", "Star6", "Star7", "Star8", "Star9", "Star10"},
	Callback = function(Value)
		_G.selectEgg = Value
        print(_G.selectEgg)
	end 
})

--Lables

CreaditsTab:AddLabel("By Xoova Sub To Xoova In YT :)")









end
OrionLib:Init()





