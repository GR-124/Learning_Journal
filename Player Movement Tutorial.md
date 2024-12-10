# Player Movement Tutorial
In this tutorial i will teach you how to move your 2D player using a movement script. Start by making a new project and making it 2D. 
First you crate a empty player by going in the inspector, right click press 2D object then press square. Do the same for a floor (ground) and name them both player and ground.
Create script in unity by right clicking in the project area and scrolling up to create. After clicking create, many options will appear and you press the one that says "C# Script".
You will be taken into visual studios where your script is. First thing you should know is that after writing a line of code you have to put a semi colon (;) at the end inorder for it
to work.

The first thing you do is create a public Rigidbody2D then space and type  theRB. this enables your player to act under the laws of physics.
Then type public float. Make sure there are is a space. You are making it public so that you can change it in unit without having to go back to visual studios. 
Float converts floating points (decimals or fractions) into integers (whole numbers) and that allows the player to move. 
After public float, moveSpeed. Under you type pulic float jumpForce. Its public which means the speed can be changed from unity. Then you must make 2 more public's and one private.
(public Transform groundPoint, Private bool isOnGround, public LayerMask whatIsGround). The last 3 lines were put there so the player knows when its on the ground which is important
for jumping. Remember that after writing a line of code you must add a semicolon (;) at the end. Save the script (Ctrl + S) and go back to unity. When in unity drag the script into
the players inspector (the side bit shown when on the player) and speed and jump force (how high you jump) will be available to change if you want. You will also have to create a ground layer
for your ground and a ground point in the inspector. To check if there are no errors press play.If there are just come back here and see if you did something wrong. 


![image](https://github.com/user-attachments/assets/94ebc9d5-2ac2-4089-b3e7-48e5b85b2356)




The next step is to go back to the script and go down to void Update(). Under it will be two curly brackets and a space between them, thats were you will write your next lines of code.
The first line of code will be -->  theRB.velocity = new Vector2(Input.GetAxis("Horizontal") * moveSpeed, theRB.velocity.y);. Vector is where your players spawn  direction and the 2 is
for the 2 different axis' (X,Y), its not 3 because the game we are making is 2D so the z axis is not needed. Input.GetAxis("Horizontal")ensures that the player will also be able to face the 
left or right when moving left or right. Under you will type this line --->  if (theRB.velocity.x < 0). the if is there as a condition. It means the player can only do this certain thing if the conditions
are met. Under that you type in a curly bracket go down two and put another curly bracket. In the line between you type in --->  transform.localScale = new Vector3(-1f, 1f, 1f); transform refers to the the position, rotation and scale of an object. Local scale determines the size. I explained what a vector is earlier, but now instead of 2, its 3 because we also include the z axis. 



![image](https://github.com/user-attachments/assets/bdd81003-c864-4c4c-9dee-68c7f29bb385)


Under this you will type else then under put the curly brackets like the last line. Then type the same if code from before, execpt after the Vector3, type .one and dont forget the semi colon at the end.
Under that you type ----> isOnGround = Physics2D.OverlapCircle(groundPoint.position, .2f, whatIsGround);. isOnGround = Physics2D means that when the player is on the ground, the laws laws of physics are
applicable to the player (e.g. gravity). Under the last line, type another if statment. This time the if statement is ----> if (Input.GetButtonDown("Jump") && isGround). This line means that when you press
down the button (usually the space bar) the player jumps but only when its on the ground. After that you put the curly brackets under. between the curly brackets, type --->
theRB.velocity = new Vector2(theRB.x, jumpForce);.  This line ensures that the player stays upright when jumping and will make the player jumps the direction its mean't to go.


![image](https://github.com/user-attachments/assets/faaa0627-3d47-49e7-ba56-c9c4271e3c2c)


When finished, the code should work but if not then come back here and see what you did wrong. Under is the full thing. Though it doesn't show in the picture below there should be two curly brackets facing outwards,
DO NOT delete them they are connected to the two curly brackets at the top of your code and are important. Goodbye and your welcome for the tutorial :) .

![image](https://github.com/user-attachments/assets/f84ba301-7db3-4d27-ab66-d67d132b8f05)

![image](https://github.com/user-attachments/assets/1c5fe51b-eadd-408d-b8f1-a7c60af8d7de)

(Dont worry about the green writing)







