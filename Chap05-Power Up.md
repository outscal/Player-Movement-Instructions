# Power-Ups

What makes a game interesting to play???🤔🤔 is it the story?? maybe, is it the player??? not so much, it is the game power ups that make the game more interesting, because they are in the favour of player which hypes up the users very much more 😍😍
    <br>
    
![power_up](https://media.giphy.com/media/Ri9WBdFdDVEpVUfE07/giphy.gif)

If you want to make your game interesting then add the feature of Power-ups and Collectibles. Power-ups are nothing but collecting items or points which will give the player a special ability. The ability could be anything- double jump, dash, or some attacks. 

Here, you will learn how to implement Power-Ups or Collectibles.

1. Drop a game object in the scene view.
2. Use a collider and in the collider component click ✅ the “Is Trigger” option.
3. Now, while implementing the logic, use compares tag to compare with the game object it collides with and after the collision, destroy the power-up game object.

![powerups](https://user-images.githubusercontent.com/44625252/152814423-612839ee-044f-4050-9c20-e8161c8d5e25.png)

You can add tons of features here like, after collecting the item enabling the double jump ability to the player for some seconds. This way, the player could only double jump if he gets the power up feature and that too for a limited period of time. To do this you can add a timer or use coroutines, for which you can read in the Dash mechanism section. 


Refer to the clip below to get an idea of what to implement

![What to Implement](https://media.giphy.com/media/SBEFjvLO5wbfvBnO4Y/giphy.gif)



Here, after getting the yellow-colored game object, which is a collectible item here, the player became big. Likewise, you need to make a player double jump when the player gets a power-up.

Bonus: If you really want to implement Dash mechanism then check out the [Player Dash](https://github.com/outscal/2D-Dash-Feature) repo.

![Bonus](https://media.giphy.com/media/fSSJUQNZOSJgsx7j8e/giphy.gif)
