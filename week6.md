**Intro**

Introduce us as Bit members

Announce goals:
- Provide foundation for how to insert audio and sfx into our game
- Make scripts communicate with each other
- Learn animation and state control to practice boolean logic

Show off a demo of example UI / inventory system and jumping mechanism

**Part 1**

[insert link to demo project here]

Review: instantiating new scripts as components and accessing variables:
- Q: How do we make a new script and automatically attach it to an object in our game?
-- Select an object, go to the inspector window, and click Add Component
- Q: What's the difference between public and private variables?
-- Public variables can be directly changed by other scripts, and by users in the inspector

In the demo scene, create a new object called "Player Manager" and add the following script to it.

~~~
public class PlayerStats : MonoBehaviour {
    public float health;
    public float hunger;
    public float energy;
    public int money;
    private int age;
}
~~~

Save, take a look at the script in inspector and discuss what is visible, and how the variables can be edited.

**Part 2**

"To actually access those variables from another script, we need to have a reference to it. Since the scripts we're interested in are usually attached to another game object floating around in the scene, we first need a reference to the object, and then use GetComponent to secure the script."

~~~
public class Player : MonoBehaviour {
    public GameObject playerManager;
    private PlayerStats playerStats;
    
    void Start(){
        playerStats = playerManager.GetComponent<PlayerStats>();
    }
    
    void Update(){
        playerStats.money += 1;
    }
}
~~~

**Part 3**

Introduction to collision / trigger as well as user input handling
- Press key to play sound
- Play sound when collision occurs

**Activities**

- Drag assets into components
- Print to console when collision occurs

**Homework**

- Some project with shared information, like a global scorekeeper, or an inventory system
-- Maybe it can follow a theme, like what the player can do depends on some hidden state.










