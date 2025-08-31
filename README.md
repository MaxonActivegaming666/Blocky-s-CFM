## Required Before Proceeding
[My Plugin](https://create.roblox.com/store/asset/81948658764284)

[BMFont Official Site](https://angelcode.com/products/bmfont/)

## How to use
First, Download BMFont from the link above.

when you open it, head to Options/Font Settings.

there, you can choose your own font.

when you're done head to Options/Export Settings.

then, copy these Settings:

Equalize Cell heights = true
Bit Depth = 32
Font Descriptor = XML
Textures = png - Portable Network Graphics

After you've done That, go to Options/Save Bitmap Font As...
then export it into your desired location.
in that location, there should be 2 files:
YourFontName.fnt
YourFontName_number.png

then, head to [My Plugin](https://create.roblox.com/store/asset/81948658764284) and  click "Get Plugin".

go to studio, open the Toolbox and Click The Four Squares (Inventory)

then choose tab "My Plugins"
and locate the a BMFont Converter plugin.
once you've located it, click on it and click the button (install).
after you've done that head over to the "PLUGINS" tab, and find the BMFont converter.
then, click the "Import BMFont" button
then, a prompt should pop-up.
in the prompt, select the folder you've exported the files into, and locate the FNT file.

double-click it, and check the ServerScriptService folder in your Studio Explorer. You'll find the ConvertedFont module.

Rename it to whatever name you want, then parent it inside the Module.Files.

this is how to use it: (localscript inside startergui)

```luau
local fontName = "FontName" --  change this to your font's name

local FontGui = Instance.new("ScreenGui")
FontGui.Name = "FontGui"
FontGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
FontGui.Parent = game:GetService("StarterGui")
local module = require(game.ReplicatedStorage:WaitForChild("Blocky's CFM", 0.5))

local container = Instance.new("TextBox")
Frame.Name = "Frame"
Frame.Active = false
Frame.BorderSizePixel = 0
Frame.BackgroundColor3 = Color3.new(0.00, 0.00, 0.00)
Frame.Size = UDim2.new(0.64, 0.00, 0.59, 0.00)
Frame.TextTransparency = 1
Frame.BorderColor3 = Color3.new(0.00, 0.00, 0.00)
Frame.Text = "Enter text here"
Frame.Selectable = false
Frame.Position = UDim2.new(0.30, 0.00, 0.13, 0.00)
Frame.Parent = FontGui

module.RenderText("Enter Text Here", container, fontName, true)
container:GetPropertyChangedSignal("Text"):Connect(function()
	for _, image in pairs(container:GetChildren()) do
		if image:IsA("ImageLabel") then
			image:Destroy()
		end
	end

	module.RenderText(container.Text, container, fontName, true)
end)


```
