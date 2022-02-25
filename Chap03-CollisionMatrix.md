# Collision Matrix

Finally, another condition may arise when we might want collisions for the GameObjects but maybe not collide with specific objects. For example, we might want enemies to pass through each other but the Player should collide with them.

![enemies_passing](https://user-images.githubusercontent.com/44625252/152812436-ba838a58-b13c-40f8-a12f-47d69685d9ed.PNG)

In such cases, a collision matrix can be used to uncheck collisions between specific layers as shown. below. You can find this setting under Project Settings → Physics2D (for a 2D game) or Physics for a 3D game.

![collision_matrix](https://user-images.githubusercontent.com/44625252/152812499-2e923ec3-3cfa-4a6d-95d0-031fefc95f40.PNG)
