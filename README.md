## Required Before Proceeding
[My Plugin](https://create.roblox.com/store/asset/81948658764284)

[BMFont Official Site](https://angelcode.com/products/bmfont/)

[The Module (if you dont have it yet)](https://create.roblox.com/store/asset/81394450551935/Blockys-CFM)

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

Rename it to whatever name you want, then parent it inside the folder: [Module.Fonts].
now, view the ConvertedFont module in the script editor, and change the imageId to the png's rbxassetid.
if you didnt do that, here's how to do it:
go to [The Decal uploading page](https://create.roblox.com/dashboard/creations/upload?assetType=Decal) and click the [Upload] button on the top.
then, select your image file in the same folder as the FNT file.
make sure to name it for example: ["My Custom Font Image"].
when uploaded, now head to the bottom of the page and click the second [Upload] button.
now, head to [The Decals tab](https://create.roblox.com/dashboard/creations?assetType=Decal&activeTab=Decal) and find the decal with the same name you've entered.
when found, click the Three dots on the Top right corner of the icon, and click [Copy Asset id].
now, head back to the ConvertedModule and make the [rbxassetid://1234567890] line this: rbxassetid://{your-copied-id-here}
there you go, you've done it!

this is how to use it: (localscript inside startergui)

```luau
local fontName = "FontName" --  change this to your font's name, depending on the name of your font module

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

Finally, it is so fast i made a working font in 1 minute. it's that easy!

here is some places you can find a font on:

[The Google Fonts Store](https://fonts.google.com/)

[Fontmeme.com (has fonts from various movies and games)](https://fontmeme.com/)

[DaFont (has fonts from more games and more fonts then Fontmeme)](https://www.dafont.com/)

[1001Fonts (best place to get fonts from my opinion)](https://www.1001fonts.com/)

If you want to find more fonts, go to [Google.com](https://www.google.com/search?q=font) or [Bing.com](https://www.bing.com/search?q=font) for more font stores.

Thank you for all of the support and usages.
