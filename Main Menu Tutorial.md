# Main Menu Tutorial

In this tutorial I will teach you how to create a main menu and have it move in a 2D game. The first thing to do is to create a new scene and its done by right clicking in the project area and press create then scroll down to scene. Your game will have t The new scene will be empty and so first you create a button by right clicking in the hiearchary and scrolling down to UI. press UI then scroll down and select Button-TextMeshPro. Name that button start. You name the button on the scene by pressing the triangle thats next to your button on the hierachry and underneath will appear the option called, Text (TMP). When pressed, the inspector shows the option called TextMeshPro-Text (UI) and thats where you can name your start button.

Now onto the script part. First create a new script called MainMenu by right clicking in the project and pressing create then C# Script. The first few lines we need to type in will be directly under the the first few lines. Type in ---> using TMPro.Examples;, using UnityEngine;, using UnityEngine.SceneManagment; and using UnityEditor;. We type those four lines so unity can now that our scripts reference and are using this softwares in unity.

![image](https://github.com/user-attachments/assets/9c9dec59-bb29-4c4a-8cb4-b752bdbb590b)

Next you go to the curly bracket ({}) under the where it says public class MainMenu : MonoBehaviour and create some space for youe to type. The first line to type is ----> public void playGame (), then create a set of curly brackets  and in the line between them type in -----> SceneManager.LoadScene("Main");. 
