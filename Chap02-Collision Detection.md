# Collision Detection

Ever wondered how a car flips in GTA once you dash into another car?? 🤔🤔 That's where Colliders come in action.
Using colliders we are able to perform collision detection.

  <br>

![collision](https://media.giphy.com/media/xTiTnzwJoXpg7gdONy/giphy.gif)

Collision detection helps in the application of physics to the objects in Unity so that they behave like real-world objects inside the game, for example, when the player touches a wall or platform they should get stuck and the player shouldn’t be able to pass through it (a typical game where the user controls a player but of course, if your game requires objects to pass through each other, this can be implemented as well). In a 2D game, any GameObject can have a collider component attached to it like a Box Collider 2D that helps in detecting collisions among objects that would have their boundaries in a rectangular shape.

![boxCollider2d](https://user-images.githubusercontent.com/44625252/152811074-2b0fd11f-770c-44e9-8766-ab0f9415e254.PNG)

As shown above, this collider component when added to both objects will start colliding when touching each other. 

The Collider 2D types that can be used with **Rigidbody** 2D are:

- [Circle Collider 2D](https://docs.unity3d.com/Manual/class-CircleCollider2D.html) for circular collision areas.
- [Box Collider 2D](https://docs.unity3d.com/Manual/class-BoxCollider2D.html) for square and rectangle collision areas.
- [Polygon Collider 2D](https://docs.unity3d.com/Manual/class-PolygonCollider2D.html) for freeform collision areas.
- [Edge Collider 2D](https://docs.unity3d.com/Manual/class-EdgeCollider2D.html) for freeform collision areas and areas which aren’t completely enclosed (such as rounded convex corners).
- [Capsule Collider 2D](https://docs.unity3d.com/Manual/class-CapsuleCollider2D.html) for circular or lozenge-shaped collision areas.
- [Composite Collider 2D](https://docs.unity3d.com/Manual/class-CompositeCollider2D.html) for merging **Box Collider** 2Ds and Polygon Collider 2Ds.

Coming to the second part of the Collider detection when you need the objects to pass through each other but maybe perform an action when their colliders come in touch, The Collider component provides the ‘Is Trigger’ box, which if ticked the objects will pass through each but certain functions or tasks may be performed. For example, in-game we might want the Player Object to pass through a door and go to the Next Level.

While Scripting, MonoBehaviour functions can be used - OnCollisionEnter2D/Stay2D/Exit2D() and similarly OnTriggerEnter2D/Stay2D/Exit2D() based on if it is a collider or simply a trigger.

**Collision with enemies** - For fair gameplay, if your game consists of enemies, in the case of this 2D platformer, you would want gameplay where your enemies will cause damage to the Player on either colliding(eg, super Mario dies when touches the tortoise), or with any type of action performed (eg, bullets firing from an enemy).
After the different types of enemies have been created, you will need to apply collision detection between Enemies and the Player GameObjects to start a function OnCollisionEnter2D, for example, that deals with either decreasing the life of the Player or death, depending on your game requirements. For this game as a start, since the levels are of small sizes, you can implement three lives, on touching the enemy once, you can implement a function that reduces the number of hearts by 1, and then once all 3 lives are lost, you can implement another function that will cause the death for the Player. Following UI is an example of the lives (hearts) implementation in-game:

![lives_all](https://user-images.githubusercontent.com/44625252/152811468-b49c1d60-3189-4449-a6ba-7bc7a31ce3d4.PNG)

**Collision with walls** - The Colliders setup on the walls will help in stopping the player from falling down from the platform. A layer can be applied to denote all the platforms, for example, a layer called Platforms, and then this layer can be setup to be static (for the platforms that won’t be moving) and collision detection can be ticked in the matrix for Player and walls, the layers here being ‘Player’ and ‘Wall’ respectively.

**Collision with Items and Collectibles** – If a game has got some items or collectibles that can be picked up by the player, then that can provide more challenges for the Player and can help increase the level of satisfaction in playing the game. Any item placed in-game can be made to perform some function based on the requirement. For, eg, the below shows keys as items to be picked up by the Player:

![Items_Keys](https://user-images.githubusercontent.com/44625252/152811639-4b75891b-bae1-4ad2-a10e-f3614ea65f84.PNG)

For such items, similar functionality can be applied to detect collision between the Player and the Items, when detected any function can be triggered that performs some action, for example, in the above case, the key was made to disappear (by using Destroy(gameObject)) and the score was increased each time the player picks up one. In this case, you can also use a Trigger instead of a collision, since the Player doesn’t actually need to collide with the Item, rather some action should happen as soon as the Player enters the Trigger area of the Item’s Collider.

**Trigger/Collision for Level End Condition** – At the end of a level, a level-win condition is required to be provided. This condition would be responsible for either completing the game or starting the next level. For example, in Super Mario, we see 8 Areas/levels that Mario needs to be complete in order to finish the game. Hence, this would also need to be setup as a Trigger or Collider as required. When the player enters the trigger area, a function can be triggered that does the work of starting a new level and notifies the user that the current level/area/scene has been completed. For example, something like the Portal asset shown below can be used to trigger the level condition. It might be required that the player is shown as a layer on top of the portal or door, in which case a Trigger instead of a collision would be preferable.

![Door_end](https://user-images.githubusercontent.com/44625252/152811737-f697ef06-43dd-4c91-bbf6-666eec7d75b8.PNG)
