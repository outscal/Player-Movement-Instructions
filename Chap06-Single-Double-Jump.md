# Single/Double/Triple Jump


Player Jump is one of the most crucial elements for this project. Before making the double jump or triple jump first, go through the *Player Movement* section to get an idea of how you can use physics in a particular game object to move it. Also, get yourself familiarized with the RigidBody2D, BoxCollider2D components.

Single Jump: If you have tried to write a code for jump mechanics then you must have seen how the game object behaves when pressing the attached input. It goes infinite at a one-time press. How to fix it? *Hint:* Limit it by using a **bool value**. Also, do not forget to read about *Collison Detection* as it is important for this task.
        
Here is a code where you can get an idea of how to do it.
        
```
    private void OnCollisionEnter2D(Collision2D collision)
    {
        if (collision.gameObject.CompareTag("Platform"))
        {
            onGround = true;
        }
    }
```

Also, this is not the end. You need to write a logic for OnCollisionExit2D as well. Do it by yourself. It will boost your confidence.

Double Jump: Can we use a counter for it? 🤔 It’s like if you press the UP Arrow key once, then it will count for 1 time and jump once. If pressed twice then it will count for 2 times and jump twice. hmmmmmm.... ????? But how to implement it?
    
Let’s see a code and understand it.
        
```
    void Update()
    {
        if (currentTime == 0f)
        {
            finishTimer = true;
        }

        bool vertical = Input.GetKeyDown(KeyCode.UpArrow);

        if (currentTime == 0f || (finishTimer == true))
        {

            Player_Jump(vertical);
        }


        if ((isPickUp == true) && (currentTime > 0f) && finishTimer == false)
        {
            currentTime -= 1 * Time.deltaTime;
            countDownText.text = currentTime.ToString("0");
            PlayerDoubleJump(vertical);
        }
        else if (currentTime <= 0f)
        {
            currentTime = 0f;
            countDownText.gameObject.SetActive(false);
            isPickUp = false;
        }
    }

    void Player_Jump(bool vertical)
    {
        if ((vertical) && (isPickUp != true) && (onGround == true))
        {
            Debug.Log("jump");
            player_Rb.AddForce(new Vector2(0f, 7f), ForceMode2D.Impulse);
        }
    }
    private void PlayerDoubleJump(bool vertical)
    {
        if (onGround == true)
        {
            extraJump = 1;
        }

        if ((vertical) && (extraJump > 0))
        {
            player_Rb.AddForce(new Vector2(0f, 7f), ForceMode2D.Impulse);
            extraJump--;
        }
    }
```
        
Here, the counter is extraJump variable. By default, the game object has the ability to jump by once. So when extraJump is 1 then the game object will jump twice. The extraJump will only be available if the game object stands on the ground platform. The value of extraJump is decreased to zero so that when the player inputs the bound key(UP-ARROW) the second time, the extraJump would become 0, and the next time if the player continuously presses the key again, it wouldn't affect anything to the game object and the player won't be able to jump more than twice.
        
Triple Jump: Change the value of extraJump to 2. 
You can use any number of jumps depending upon what you want in your game.
      
![jumpsss](https://user-images.githubusercontent.com/44625252/152815263-4cd31bb1-9d4f-4352-af3e-ac3befcec2d3.png)

