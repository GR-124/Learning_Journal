# Main Menu Tutorial

In this tutorial I will teach you how to create a main menu in a 2D game. The first thing to do is to create a new scene and its done by right clicking in the project area and press create then scroll down to scene. Your game will have t The new scene will be empty and so first you create a button by right clicking in the hiearchary and scrolling down to UI. press UI then scroll down and select Button-TextMeshPro. Name that button start. You name the button on the scene by pressing the triangle thats next to your button on the hierachry and underneath will appear the option called, Text (TMP). When pressed, the inspector shows the option called TextMeshPro-Text (UI) and thats where you can name your start button. A exit button would also be important to make so you can quit the game.

Now onto the script part. First create a new script called MainMenu by right clicking in the project and pressing create then C# Script. The first few lines we need to type in will be directly under the the first few lines. Type in ---> using TMPro.Examples;, using UnityEngine;, using UnityEngine.SceneManagment; and using UnityEditor;. We type those four lines so unity can now that our scripts reference and are using this softwares in unity.

![image](https://github.com/user-attachments/assets/9c9dec59-bb29-4c4a-8cb4-b752bdbb590b)

Next you go to the curly bracket ({}) under the where it says public class MainMenu : MonoBehaviour and create some space for youe to type. The first line to type is ----> public void playGame (), then create a set of curly brackets  and in the line between them type in -----> SceneManager.LoadScene("Main");. This line allows you to go from the main menu to the game. I called the scene with the game in it Main, but you can call the scene whatever you want (as long as its the same name as the scene in unity). 

![image](https://github.com/user-attachments/assets/0b59f06b-b474-4194-ad2c-e9de256cf4d5)

The next line of the script you need to type in is ----> public void options(). Set the curly brackets and inbetween them type ----> Debug.Log("options");. Logs are messages sent to the unity console and debug is a debugger which allows your code to run without any problems. Debug.Log just means that the code is sending debugging messages to unity and that allows the code to run smoothly. In the brackets I typed the word options, I did this because I created a new button called options. The debugging is for this button because options will bring you to a different scene that will have more buttons. In this tutorial I am only focusing on the main menu and getting from there to the game, but many of the things I've written in here can and do apply in making the options button. 

![image](https://github.com/user-attachments/assets/deeb76c0-33ca-460a-bc34-fdac8ef2ed6f)

The final part of this code is for the exit button. First type in ---> public void exit(). Next create the curly brackets. Some of the coming lines will have a # and they should be outside the curlly brackets. Next thing to  type underneath the last line and between the curly brackets ---> #if UNITY_EDITOR. This is a different type of if statement than the ones I have done in previous tutorials. Back inside the curly brackets and under the last line type ----> EditorApplication.ExitPlaymode();. This means when you press exit it will take you out of the game. Next you go down a line and type -----> #else then down another line ----> Application.Quit(); and down a line one more time and type ----> #endif. The else and application quit part were just incase of if you choose to quit and close the game by closing the application instead of just pressing the quit button. 

![image](https://github.com/user-attachments/assets/93dd0530-ea3b-4306-aa64-d9ee7a183e17)

With that done, the script is complete. Underneath is the full script. 
