In this tutorial i will teach you how to move your player in unity, using a movement script. 
First you crate a script in unity by right clicking in the project area and scrolling up to create. After clicking create,
many options will appear and you press the one that says "C# Script". You will be taken into visual studios where your script is.

![image](https://github.com/user-attachments/assets/f5264b23-92b9-43f3-a62f-30c050f8b02d)

The script will look like the image above. The first thing you do is create a public float. Make sure there are is a space. You are making it public so that you can
change it in unit without having to go back to visual studios. Float converts floating points (decimals or fractions) into integers (whole numbers) and that allows the player to move. 
After public float, type speed = 10f. This means the speed is 10 and the f stands for float. if you want the player to be faster incease the number and if you want the player to be slower 
decrease the number. Remember that after writing a line of code you must add a semicolon (;) at the end. When complete the line should look like this --> public float speed = 10f;. when done
save the script (Ctrl + S) and go back to unity. When in unity drag the script into the players inspector (the side bit shown when on the player) and speed will be available to change if you want.
To check if there are no errors press play.If there are just come back here and see if you did something wrong. The player won't move just yet but we are getting there :) .

![image](https://github.com/user-attachments/assets/820f7d23-bf77-457a-acf5-0cc1672b8e81)




The next step is to go back to the script and go down to void Update(). Under it will be two curly brackets and a space between them, thats were you will write your next lines of code.
The first line of code will Vector3 move = Vector3.right * Input.GetAxis("Horizontal"). Vector is where your players spawn  direction and the 3 is for the 3 different axis' (X,Y,Z). I put 
right in because that will be where the player is facing. Input.GetAxis("Horizontal") ensures that the player will also be able to face the left when moving left. After you finish that line,
create a new line under it and type transform.Translate(move * speed * Time.deltaTime). Transform is just the component that is in charge of the position, scale and rotation of t a game object.



Make sure you put a semicolon
at the end.

