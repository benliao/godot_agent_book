The `Item` class represents an in-game object, featuring properties such as `name`, `description`, `type`, and `value`. It also defines a `max_stack` attribute, specifying the maximum number of items that can be put together in a single inventory slot. The class includes methods for using and dropping items, allowing for interaction within the game world. The `use` method is virtual, enabling GDScript implementations to override it for specific item functionality.

```admonish summary
[toc]
```

## Properties
- `name`: The name of the item.
- `description`: A brief description of the item.
- `type`: The type of the item (e.g., weapon, armor, consumable).
- `value`: The value of the item in the game world.
- `max_stack`: The maximum number of items that can be stacked together in a single inventory slot.
- `icon`: The icon representing the item in the inventory.

## Methods
 - `use`: A method that defines how the item can be used in the game. This could involve applying effects, consuming the item, or equipping it. It's a virtual method, the GDScript implementation should override this method to provide specific functionality for the item.
 - `drop`: A method that defines how the item can be dropped in the game world. This could involve removing the item from the inventory and placing it in the game world.
