COMPONENT PACKAGE- 

PROBLEM:
I created a scene with 2 planes, a player object and a turret on the second plane. I wanted it so that when the player entered the second area, the turret would activate and start firing the bullets. I also wanted it so that when the player entered it, a timer would start and if the timer ran out, the turret would cool down for a set time and the cool down time would display.

To start, I created a PlayerMovement script, a TurretMovement script and a BulletController script. The TurretMovement script just updates the turret object to look at the player and the BulletController script instantiates the bullet prefab with a force repeatedly after a set time.

I wanted these scripts to be activated when the player collides with the second plane area collider.

I created a script called TurretOn which would find out when the player collides with the area, and pass a boolean value of true to both of the other scripts.

SOLUTION:
When trying to pass the boolean value from this TurretOn script to the other two scripts, I had set the boolean value to private, which meant the scripts could not access this value. I changed this to a public variable and used “ { get; private set} to make the variable accessible via scripts but not accessible in the Unity editor.

