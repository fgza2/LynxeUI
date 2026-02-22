# Lynxe library
This documentation is to explain how to setup lynxe and how to use lynxe.

This library is new and may have bugs and missing features or elements

## Booting the library
```lua
local lynxe = loadstring(game:HttpGet("https://raw.githubusercontent.com/GithubJay00/LynxeUI/refs/heads/main/Lynxe.Main"))()
```


## Creating a window
```lua
local Window = lynxe:CreateWindow({
	Name = "Lynxe UI", -- The name of your script / hub
	Icon = "rbxassetid://10709782497", -- logo 

	UItoggleBind = "P", -- The toggle Key-Bind for PC users

	LynxeUIPrompts = true, -- Lynxe UI notifications

	LoadingTitle = "Title", -- Your loading title
	LoadingDescription = "Title Tip", -- Your loading description

	ConfigSaving = { -- Configuration saving
		Enabled = false, -- On / Off
		FolderName = "LynxeConfigs", -- Folder name
		FileName = "lynxehub" -- File name
	},

	Logging = { -- Execution logging
		Enabled = false, -- On / Off
		Url = "Your_Webhook_Here" -- Discord webhook 
	},

	Discord = { 
		Invite = "NoInvite" -- Your server invite
	}
})

local HomeTab = Window:CreateHomeTab() -- This is optional but recommended
```


The elements below can be created from the tab or the section, here is an example: Tab:CreateObject({}), Section:CreateObject({})

## Creating a tab
```lua
local Tab = Window:CreateTab({ Name = "Test Tab", Icon = "rbxassetid://10709782497" })
```


## Creating a section
```lua
local Section = Tab:CreateSection({ Name = "Test Section" })
```


## Notifying the user
```lua
lynxe:Notify({
	Title = "Notification", -- The title of your notification
	Info = "Information", -- The information you want to display
	Duration = 5, -- How long the notification will last
	Image = "rbxassetid://10723374276" -- the icon for your notification
})
```


## Creating a button
```lua
local button = Section:CreateButton({ 
	Name = "Test Button", 
	Callback = function() 
		-- The function that will execute when the button is pressed
	end
})
```


## Creating a toggle
```lua
local toggle = Section:CreateToggle({
	Name = "Test Toggle",
	CurrentValue = false,
	Flag = "Toggle1", -- The flags are for configuration saving; each flag must be different
	Callback = function(Value) 
		-- The function that will execute when the toggle is pressed
		-- Value is a boolean that determines if the toggle is on or off
	end
})
```


### Changing the value of a toggle
```lua
toggle:Set(true)
```


## Creating a slider
```lua
local slider = Section:CreateSlider({
	Name = "Test Slider",
	CurrentValue = 10,
	Range = {min = 0, max = 100},
	Increment = 1,
	Flag = "slider1", -- The flags are for configuration saving; each flag must be different
	Callback = function(Value)
		-- The function that will execute when the slider changes
		-- Value is a number that determines the percentage or value of the slider
	end
})
```


### Changing the value of a slider
```lua
slider:SetValue(10)
```


### Getting a sliders value
```lua
slider:GetValue()
```


## Creating a dropdown
```lua
local dropdown = Section:CreateDropdown({
	Name = "Test Dropdown",
	Options = {"Option 1", "Option 2"},
	CurrentOption = {"Option 1"},
	Flag = "Dropdown1", -- The flags are for configuration saving; each flag must be different
	Callback = function(Option)
		-- The function that executes when the option is changed
		-- Option is the option that is currently selected
	end
})
```


## Creating a keybind
```lua
local keybind = Section:CreateKeyBind({
	Name = "Test Keybind",
	Keybind = "Q",
	Flag = "Keybind1", -- The flags are for configuration saving; each flag must be different
	Callback = function(keybind) 
		-- The function that executes when the keybind is pressed
		-- keybind is the keybind that was pressed
	end
})
```
