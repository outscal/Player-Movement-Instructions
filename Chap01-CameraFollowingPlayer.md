# Camera Following The Player

In every game you might have noticed that the camera keeps on following our player endlessly. You must be thinking that there is a person running behind our player with a camera in hand like him 😛 
  <br>
  
![Camera](https://media.giphy.com/media/6MMDMJUBYrNLU5zfTj/giphy.gif)

That is so not the case here.

In any type of game where the camera is projecting the scene for the user, as the player moves, we need to make a design such that the scene is visible for the required range of view of the user rather than keeping the camera view of the scene static which will make the user who is watching the screen lose their player object in-game as the player keeps moving out of the range of view. As such, as we learnt that the camera is also actually a GameObject, it can be manipulated just as any other GameObject in Unity is treated and can be worked on in a similar manner. Two such ways how the camera can be kept moving along with the player object in-game is:

- Attach the camera GameObject to the Player Object, as we know Unity works using a parent-child hierarchy relationship of Objects, so any child object attached to a parent object keeps moving as well when the parent object moves, for example, as shown in the image below, the Main Camera is attached to the player object for a 2D platformer game

![parent_child_attach](https://user-images.githubusercontent.com/44625252/152809953-9df7e275-87a7-4f89-9efb-d579daf6e936.PNG)

- Create a script Component for the Camera Object that can be made to change its position based on movement changes of the Player GameObject by using a variable in the inspector that takes the Player object as a parameter or by finding the PlayerObject in-game using GameObject.Find.
