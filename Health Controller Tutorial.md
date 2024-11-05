In this tutorial, I will show you make a Health Controller script. Before we start i should mention that this script will reference both a Damage Player and Respawn Controller script. I have made tutorials on how to
make both of those as well so after this go look at them.If you've looked at those first and already have the scripts you should be fine (unless you done something wrong). First thing you do is make sure you have a player, ground and for now just add an empty object that will be what will damage your player (i'll be using a red square because my player is just a green square).

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
come back and see what you did wrong. Goddbye and your welcome for the tutorial :).

![image](https://github.com/user-attachments/assets/cf4dacda-4d19-47b5-8fe7-c899a25ec4e5)

