# Vape V4 Documentation
This documentation will teach you how to create modules, tooltips, ETC
> [!WARNING]
> This isnt a real documentation by owner, Module creating, and more, they may not work.
## Modules
Modules are those toggles you can interact with, like Speed, Killaura, and more. To create an module simply add this in universal.lua or something.
```lua
local Module = vape.Categories.Combat:CreateModule({
    Name = 'ModuleName',
    Function = function(callback)
        if callback then
            print("Toggled on")
        else
            print("Toggled off")
        end
    end,
    Tooltip = 'Module tooltip'
})
```
The code is pretty self explanatory to edit..
## Module Settings
Module settings can let you change how a module works, for example. A speed module, you can add a toggle or slider to change the speed up or down. To create these, simply do this
```lua
local ModuleToggle = Module:CreateToggle({
    Name = 'Module Toggle Name',
    Default = false,
    Function = function(callback)
        print('Hello')
    end
})
```
Code is also self explanatory. And you can add sliders.
```lua
local ModuleSlider = Module:CreateSlider({
    Name = 'Slider',
    Min = 0,
    Max = 10,
    Default = 5
})
```
I dont know but you probably gotta do this.
```lua
local ModuleSlider = Module:CreateSlider({
    Name = 'Slider',
    Min = 0,
    Max = 10,
    Default = 5
    Function = function(callback)
        print("New callback: " .. callback)
    end
})
```
## Notifications
Vape has built in notifications you can add, heres how you can do it
```lua
notif("Notification Text", "Notifiaction Subtext", 5, "warning")
```
You can do more than just warning, Alert, default (by not adding a type), Thats the end, I really dont know any more.
