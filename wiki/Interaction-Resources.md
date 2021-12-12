The interaction resources are added by plugin named "OpenSuspect Interaction." The files for said plugin can be found in ```src/addons/opensusinteraction```.

## Quick Start Guide
1. Attach a script to any NODE of your choice
2. Add an exported variable to contain the resource
```gdscript
export(Resource) var interact_resource
# or
export var interact_resource: Resource
```
3. In the editor inspector, set that variable to an Interact resource type. This can be done by dragging or loading the base version of the resource from ```src/addons/opensusinteraction/resources/interact/interact.tres``` or by finding the Interact type in the dropdown. You can also put a different interaction resource type here, like InteractUI or InteractMap.
4. Customize the Interact resource in the editor. Make sure to set interact type to match the interaction you want. If you want to create a task, set it to task, if you want to open a UI, set it to UI, or if you want to interact with a map node, set it to map.
5. Customize the sub-resource that corresponds the the type of interaction you want. In depth info about each type of interact resource can be found lower on this page.
6. Set up the rest of your script:
```gdscript
# where the interact resource is stored
export(Resource) var interact_resource

func _ready():
    # it is good practice to call init_resource() on the resource inside _ready()
    # we are passing self to give the resource access to the scene tree, without access map interactions would be impossible
    # this is NECESSARY for task resources if you want the task to be registered when the game starts.
    interact_resource.init_resource(self)
    # if you want to see what data the interact resource is using, you can call get_interact_data() on it
    # it is optional to pass self if you have already called and passed self in init_resource()
    print(interact_resource.get_interact_data(self))

# data to pass to the interact resource
# it is completely optional to pass custom data
var custom_data = {"your custom": "data here"}

# when you want to execute the interaction, call interact() on the resource
# we are passing self to give the resource access to the scene tree
# it is optional to pass self here ONLY IF you have called init_resource(self) already
# it is completely optional to pass custom data
func interact():
    interact_resource.interact(self, custom_data)
```

## Resource Types

### Interact
This is a wrapper for other interact resources. It is useful for creating an object that will be used for multiple things (like a button). It is currently used for standbutton (```src/assets/maps/common/interactables/standbutton/```) and interactpoint (```src/assets/maps/common/interactables/interactpoint/```)

**Interact Type (interact_type):** Set this to the type of interaction you want. Task is for declaring and registering a task, map is for interacting with a map node, and UI is for opening or showing a UI element.

**Task Resource (task_res):** Stores the task interaction resource. Customize this value to customize task interaction.

**Ui Resource (ui_res):** Stores the ui interaction resource. Customize this value to customize ui interaction.

**Map Resource (map_res):** Stores the map interaction resource. Customize this value to customize map interaction.

### InteractTask
Currently a WIP and is not fully implemented. Documentation will be updated when it is functional.

### InteractUI
This resource interacts with the UI system.

**Ui Name (ui_name):** The name of the UI element you want to open. A dictionary containing these names is stored in ```ui_list``` inside UIManager (```src/assets/autoload/uimanager.gd```)

**Ui Data (ui_data):** Data to pass to the UI element defined in ui_name. The script of the UI you are opening must be set up properly to receive this data. All this entails is declaring a variable ```ui_data``` and setting it to any dictionary, such as ```{}```. IT CANNOT BE LEFT UNSET, OTHERWISE THE UI SYSTEM WILL NOT UPDATE IT. 

Currently, the UI system will completely overwrite this variable, so anything stored in it WILL be lost.  

**Advanced/Reinstance (reinstance):** Whether or not to free and recreate the UI element if it is already opened.

**Advanced/Only Instance (only_instance):** Enabling this means that the UI system will only create/instance the UI element, and will not make any effort to open it. This is useful for overlays or other UI elements that shouldn't keep the player from moving around. It is also useful if you want to control when UI nodes are being loaded and instanced.

### InteractMap
This resource interacts with the map interaction system.

**Interact With (interact_with):** NodePath to the node you want to interact with.

**Interact Data (interact_data):** Data to pass to the node you are interacting with.