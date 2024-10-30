In this tutorial i will show you how to make a Damage Player script. Before i start you should know a Health controller and Respawn Controller script is needed so you can reference it in this script or
they reference each other.If you don't have one thats fine i will (or already have) make a tutorial for one as well. First thing you do is make sure you have a player, ground and for now just add an 
empty object that will be what will damage your player (i'll be using a  red square because my player is just a  green square).

Now on to the actual script part. Right click on the project part of unity and go to create then to C# Script. When in visual studios, under the first curly bracket ({}), type in the ---> public int damageAmount = 1;.
That line shows how much the damge will be but because its public it can be changed in unity. The next line of code will be ---> private void onCollisionEnter2D(Collison2D other). This line makes sure that when the player
comes in contact with whatever has this script on it, will collide with it.

![image](https://github.com/user-attachments/assets/2f372e25-5e78-45a9-ab26-2ae453f65469)

Next thing to do is go to the line above void start and press enter a bunch of times to create a space between it and the lines you just wrote. In the space under the line put in two curly brackets and some space between.
The first line to type is ---> if (other.gameObject.tag == "Player"). Under that line, type in another two curly brackets just like what was done before. Between the curly brackets type in ---> DealDamage();.
This whole thing ensures that when colliding with whatever has the script will take damage.

![image](https://github.com/user-attachments/assets/97f4c17e-581a-4d53-9155-d5c17ab04ab8)

Next create some space between the last lines of code so we can make a new line of code. The first new line is ----> private void OnTriggerEnter2D(Collider2D other). This line is for if whatever is mean to damage the player
is a projectile. When that projectile enters the players barrier (collider) it will trigger damage to the player.
