## Creating Modules

Modules are the main containers for groups of settings. To create a module:

```lua
local MyModule = vape.Categories.SomeCategory:CreateModule({
    Name = "ModuleName",
    Function = function(callback)
        -- Code that runs when module is toggled
        if callback then
            -- When enabled
        else
            -- When disabled
        end
    end,
    Tooltip = "Description of what this module does" -- Optional
})
```

You can also toggle your module

```lua
MyButton:Toggle(false)
```
```lua
MyButton:Toggle(true)
```

## Creating Sliders

Sliders allow numerical value selection within a range:

```lua
local MySlider = MyModule:CreateSlider({
    Name = "SliderName",
    Min = 0,         -- Minimum value
    Max = 100,       -- Maximum value
    Default = 50,    -- Default value
    Function = function(value)
        -- Code that runs when slider value changes
        print("New value:", value)
    end
})
```

## Creating ColorPickers

ColorPickers allow selecting a color with HSV values:

```lua
local MyColor = MyModule:CreateColorPicker({
    Name = "ColorName",
    Default = {      -- Default color in HSV
        Hue = 0.5,
        Sat = 1,
        Value = 1
    },
    Function = function(color)
        -- Code that runs when color changes
        print("New color HSV:", color.Hue, color.Sat, color.Value)
        -- Convert to RGB color if needed:
        local rgbColor = Color3.fromHSV(color.Hue, color.Sat, color.Value)
    end
})
```

## Creating Notifications

Notifications display temporary messages to the user:

```lua
-- Using the notif function seen in your code
notif("Title", "Message content", 5) -- Title, message, duration in seconds

-- Or the full version
vape:CreateNotification("Title", "Message content", 5, "info") -- Title, message, duration, type (info, alert, warning)
```

## Creating Dropdowns

Dropdowns allow selecting from a list of options:

```lua
local MyDropdown = MyModule:CreateDropdown({
    Name = "DropdownName",
    List = {"Option1", "Option2", "Option3"}, -- List of options
    Function = function(selected)
        -- Code that runs when selection changes
        print("Selected:", selected)
    end
})
```

## Creating Labels

Labels display static text:

```lua
local MyLabel = MyModule:CreateLabel({
    Name = "LabelText",
    Function = function()
        -- Optional function that runs when the label is clicked
    end
})
```

## Creating Text Boxes

Text boxes allow text input:

```lua
local MyTextBox = MyModule:CreateTextBox({
    Name = "TextBoxName",
    Default = "Default text",
    Function = function(text)
        -- Code that runs when text changes
        print("New text:", text)
    end
})
```

## Creating Toggles

Toggles are on/off switches:

```lua
local MyToggle = MyModule:CreateToggle({
    Name = "ToggleName",
    Default = false,  -- Default state
    Function = function(enabled)
        -- Code that runs when toggle changes
        if enabled then
            -- When enabled
        else
            -- When disabled
        end
    end
})
```

## Creating Target Selectors

For targeting settings (like you see in the AimAssist module):

```lua
local MyTargets = MyModule:CreateTargets({
    Players = true,  -- Target players by default
    NPCs = false     -- Don't target NPCs by default
})
```
