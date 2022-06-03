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


func _setup():
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

## Get nodes

When trying to get a node, don't seek the "/root/..." node firts, try all you can to get it as a relative reference.

~~~GDScript

var node: Node

func _ready():
	node = get_node("<PAHT_TO_NODE>")


func _process(delta):
	...
	DO SOMETHING
	...

~~~

## Resources

Resources can be used when many nodes need the standert stats, which only need differing values.

1. Make a script, that inherits from "Resources"
2. write:

~~~GDScript

extends Resources
class_name <RESOURCE_NAME>

~~~

3. Then make propertys like you do when you export values:

~~~GDScript

export (<TYPE>) var <VAR_NAME>

~~~

4. (Optional) If you want to be able to get and set the exported variable, do like so:

~~~GDScript

export (<TYPE>) var <VAR_NAME>, setget <SETTER_NAME>, <GETTER_NAME>

func <SETTER_NAME>(value):
	<VAR_NAME> = VALUE

func <GETTER_NAME>() -> <TYPE>:
	return <VAR_NAME>

~~~
