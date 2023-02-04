# WindowEntry
A C# wrapper for iterating windows and getting their attributes

# Examples
```C#
var steamProcessId = WindowEntry
	.desktop
	.allChildren
	.Where(x => x.className == "steam" 
		&& x.isVisible == true 
		&& x.isTopLevel == true)
	.First()
	.next
	.processId;

Console.WriteLine($"Steam process id: {steamProcessId}");


var firefoxWindowLocation = WindowEntry
							.desktop
							.findWindow(className: "MozillaWindowClass")
							.windowRect;

Console.WriteLine(firefoxWindowLocation.ToString());
```