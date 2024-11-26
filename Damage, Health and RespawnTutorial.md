# Damage, Health and Respawn Player Tutorials
In this tutorial i will show you how to make a Damage Player script, a Health Controller script and a Respawn Controller script. In the Respawn Controller script it references a 4th script.
The 4th script is for the Respawn Point. These scripts are for 2D games but with minor tweaks they can be for 3D as well. I will start with the Damage Player script.
## Damage Player script
Before i start you should know a Health controller and Respawn Controller script is needed so you can reference it in this script or
they reference each other.If you don't have one thats fine because further down there will be tutorials for both. First thing you do is make sure you have a player, ground and for now just add an 
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
is a projectile. When that projectile enters the players barrier (collider) it will trigger something in the player. Next is to go under the line and add curly brackets with space between. In that space type in a this
if statement ---> if (other.gameObject.tag == "Player"). After this put curly brackets under it and make sure there is a space inbetween. In the space, type ----> DealDamage(). We've typed in these lines before but the difference is that the damage is triggered by something entering the players barrier.

![image](https://github.com/user-attachments/assets/772784b2-bb13-41b5-85fe-1c4ddc263b96)

The last line of code needed in this script tyes back to the beginning and will refernce a health controller script. The first line is ---> void DealDamage(). Under, put curly brackets and in the space in between, type
----> HealthController.instance.DamagePlayer(damageAmount;. This line ensures that when the player takes damage it affects its health. Depending on how much health the player has and how much damage it takes it could either just hurt the player or its could straight up just kill the player.    

![image](https://github.com/user-attachments/assets/7bae4537-d518-40a6-8eb9-5c04c60112cb)

The full script is below.Depending on if you have a health controller script and a respawn controller script, this script should work but if not come back to see what you did wrong.On to the next tutorial.

![image](https://github.com/user-attachments/assets/0e0fd4ce-58db-4e38-9a86-c5f86526bb7f)


## Health Controller script
Now that i've done the Damage Player script, I will show you make a Health Controller script. As mentioned before this script will reference both a Damage Player and Respawn Controller script.
First thing you do is make sure you have a player, ground and for now just add an empty object that will be what will damage your player (i'll be using a red square because my player is just a green square).

Now on to the actual script part. Right click on the project part of unity and go to create then to C# Script. When in Visual studios, go under the curly bracket (do not delete it cos they are important) thats just under
the line, public class HealthController : MonoBehaviour. Create some space for the code we are gonna type (make the space big). The first line you type is ---> public static HealthController instance. This line ensures
that the players health can be changed in unity because it is public. Underneath you type the line ----> private void Awake(). Under that type in two curly brackets ({}) and a space and a line between them. In that line type
----> instance = this; The lines you just typed in determine what number will be the health of the player but because its public you typed in "this" and it can be changed to any number you want in unity.  

![image](https://github.com/user-attachments/assets/6fe14179-c705-4e9b-813e-00dc4432215d)

The next line of code will be ----> [HideInspector] and under type in two lines (one under the other). Those lines are ----> public int currentHealth; and public int maxHealth;. The first line you typed hides the other
two lines in unity. Public int currentHealth shows how much the player has in that moment. Public int maxHealth shows how much health the player is allowed to have and is what the player typically starts with. Remember
that in the end of the last two lines you need to type in a semi colon (;).

![image](https://github.com/user-attachments/assets/10eb641e-4de9-42e0-ac93-67a34843318f)

There are lines that already come with the script and one is the line ---> void Start(). Under that line is the curly brackets with a line in the middle. On the middle line type ----> currentHealth = maxHealth;.
That line means that when you start the game, the health the player starts with is the most it will have and most it can have.


![image](https://github.com/user-attachments/assets/04e193cf-2e9c-43a5-8ad3-740d20b6d268)


Unlike the last line, the line you will next need to type does not have bits that already come with the script. This line refernces other components from other scripts, so with those scripts this won't work.
Don't worry though, you will be fine if and when you have the other two scripts that are referenced. As i mentioned before, i have made tutorials on the scripts needed. Under the void Update line create some
space for your lines. First line you type is ----> public void DamagePlayer(int damageAmount). This reference will connect the Health Controller script and the Damage Player script. Type in curly brackets how
we have done all the other times and in the line between type in ----> currentHealth -= damageAmount;. This line means, when the player is damaged it will lower its health. Under that line we type in an if statement.
The if statement is a condition that must be met inorder for a specific something to happen. The if statement is ----> if (currentHealth < 0). Type in curly brackets underneath and in the line inbetween type
----> currentHealth = 0;. Create another space under the last line (make sure its still inbetween the curly brackets) and type ---> RespawnController.instance.RespawnPlayer();. That last line references the Respawn Controller script. The lines of code we just typed mean that if the player gets damaged to the point where its health is zero, then it will die and respawn.

![image](https://github.com/user-attachments/assets/432952fa-6183-4730-bfad-61fbdd576ef0)

With that done, your script is complete. Below is the full script. If the script doesn't work, remeber you need the Damage Player script and the Respawn Controller script and if you have those and still something is wrong
come back and see what you did wrong. On to the next tutorial.

![image](https://github.com/user-attachments/assets/cf4dacda-4d19-47b5-8fe7-c899a25ec4e5)

## Respawn Controller script
Now I will show you how to make a Respawn Controller script. This script (just like the ones before it) will reference both a Damage Player and Health Controller script. In addition to those two
scripts, this script unlike the others referenced, it also refernces another script. That script is the Respawn Point script and the other scripts don't reference it.
 First thing you do is make sure you have a player, ground and for now just add an empty object that will be what will damage your player (i'll be using a red square because my player is just a green square). Then the next thing is to go on the hierarchy and create an empty and call it RespawnManager. Thats where the scrpit will be instead of in the player.

Now on to the actual script part. Right click on the project part of unity and go to create then to C# Script. When in Visual studios, go under the curly bracket (do not delete it cos they are important) thats just under the line, public class RespawnController : MonoBehaviour. The first line you need to type is ---> public static RespawnController instance;. public means that it can be changed in in unity and static means that it won't move unless you move it. The next lines that must be typed in in are ----> public Vector3 respawnPoint; and under it type ----> public float waitToRespawn;. Vector3 refers to the 3 axis' and respawnPoint is where the player will
respawn once it dies. It also refers to the Respawn Point script. In the second line float converts floating points (decimals or fractions) into integers (whole numbers) and that allows the player to move, and waitToRespawn
means that the player does not respawn immediately. You can change how long the wait is for the player to respawn because the line starts with public. Under the last line type in ----> public GameObject thePlayer;.
This line ensures that the game knows that the player is the one thats supposed to die and respawn.

![image](https://github.com/user-attachments/assets/cbedb2f9-297f-4495-8db8-4bdae397c787)

After the lines you just typed in create a new line and type in ---->  public void Awake () and type in the curly brackets on top of each other and a space between. In that space, you type in an if statement.
That if statement is -----> if (instance != null). Under that, type in another set of curly brackets and inbetween type in Destroy(this.gameObject);. Null represents the absence of an object and so the line
means if there is no object. The next line means that the player should get destroyed (disappear) when it dies. Next you type else, which acts as an alternative to the if staement then type in the curly brackets.
Inbetween those brackets, type type in ----> instance = this; and under it type in ---> DontDestroyOnLoad(this);. These lines make sure that the player can spawn and not get destroyed in because it spawned in the 
respawn point.

![image](https://github.com/user-attachments/assets/129c5801-3313-4530-b86a-9cde9887e4c8)

After those lines go to void Start(). Under that line, there will already be curly brackets and inbetween you will type two lines in. The first line is -----> thePlayer = HealthController.instance.gameObject;. This line 
references the Health Controller script and it ensures that the player and the health controller are connected so when the player dies and has to respawn the health controller knows the players health was zero and
when it respawns it will have full health again. The second line is ---> respawnPoint = transform.position;. This line references the Respawn Point script. The line means that when the player will rrespawn wherever
you set the respawn point.

![image](https://github.com/user-attachments/assets/19d563b3-9b3e-4445-b117-7c25c273f9f7)

After putting some space between the last lines, the next line of code to type in is ---> public void SetRespawn(Vector3 pos) then underneath put in the curly brackets and type in ----> respawnPoint = pos;.
Both lines ensure that the player will respawn where you put the respawn point and because its public it can be moved in unity. Next, type in ---> public void RespawnPlayer() and underneath put in curly 
brackets and type in ----> StartCoroutine(RespawnCo());. A StartCoroutine is like an if statment but when it a encounters a yeild statment it waits till the condition is met and continues from where it left of.
A yeild staement pauses other functions to allow other functions to run then lets the first function to run again. 

![image](https://github.com/user-attachments/assets/f7aed519-4e69-41a3-b39b-4b9ba1b95dfb)

The next few lines of code will be ----> IEnumerator RespawnCo(), then put in the curly brackets and in between the first line you type is -----> thePlayer.SetActive(false);. The IEnumerator's function is to go
through each yeild and makes sure that what its paused will run again. The next line under the last you typed will be ----> yeild return new WaitForSeconds(waitToRespawn);. This line makes it so the player will
have to wait a few seconds before respawning. The next line is ----> thePlayer.transform.position = respawnPoint; and under it the line is ----> thePlayer.SetActive(true);. Those two lines make sure that where ever i move the spawn point is where the player will spawn. 

![image](https://github.com/user-attachments/assets/40b46062-5167-49d2-b2ec-938a373d19db)

With that done, your script is complete. Below is the full script. If the script doesn't work, remeber you need the Damage Player script and the Respawn Controller script and the Respawn Point script. If you have those and still something is wrong come back and see what you did wrong. Full script bellow. Don't worry about the green lines of code. On to the next tutorial.

![image](https://github.com/user-attachments/assets/b6788f18-b4bf-4d6a-ae5e-57f700dc5c51)
![image](https://github.com/user-attachments/assets/1bd99178-2bed-4f81-abbb-8801f48e8108)

## Respawn Point script
This is the fourth and final script in this tutorial, the Respawn Point script. First thing to do is to go to the hiearchy in unity and and create an empty. Call that empty Respawn Point and drag it
into Respawn Manager. The script will be put into Respawn point. When in the inspector of Respawn Point there will be a white box in the top left corner. I would advise you click it and change the colour.
The box (when its colour is changed), shows you where the respawn point will be and you can move it. While in the inspector add a component. Depending on if you are making an 2D OR 3D game you add
in a box collider or box collider 2D and the tick the box that says trigger. When that box is ticked it will allow the player to pass through it and when it does it will trigger somkething, in this case
it will allow the player to respawn at the point of where it came in contact with the respawn point.

Now on to the actual script part. Right click on the project part of unity and go to create then to C# Script. When in Visual studios, go under the curly bracket (do not delete it cos they are important) thats just under the line, public class RespawnPoint : MonoBehaviour. Go down under the default code and make some space for the one we will be typing in and make sure no curly brackets ({}) get deleted. The first line of code
you need to type is ----> private void OnTriggerEnter2D(Collider2D collison). This line means that when the player comes in contact with the collider we put in before something will happen. Next thing to do is go
under your previous line and type in ----> if (collision.CompareTag("Player")). This if statement means that if the player comes in contact with the collider something will happen and it only applies to the player.
Under that line type in the curly brackets with a line inbetween them and in the the space type ----> RespawnController.instance.SetRespawn(this.transform.position);.This line ensures that the player will respawn 
where it first came in contact with the respawn point. 
When finished, the code should work (if you have the other scripts) but if not then come back here and see what you did wrong. The full script bellow. Goodbye and your welcome for the tutorials :). 

![image](https://github.com/user-attachments/assets/30e05870-ad92-4b23-8175-5d73f7cccc51)












