### Item Usage ###
Items are entities used for and created by executing tasks. They may be picked up, carried, and dropped in most cases.
More about items in the design document: https://github.com/opensuspect/design-document/blob/main/general_gameplay.md#items

***

### How It Works ###
Every player has two nodes used for detecting and handling items: an `Area2D` named **ItemPickupRange** used to locate items in its child `CollisionShape2D` node named **PickupRangeCollision** and a `Node2D` named **ItemHandler** used to decide whether the player can and must pick up or drop items. **ItemPickupRange** is set up so that it only collides with nodes on physics layer 5 (Bit 4, value 16, interactive), which is where interactive items and areas will be located.

Once a body entering **ItemPickupRange** has been detected to be an item and the player detecting it is the main player on that client, then the item is outlined in yellow. At this point, the player may choose to pick up the item by pressing the action `interact`, which on keyboard the default is set to "E", or by left clicking on the item with the mouse. If there are multiple items within range and the main player presses `interact`, then the item closest to the player will be picked up. To swap items, the main player must have another item in range, and press `interact` or click on the item. Picked up items may be dropped by pressing `interact` when there are no other items in range.

Item pickups and drops are synced over the network in `main.gd`. **ItemHandler** only emits a signal to this script when a player makes a request to pick up or drop an item. Once a player receives an RPC to pick up or drop an item, only then is the item actually picked up/dropped.

***

### New Items ###
Every item scene should inherit from the base `Item` class, located in `res://assets/items/item.gd`. This class inherits from `KinematicBody2D`, so it has a collision layer and a collision mask. The collision layer must remain set at physics layer 5, (Bit 4, value 16, interactive) for players to be able to detect the item. The collision mask is set to physics layer 1 (Bit 0, value 1, terrain) in case we want to have the item collide with objects in the environment for any reason.

The item has an `AnimationPlayer` child node named **ItemAnimator** which is used to handle animations on the item. In the base class there are two animations: "hover" and "idle". When the item is on the ground, it will "hover" in place as if it were floating. When the item is picked up, it will stop hovering and becoming "idle". The item is visualized through the `AnimatedSprite` node named **ItemSprite**. Here you can create a `SpriteFrames` resource and create a single frame animation if the item is static or multiple frame animations if the item is animated. If you want to create an animted item, be sure to first make the `AnimationPlayer` node unique by clicking on the tools icon to the top right of the Inspector, then clicking "Make Sub-Resources Unique".

![Making sub-resources unique](https://i.imgur.com/i4nAwpk.png)

It is recommended to extend the Item class in a new script and play the animation through **ItemAnimator** (Click on **ItemAnimator** in the scene tree, click on "Animation" in the Animation dock, and click "New". Then, click on **ItemSprite**, switch to the "Animation" dock if it doesn't automatically open, and press the key icon next to "Animation" in the Inspector to keyframe **ItemSprite's** animation property). 

![Key-framing an AnimatedSprite's animation property](https://i.imgur.com/qoTjhSA.png)

More on Godot's 2D animation features here: https://docs.godotengine.org/en/stable/tutorials/animation/introduction_2d.html

The **MouseArea** `Area2D` is used to detect when you mouse over an item. The `shape` property of its `CollisionShape2D` named **MouseCollision** should be slightly larger than the size of the item sprite to give some leeway to the mouse click area.

Item specific behavior like what the item will be used for should be implemented in a new script that inherits from the `Item` class. **_Do not modify item.gd itself_**.