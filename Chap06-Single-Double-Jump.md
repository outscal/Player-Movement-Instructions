# A. Single/Double/Triple Jump


Player Jump is one of the most crucial elements for this project. Before making the double jump or triple jump first, go through the *Player Movement* section to get an idea of how you can use physics in a particular game object to move it. Also, get yourself familiarized with the RigidBody2D, BoxCollider2D components.

Single Jump: If you have tried to write a code for jump mechanics then you must have seen how the game object behaves when pressing the attached input. It goes infinite at a one-time press. How to fix it? *Hint:* Limit it by using a **bool value**. Also, do not forget to read about *Collison Detection* as it is important for this task.
        
Here is a code where you can get an idea of how to do it.
        
![collision](https://user-images.githubusercontent.com/44625252/152814775-ba198674-bb92-4e76-bd7e-02d9896ab640.png)

Also, this is not the end. You need to write a logic for OnCollisionExit2D as well. Do it by yourself. It will boost your confidence.

Double Jump: Can we use a counter for it? 🤔 It’s like if you press the UP Arrow key once, then it will count for 1 time and jump once. If pressed twice then it will count for 2 times and jump twice. hmmmmmm.... ????? But how to implement it?
    
Let’s see a code and understand it.
        
![doblejump](https://user-images.githubusercontent.com/44625252/152814891-30ebacac-d1cf-4679-b2de-20c4fd57e04f.png)
        
Here, the counter is extraJump variable. By default, the game object has the ability to jump by once. So when extraJump is 1 then the game object will jump twice. The extraJump will only be available if the game object stands on the ground platform. The value of extraJump is decreased to zero so that when the player inputs the bound key(UP-ARROW) the second time, the extraJump would become 0, and the next time if the player continuously presses the key again, it wouldn't affect anything to the game object and the player won't be able to jump more than twice.
        
Triple Jump: Change the value of extraJump to 2. 
You can use any number of jumps depending upon what you want in your game.
      
![jumpsss](https://user-images.githubusercontent.com/44625252/152815263-4cd31bb1-9d4f-4352-af3e-ac3befcec2d3.png)

