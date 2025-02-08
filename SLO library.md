# SLO Library
ملفات المكتبة كامله

## مشغل المكتبة
```lua
local OrionLib = loadstring(game:HttpGet(("https://raw.githubusercontent.com/S2EXE/Gui-/refs/heads/main/S2%20Library.txt")))()

```



## اصنع الواجهة
```lua
local Window = OrionLib:MakeWindow({Name = "عنوان المكتبة", HidePremium = false, SaveConfig = true, ConfigFolder = "ملف"})

--[[
تقدر تحط اسم الملف بك
]]

```



## اصنع النافذ
```lua
local Tab = Window:MakeTab({
	Name = "النافذه الاولة",
	Icon = "rbxassetid://136401635766491",
	PremiumOnly = false
})

```
## اصنع القسم 
```lua
local Section = Tab:AddSection({
	Name = "قسم 1"
})

```


## ارسل اشعار ل المستخدم
```lua
OrionLib:MakeNotification({
	Name = "العنوان",
	Content = "وش راح تقول في الاشعار؟؟؟",
	Image = "rbxassetid://136401635766491",
	Time = 5
})

```



## اصنع زر
```lua
Tab:AddButton({
	Name = "زر 1",
	Callback = function()
      		print("Hi")
  	end    
})

```


## اصنع زر تشغيل والغاء
```lua
Tab:AddToggle({
	Name = "زر الغاء و تشغيل",
	Default = false,
	Callback = function(Value)
		print(Value)
	end    
})

```

### تغيير قيمة Toggle الموجودة
```lua
CoolToggle:Set(true)

```



## لون الواجهة او اشياء ثانيه
```lua
Tab:AddColorpicker({
	Name = "Colorpicker",
	Default = Color3.fromRGB(255, 0, 0),
	Callback = function(Value)
		print(Value)
	end	  
})

```

### حط لون
```lua
ColorPicker:Set(Color3.fromRGB(255,255,255))

```


## اصنع خط تقدر تسحبه وترجعه
```lua
Tab:AddSlider({
	Name = "Slider",
	Min = 0,
	Max = 20,
	Default = 5,
	Color = Color3.fromRGB(255,255,255),
	Increment = 1,
	ValueName = "bananas",
	Callback = function(Value)
		print(Value)
	end    
})

```

### تغير قيمة Slider
```lua
Slider:Set(2)

```
Make sure you make your slider a variable (local CoolSlider = Tab:AddSlider...) for this to work.


## اصنع تسمية
```lua
Tab:AddLabel("Label")

```

### تغير القيمه Label
```lua
CoolLabel:Set("Label New!")

```


## اصنع بروغراف
```lua
Tab:AddParagraph("Paragraph","Paragraph Content")

```

### تحديث البروغراف
```lua
CoolParagraph:Set("Paragraph New!", "New Paragraph Content!")

```


## اصنع مدخلات التكيف
```lua
Tab:AddTextbox({
	Name = "Textbox",
	Default = "default box input",
	TextDisappear = true,
	Callback = function(Value)
		print(Value)
	end	  
})

```


## إنشاء اخفاء الواجهة
```lua
Tab:AddBind({
	Name = "اخفاء",
	Default = Enum.KeyCode.E,
	Hold = false,
	Callback = function()
		print("press")
	end    
})

```

### تغير 
```lua
Bind:Set(Enum.KeyCode.E)

```


## اصنع قائمة منسدلة
```lua
Tab:AddDropdown({
	Name = "Dropdown",
	Default = "1",
	Options = {"1", "2"},
	Callback = function(Value)
		print(Value)
	end    
})

```

### إضافة مجموعة من الأزرار المنسدلة الجديدة إلى القائمة الموجودة
```lua
Dropdown:Refresh(List<table>,true)

```

The above boolean value "true" is whether or not the current buttons will be deleted.
### تحديد خيار القائمة المنسدلة
```lua
Dropdown:Set("dropdown option")

```

# الانتهاء من البرنامج النصي الخاص بك (مطلوب)
يجب إضافة الوظيفة أدناه في نهاية التعليمات البرمجية الخاصة بك.
```lua
OrionLib:Init()

```

### كيفية عمل الأعلام.
قد تكون ميزة الأعلام في واجهة المستخدم مربكة لبعض الأشخاص. إنه يخدم غرض كونه معرف عنصر في ملف التكوين، ويجعل الوصول إلى قيمة العنصر في أي مكان في الكود ممكنًا.
أدناه في مثال لاستخدام الأعلام.
```lua
Tab1:AddToggle({
    Name = "Toggle",
    Default = true,
    Save = true,
    Flag = "toggle"
})

print(OrionLib.Flags["toggle"].Value) -- prints the value of the toggle.

```
يطبع قيمة التبديل.


تعمل الأعلام فقط مع أدوات التبديل، وشريط التمرير، والقائمة المنسدلة، والربط، ومنتقي الألوان.

### جعل واجهتك تعمل مع التكوينات.
لكي تجعل واجهتك تستخدم وظيفة التكوينات، عليك أولاً إضافة `SaveConfig و`ConfigFolder`  
 الحجج لوظيفة نافذتك. شرح هذه الحجج في أعلاه.
بعد ذلك، يتعين عليك إضافة قيمتي "Flag" و"Save" إلى كل تبديل، وشريط تمرير، وقائمة منسدلة، وربط، ومنتقي ألوان تريد تضمينه في ملف التكوين.
الوسيطة `Flag = <string>` هي معرف العنصر في ملف التكوين.
تتضمن الوسيطة `Save = <bool>` العنصر الموجود في ملف التكوين.
يتم إنشاء ملفات التكوين لكل لعبة يتم تشغيل المكتبة فيها.

## تحطيم الواجهة
```lua
OrionLib:Destroy()

```
