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
Inbetween those brackets, type type in ----> instance = this; and under it type in ---> DontDestroyOnLoad(this);. 
