Tag: #Coding
Status: Not importent

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


## Structures

GDScript does not support structures, therefor the same result must be emulated via classes like so:
~~~GDScript

class <CLASS_NAME>:
	...
	PROPERTIES
	...


def _setup():
	var <var_name> = <CLASS_NAME>.new()

~~~

