In this tutorial i will teach you how to move your player in unity, using a movement script. Your welcome :)
First you crate a script in unity by right clicking in the project area and scrolling up to create. After clicking create,
many options will appear and you press the one that says "C# Script". You will be taken into visual studios where your script is.







The script will look like the image above. The first thing you do is create a public float. Make sure there are is a space. You are making it public so that you can
change it in unit without having to go back to visual studios. Float converts floating points (decimals or fractions) into integers (whole numbers) and that allows the player to move. 
After public float, type speed = 10f. This means the speed is 10 and the f stands for float. if you want the player to be faster incease the number and if you want the player to be slower 
decrease the number. Remember that after writing a line of code you must add a semicolon (;) at the end. When complete the line should look like this --> public float speed = 10f;. when done
save the script (Ctrl + S) and go back to unity. When in unity drag the script into the players inspector (the side bit shown when on the player) and speed will be available to change if you want.
To check if there are no errors press play.If there are just come back here and see if you did something wrong. The player won't move just yet but we are getting there :) .







The next step is to go back to the script and go down to void Update(). Under it will be two 
