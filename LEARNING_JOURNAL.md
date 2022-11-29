# LEARNING JOURNAL

### COMPONENT PACKAGE

**PROBLEM:**
I created a scene with 2 planes, a player object and a turret on the second plane. I wanted it so that when the player entered the second area, the turret would activate and start firing the bullets. I also wanted it so that when the player entered it, a timer would start and if the timer ran out, the turret would cool down for a set time and the cool down time would display.

To start, I created a PlayerMovement script, a TurretMovement script and a BulletController script. The TurretMovement script just updates the turret object to look at the player and the BulletController script instantiates the bullet prefab with a force repeatedly after a set time.

I wanted these scripts to be activated when the player collides with the second plane area collider.

I created a script called TurretOn which would find out when the player collides with the area, and pass a boolean value of true to both of the other scripts.


**SOLUTION:**
When trying to pass the boolean value from this TurretOn script to the other two scripts, I had set the boolean value to private, which meant the scripts could not access this value. I changed this to a public variable and used “ { get; private set} to make the variable accessible via scripts but not accessible in the Unity editor.

![Capture](https://user-images.githubusercontent.com/114989045/201912236-77443c27-1b4f-4ea1-840a-4996c37703a9.PNG)

**PROBLEM:**
I wanted the bullets fired to destroy after a set amount of time. I tried editing the update function in the BulletController script and thought creating a bulletTime float, decrementing it by time and setting that when this float is equal to 0, the clone gameobject of the instantiated bullet prefab would destroy by using clone.IsDestroyed. However, this did not work.

**SOLUTION:**
I asked a peer for some help. They showed me how creating a script for this destroy function would be the best way. I created a script called BulletDestroy and created an if statement to say that if bulletTime is less than or equal to 0, the gameobject that the script is on will destroy.

![Capture](https://user-images.githubusercontent.com/114989045/201926280-489aa458-71b4-4d19-bffb-aa389ec44922.PNG)

**PROBLEM:**
I wanted the turret to stop firing when the player has left the plane and plane area collider. So, I created an OnTriggerExit function and set the boolean variable turretOn to false. This did not work, as when the bullets were colliding with the area, it was setting turretOn as true due to the OnTriggerStay.

**SOLUTION:**
I created a tag called player and then created an if statement in both trigger functions to say if the collider tag is player, set the turretOn variable to true of false.

![Capture](https://user-images.githubusercontent.com/114989045/201932010-4c647517-ab73-48a9-bd85-f6e854218fac.PNG)

**PROBLEM:**
I wanted to make the amount of turrets accessed by the player editable. For example, if a user of the component package wanted to add or subtract turrets to the scene, the current amount of turrets will be accessed.

**SOLUTION:**
In the Timer script which is on the player object, I removed all of the variables referencing the TurretOn script for each turret and just created a list for all of them instead to count the amount of turrets.

![Capture](https://user-images.githubusercontent.com/114989045/204537096-07dbfab2-6368-4a89-8a45-c3a9d68bc33e.PNG)

In the Start function, I need to find the script to find out how many turrets are in the scene so I used "AddRange" to add those found and to find the turret objects, I used "FindObjectsOfType<TurretOn>()". This finds all the objects referencing the "TurretOn" script

![Capture](https://user-images.githubusercontent.com/114989045/204538748-841bf1a4-addd-4b91-8132-6cf81e32e7ff.PNG)

  
