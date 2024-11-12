# Respawn Controller Tutorial
In this tutorial, I will show you make a Respawn Controller script. Before we start i should mention that this script will reference both a Damage Player and Health Controller script. In addition to those two
scripts, this script unlike the others referenced, it also refernces another script. That script is the Respawn Point script.
I have made tutorials on how to make both of those as well so after this go look at them.If you've looked at those first and already have the scripts you should be fine (unless you done something wrong). 
 First thing you do is make sure you have a player, ground and for now just add an empty object that will be what will damage your player (i'll be using a red square because my player is just a green square).

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

Don't worry about the green lines of code.

![image](https://github.com/user-attachments/assets/263fc960-bffd-4b22-93c7-c0525120e8c1)
![image](https://github.com/user-attachments/assets/e4c100d2-5918-4e89-aa8f-00b25b20be9e)

When finished, the code should work (if you have the other scripts) but if not then come back here and see what you did wrong. Goodbye and your welcome for the tutorial :). 



