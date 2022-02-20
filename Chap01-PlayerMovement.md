# Player Movement

Player Movement can be achieved in different ways in unity, depending on the specific requirement, few are:

* Changing Transform.position of the player every frame based on input direction, this process is usually best when no Rigidbody is there and the object simply needs to shift every frame, for eg, in the case of a top-down camera game like Snake
* Force - Applies a gradual force on the Object, taking mass into account. This is a literal pushing motion where the bigger the mass of the object, the slower it will speed up
* Impulse - Applies an instant force on the Object, taking mass into account. This pushes the Object using the entire force in a single frame. Again, the bigger the mass of the object, the less effect this will have. Great for recoil or jump functions
* Acceleration - Same as ForceMode.Force except that it doesn't take mass into account. No matter how big the mass of the object, it will accelerate at a constant rate
* VelocityChange - Same as ForceMode.Impulse and again doesn't take mass into account. It will literally add the force to the Object's velocity in a single frame

Understanding these different types of forces can be important to shaping the structure of the game as movement is probably the basic feature of any game. For example, the following code shows how a jump action that propels the object upward based on ‘space’ key input from the keyboard can be made to work by applying a velocity change to the Rigidbody component attached to the Player GameObject.

![Velocity\_Jump](https://user-images.githubusercontent.com/44625252/152804627-d0824397-b20b-470c-acb0-53c6a54ac500.PNG)

For this game, since this is a 2D platformer, you can use Transform.position changes along with the Axes (Horizontal, Vertical) to create the movement of the Player every frame, and Rigidbody velocity changes for the jump.

Want more? Head on to the next chapter. ..

![](https://media.giphy.com/media/1gUWdf8Z8HCxpM8cUR/giphy.gif)
