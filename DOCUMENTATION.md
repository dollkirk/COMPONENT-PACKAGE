# DOCUMENTATION

## TURRET ARENA COMPONENT PACKAGE

### TURRET MOVEMENT:
This script finds the postion of the player object, what the bullet prefab game object is, and the spawn position of the bullet prefab on the turret.
It checks if the turret object is on, and if so, to make the turret look at the player object.
It also instantiates the bullet prefab object at the spawn point with a forward force.
This script should be attached to each turret created, and the bullet speed and fire rate values can be edited in the Inspector.


### TURRET ON:
This script sets the turret to be off unless the player object enters with the fire area of the turret. When the player object leaves the fire area, the turret is set back to off. For testing, the script component can be set as true in the Inspector without the player object having to enter the fire area of that turret.

### BULLET DESTROY:
This script destroys the bullet object that the script is attached to after a certain amount of time. This should be attached to the bullet prefab and in the Inspector, the amount of time given till it destroys can be edited.

### TIMER:

