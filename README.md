# **Introduction to Game Development**
### Course Details
Duration: 10-12 weeks

Level: 5th - 8th Grade

Created by Daniel Panfili, PhD 

Distributed by Mindset of Champions

## Overview
Video games come in all shapes and sizes. Teams of hundreds of people work year round on AAA titles like Fortnite, Call of Duty, and League of Legends. Other games are developed over a number of years by small teams, or sometimes by a single developer (Undertale, Stardew Valley, ). Regardless of how big or small, making a game requires a variety of different skills. Programming, art, music, design, and testing—each of these elements must come together to make a game, especially one people want to play.

In this course, we will walk through each of the stages of game development. Using the Unity Engine, students will create a game of their own over the course of 12 weeks while learning the basics of computer programming and game production. Students may choose to work with a team at any point, but all students will do class activities individually to amass their own assets. At the end of the course, students will participate in a Game Jam, publishing their game online and helping playtest their classmate’s games.

Game Jam Theme: One Button

## Syllabus at a Glance
1. Introduction to Unity
2. Planning & Brainstorming
3. Basics of Logic
4. Level Design & Progression
5. Game Programming
6. Art & Animation
7. User Interface & Experience
8. Sound & Music
9. Testing, Debugging & Feedback
10. Final Project 

# Week 1: Introduction to Unity

## Objectives
- Understand the basics of the Unity interface.
- Follow a guided project to create a simple game (Flappy Clone).
- Familiarize students with the game development process.

## Preperation
1. Required Software
	- Unity Hub
	- Unity 2022.3.49f1 (LTS)
	- Visual Studio Code
2. YouTube
	- [GMTK - The Unity Tutorial For Complete Beginners](https://www.youtube.com/watch?v=XtQMytORBmM&t=1312s)
	- [Fireship - Unity in 100 Seconds](https://www.youtube.com/watch?v=iqlH4okiQqg)
3. Unity
	- [Tutorials](https://learn.unity.com/)
	- [Manual](https://docs.unity3d.com/Manual/UnityOverview.html)

## Lesson Plan

1. **Introduction to the Course --- 10 Minutes**
	- Overview of game development and its importance.
		- Game development is interdisciplenary, requiring skills in many areas.
		- Dev teams range from 100's of professionals, to solo amateurs.
		- Team composition, skill, time, and resources have a major influence on the games that can be developed (size, scope, genre, complexity, etc.
		- Game engines like Unity provide a starting block with many tools.
	- Brief discussion on Unity and its relevance in the industry.
		- Large development community, many resources available online.
		- Wide variety of games developed in the engine, including:
			- Fall Guys (3D Platformer Party Game)
			- Among Us (2D Social Deduction Game)
			- Pokemon GO (Mobile AR App)
			- Beat Saber (VR Rhythm Game)
			- Genshin Impact (3D Open World RPG)
	- Overview of the goals of the course
		- All stages of game development will be covered, see syllabus
		- Course will end with a Game Jam, where everyone share the games they made and vote on which games they liked best
		- We will start with a full walkthrough of a simple game to demo each component of game development students will learn.
			- Students don't need to program alongside the teacher, but can if they'd like.

2. **Setting Up Unity**
   - **Installation**
     - Download Unity Hub and the Unity Editor.
     - Create or log into a Unity account.
   - **Creating a New Project**
     - Create a 2D project.
     - Name the project “Flappy Clone”.

3. **Unity Interface**
	- **Scene View**
		- **Definition:** Workspace for designing and arranging game elements.
		- **Navigation:** Use right mouse button to look around, middle button to pan, and scroll wheel to zoom. Use **WASD** keys to move.
		- **Tools:** Includes Move, Rotate, and Scale tools; toggle gizmos for object visualization.
	- **Game View**
		- **Definition:** Simulates the game as players experience it.
		- **Testing:** Enter Play Mode to test functionality (e.g., movement).
		- **Adjusting View:** Change resolution to see game on different screen sizes.
	- **Hierarchy Panel**
		- **Definition:** Lists all game objects in the scene in a tree structure.
		- **Organization:** Create parent-child relationships to manage object transformations.
		- **Management:** Rename, delete, and group objects; use search for quick access.
	- **Inspector Panel**
		- **Definition:** Displays properties of the selected game object.
		- **Modifying Properties:** Change position, rotation, and scale via the Transform component.
		- **Adding Components:** Add colliders, scripts, and adjust settings directly.

4. **Project Setup**
   - **Importing Assets**
     - Download the [Flappy Clone Asset Bundle]().
     - Import the assets into the Unity Project by dragging and dropping.
   - **Organizing Assets**
     - Create folders for sprites, scripts, and sounds.

5. **GameObjects**
	- **Creating the Bird Object**
		- Create an empty game object
		- Add a sprite renderer component.
		- Assign the bird sprite to the GameObject
	- **Add a Camera**
		- A camera should already be included in the game scene.
		- Adjust its view and position until bird is the preferred size.
		- Adjust background color
   - **Adding Physics**
     - Add a *Rigidbody2D* component to the bird.
	     - This adds gravity and collision to the *GameObject*.
	  - Adjust hitbox to preferred size, ideally slightly smaller than bird.

6. **Controls and Movement**
   - **Adding a Script**
     - Create a new script called *character_controller.cs*
	 - Assign the script to the bird *GameObject* by dragging and dropping.
   - **Programming in Unity**
	   - Unity scripts start with a **Start** and **Update** function
	   - **Start** runs at the start of the program.
	   - **Update** runs every time the game updates, also called a **Frame**.
	- **Adding a Flap Mechanic**
		- We want the bird to "flap" when a button is pressed.
		- First, check if the space button was pressed.
			- **IF** statements can be used to ask a question, then do some action if the answer is yes.
		- When space is pressed, we want the bird to start moving upward.
			- To do this, we must add **Velocity**. If position is where you are in space, velocity is how fast you are moving (e.g. miles per hour).
			- We can add velocity to our bird's *Rigidbody2D*, but first we need to create a **Public Variable** to reference it in our script. The bird can then be assigned from the inspector.
		- We also want to control the speed that we move, so we should declare an extra variable for flap strength.
			- Number variables can be an **Int** (whole number integer) or a **Float** (decimal number). Our speed variable should be a float.
     	- Once our code is written, we can test it by pressing **Play** in the editor.

7. **Creating the Pipes**
   - **Adding Pipe Prefabs**
	   - Create a new GameObject for the pipe obstacles, and add a **Collider**.
	   - **Colliders** check if an object is touching another object with a collider.
		   - Our bird already has one from its *Rigidbody2D*.
	   - We will want 2 of these in a column for the bird to jump between. 
		   - Copy-paste the first column, then assign the copy as a **Child** of the first by dragging and dropping in the hierarchy.
		   - **Child** objects are tied to their **Parent**, so they'll move together.
	   - Since we are going want a lot of copies of this, we will make a **Prefab**, or an premade *GameObject* that can be spawned at will.
   - **Spawning Pipes**
     - To make a script that spawns pipes, we can repurpose our earlier code.
     - This script should be assigned to a new GameObject dedicated to handling logic, since pipes will be spawned and despawned.
     - Instead of on a keypress, pipes should spawn over a time interval.
	     - This can be done with a **Timer**---counting the passed time until it hits the desired interval, spawning the next pipe, then resetting.
	    - To spawn a pipe, we can use the **Instantiate** function.
	  - To add difficulty, we can also add randomly set the height of the columns using **Random.Range(lowestHeight, highestHeight)**.
	  - When a pipe is far enough offscreen, we want to despawn it to save memory.
		  - This can be done with a collider, or by checking if its position coordinates.

8. **Scoring System**
   - **Creating a Score Variable**
     - Your score will be the number of pipes you pass through.
     - Similar to despawning the pipes, we can check this either with a new collider between the pipes or by checking if the pipe's X position has passed the bird's.
	     - If we use a collider, we need to set it as a **Trigger** collider. 
	     - We want to know when it enters the area, not have the bird *hit* it like a physical object and stop moving.
   - **Displaying Score**
	   - We can use Unity's built in **Text** objects to display the score on screen. They can be found under **UI**, and added to the hierarchy like a game object.
   - **Incrementing Score**
     - Score tracking should be added to our Game Logic object, since we want it to be tracked constantly.
	     - Score should be a **public int**, since there are no decimals.
     - When we detect the bird passing through the pipe, we add 1 to the score
     - To make sure it was the bird that entered the collider, we can assign the bird a **Layer**, and check if the colliding object was on that layer.

9. **Game Over Mechanic**
    - **Detecting Collisions**
      - Now that we have all of the objects with their colliders in place, we can add the game over mechanic.
    - **Restarting the Game**
      - Introduce a method to restart the game on user input.

11. **Wrap-Up**
    - Reflect on what they learned about Unity and game development.
    - Share the youtube video with students to try at home, and prepare to thinking about their own game ideas for next week.

## Materials Needed
- Unity installed on student computers.
- Flappy Bird asset package (sprites and sounds).
- Access to the video tutorial for reference.



# 
-   Instructors will follow a guided development project where they recreate the game Flappy Bird in Unity.
-   Premade assets kit with reference scripts and walkthrough will be provided to the teacher.
    

-   Instructors will provide an overview of each facet of game development through the dev process.
    
-   Students will install Unity, and learn the basics of the program UI through the walkthrough.
    
-   Students won’t do any programming, but will be able to see a start to finish product.
    

## Week 2: Game Planning + Brainstorming

-   Elements of game design (mechanics, dynamics, aesthetics)
    

-   Designing games within constraints (e.g. One Button games)
    

-   Storyboarding and game planning
    
-   Hands-on activity: Design a simple game concept with design document and mood board
    

## Week 3: Basic Programming

-   Introduction to programming concepts
    
-   Variables, conditionals, and loops
    
-   Hands-on activity: Logic gate puzzles
    

## Week 4: Game Programming

-   Introduction to basic player interaction, game physics, scorekeeping
    
-   Collision detection between game objects
    
-   Hands-on activity: Hello World scripts, Bouncing load screen?
    

## Week 5: Game Art and Animation

-   What art does a game need?
    
-   Importing textures and models
    
-   Hands-on activity: Draw the elements of your game (character, background, obstacle)
    

## Week 6: Sound and Music in Games

-   Importance of audio in games
    
-   Adding background music and sound effects
    
-   Creating interactive audio elements
    
-   Hands-on activity: Make simple sound effects and background music
    

## Week 7: UI and UX

-   Designing and implementing game UI (menus, HUD)
    
-   What information do players need? What information do they only need sometimes?
    
-   Hands-on activity: Add a scoring system and UI to a game
    

## Week 8: Level Design and Game Progression

-   Principles of good level design
    
-   Creating multiple levels or stages
    
-   Implementing difficulty progression
    
-   Hands-on activity: Design your game’s first level
    

## Week 9: Final Project Work - Part 1

-   Form project teams or choose individual projects
    
-   Brainstorm and plan final game projects, use work from earlier weeks
    
-   Hands-on activity: Begin development of final projects
    

## Week 10: Game Testing and Debugging

-   Importance of playtesting
    
-   Identifying and fixing bugs
    
-   Balancing game difficulty
    
-   Hands-on activity: Playtest each other's games
    

## Week 11: Final Project Work - Part 2

-   Finalize projects, debug from playtest
    
-   Work on final presentations
    
-   Hands-on activity: Refine and polish games based on feedback
    

## Week 12: Final Project Presentations

-   Start with project presentations, then play each other’s games
    
-   Let students vote on some accolades for projects, give rewards
    
-   Reflect on the game development process and lessons learned
