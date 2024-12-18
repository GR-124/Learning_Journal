# NPC Behavaior Tutorial
In this tutorial I will teach you how to create an NPC (non playable charater) and have it move in a 2D game. First thing to do is create the npc by going to the hierarchy (left side) and right click. Once you right click many options appear and you need to go down to 2D object and once clicked more options appear and press Sprites. After that, even more options will appear. Go to square be thats what i will be using. Name the square npc and in the top of its inspector (right side) and so to Layer. Create a new layer called NPC because it will be important afterwards. The top of the NPC's inspector says layer and when pressed there will be different layers. You created the NPC layer and thats the layer you press. In the inspector of the NPC add a Rigidbody2D and Box Collider 2D. Go back to the hierarchy and create an empty object and call it Barrier. In its inspector there is a cube, press it and give it an icon (give it a colour). Give the barrier a Box collider2D and RigidBody2D. Make sure to make the RigidBody2D static. Copy the barrier and place both in places where you want the NPC to move in between.

On to the script part. First create a script in unity by right clicking in the project area and scrolling up to create. After clicking create, many options will appear and you press the one that says "C# Script". 
You will be taken into visual studios where your script is. First thing you should know is that after writing a line of code you have to put a semi colon (;) at the end inorder for it to work. Go under the first curly
bracket ({}) and create some space for where we will be typing in our code. The first two lines we need to type in is ----> public float speed; and underneath ----> public float moveRate;. Go down two more lines and now
type in another two lines of code. Those lines are ----> public int dirX; and underneath ----> public int dirY;. The public speed and moveRate controls the NPC's speed and how often it moves. dir means direction and the X and Y refer to the axis'. The X axis allows the NPC to move horizontally (side to side) and the Y axis allows it to move vertically (up and down).

![image](https://github.com/user-attachments/assets/c951efdd-bf79-4a23-9d9a-2e8490548baf)

The next line to type is ----> private float moveCounter;. The moveCounter turns where the NPC is into number to track where it goes and we put it as priavte becaue we don't need to change it in unity later. Under that line,
you will type in a new one. That line is -----> private new RigidBody2D rigidbody2D {get { return GetComponent<RigidBody2D>() ?? default(RigidBody2D); }}. This line ensures that you can access rigidbody components such as mass and gravity. It basically means the NPC will obey the laws of physics. 

![image](https://github.com/user-attachments/assets/55bf155d-15cb-4bd3-be96-2bda27f4657c)

Now go down and type ---> private void Update() and go to the line underneath and create the first set of curly brackets. We will be typing in an if staement, so first type in ----> if (rigidbody2D) and create two new curly brackets with a few lines between them. In the first line inbetween the curly brackets type in -----> if (moveCounter > moveRate). We need to then make more curly brackets, the same way we just done. In that third set of curly brackets type ----> ChangeDirection(); and underneath type ---> moveCounter = 0f;. What we just typed means that when the moveCounter is tracking the NPC and its number is less then 0 it will make the NPC change direction. Under the third set of curly brackets but still inside the second is where we will continue to type. First type in -----> Vector2 vel = new Vector2(dirX * speed, dirY * speed);. Two lines down, type in ----> rigidbody2D.velocity = Vector2.Lerp(rigidbody2D.velocity, vel Time.deltaTime * 10f);. Go down two lines again and type -----> moveCounter += Time.deltaTime;. Those last three lines all control the speed and distance that the NPC will go. You may be asking what Lerp is and what is means. Lerp stands for linear interpolation. What Lerp does ,in simple terms, is it changes the value of on object for where it was to where it moved to.

![image](https://github.com/user-attachments/assets/79757de7-ed8c-4f23-90dc-e2469806fc11)

Now underneath all three of the curly brackets you just made earlier create some space and type -----> private void ChangeDiretion() and under it make the curly brackets like how we've made them so many times before.
The last two lines we need to type in depend on you. Type in ----> dirX = Random. Range(-1, 1); amd underneath  type ----> dirY = Random. Range(-1, 1); The numbers in the X direction can and should be changed base on your game and how far you want the NPC to move, for example in my game its (-2, 4);. The Y direction does not really matter unless you want the NPC to float or fly. Ignore the green stuff, i typed them in as notes and things i should remember.

![image](https://github.com/user-attachments/assets/e3e4235f-3f0e-4eac-ac63-e82923ba3cfb)

Underneath is the full script and the code should work but if not then come back here and see what you did wrong. Goodbye and your welcome for the tutorial :) .

![image](https://github.com/user-attachments/assets/549d3734-565a-4adf-88d9-e9ed81e0dfe7)
