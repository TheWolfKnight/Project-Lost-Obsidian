Tag: #Coding
Status: Constant updating

# Godot notes
## Spawning an instance

1. Create an node and save it as a template
2. Write a spawn script
3. Include the linse:

~~~GDScript
export (PackedScene) var scene

func _setup():
	var nodeInstanse = scene.instance()
	nodeInstanse.position = Vector2(x, y)
	childNode(nodeInstanse)
~~~

- [PackedScene](GDScript%20Types.md) Is the type for the .tmlp file type

## Structures

GDScript does not support structures, therefor the same result must be emulated via classes like so:

~~~GDScript

class <CLASS_NAME>:
	...
	var <PROPERTY_NAME>: <Type>
	...


def _setup():
	var <var_name> = <CLASS_NAME>.new()
	<var_name>.<PROPERTY_NAME> = {VALUE}

~~~

For more info on types, see the page [[GDScript Types]].

## Export

The export keyword either requires a prefined value, or a type anotation.

~~~GDScript
export (<Type>) var <VAR_NAME>
export var <VAR_NAME> = {VALUE}
~~~

The export keyword will allow you  to change the value of a variable in the inspection colum, in the editor.

For help with types, see [[GDScript Types]].
