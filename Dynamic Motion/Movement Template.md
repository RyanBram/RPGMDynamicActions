# DynamicMotion Mobile template [RPG Maker MZ & MV plug-in]
This page is part of the description of the Dynamic Motion plug-in .

I will introduce mobile templates.
There is some overlap with the basic usage page.
Only a brief explanation is given here, so please see the link for details.
*) The version notation is based on the MV version of Dynamic Motion, but all are also valid for Dynamic Motion MZ.

Table of contents

### Approach (near)

Get closer to the subject.
Considering the size of the target and the actor, move to the adjacent position.
In addition, the destination is automatically adjusted according to the "position (overhead, feet, etc.)" set in the animation.
```
<D-Motion: near /> // Approaching the target
```
![Image](https://image.gif)

### Return

It returns to the original position (home position).
Damage processing etc. is also executed at the timing when this is executed.
```
<D-Motion: near /> // Approaching the target
<D-Animation /> // Animation
<D-Motion: return /> // Return
```
![Image](https://image.gif)

By default, it returns to the original position (home position) with a backstep-like operation.
By the way, the pose at this time uses the escape motion. If you don't like it, you can change it as you like by setting the plugin parameters.

As I wrote in "Basic usage", the actor will return to its original position even if this is not specified. However, if the skill user is an enemy, it will not return automatically, so it is recommended to specify it properly.

### Crash

Similar to approaching, but this moves until it overlaps the target.
As the name suggests, it can be used for body crushing.
```
<D-Motion: crash/> // Collision with target
```
![Image](https://image.gif)

### Back

Move behind the subject.
The destination is just the opposite of "near".
```
<D-Motion: back /> // Behind the target
![Image](https://image.gif)
```

### Pierce

It moves from the current location to the specified X coordinate so as to penetrate (pass) the target.
If you do not specify the X coordinate, it will move to the edge of the screen.
```
<D-Motion: pierce/> // Beyond the target
```
![Image](https://image.gif)

As long as you specify the X coordinate, the Y coordinate will be determined automatically. Usually, it requires troublesome calculations, but it is convenient because it does it automatically.
```
<D-Motion: pierce> // Beyond the target
ex = defaultX --100 // Move to the target X coordinate --100
</ D-Motion />
```
![Image](https://image.gif)

It is also recommended to change the position once.
```
<D-Motion: near /> // Approach the target
<D-Motion: pierce> // Beyond the target
delay = 5 // Wait 5 frames
ex = defaultX --100 // Move to the target X coordinate --100
< / D-Motion />
```
![Image](https://image.gif)

Note that this type is not weighted unlike other mobile templates. This is because it is supposed to play animations that pass each other. You need to use wait and delay to get the timing right.

### StepForward

Take one step forward.
```
<D-Motion: stepForward /> // Go one step forward
```
![Image](https://image.gif)

### StepBack

Take a step back.
```
<D-Motion: stepBack/> // One step back
```
![Image](https://image.gif)

### Home

Return to home position.
Similar to the "return" type, but this one simply moves.
```
<D-Motion: near /> // Approach the target
<D-Motion: home /> // Go home
```
![Image](https://image.gif)

### Jump

Move while drawing a parabola.
At that time, a shadow will be displayed at your feet. (It can be erased in the settings.)
```
<D-Motion: jump /> // Jump
```

Basically, use this template in combination with others. The following is an example.
```
<D-Motion: near & jump />
```
![Image](https://image.gif)

```
<D-Motion: crash & jump />
```
![Image](https://image.gif)

Also, the jump height can be changed with "arcY". The initial value is -100.
```
<D-Motion: near & jump> // Jump
arcY = -200 // Parabola with height 200
</ D-Motion>
```
![Image](https://image.gif)

See Basic usage for details.

### Roll

Make one full turn forward (counterclockwise for actors, clockwise for enemies).
```
<D-Motion: roll />
```
![Image](https://image.gif)

This is also basically used in combination with others.
In addition, the number of rotations can be changed by changing the rotation rate "rotation". This is the number of rotations until the movement is completed.
```
<D-Motion: crash & jump & roll > // Collision & jump & rotation
rotation * = 5 // 5 rotation
frame = 10 // Move in 10 frames
</ D-Motion>
<D-Animation /> // Animation
<D- Motion: return /> // Return
```
![Image](https://image.gif)

"* = 5" means the original value x 5.
If you want to rotate in the reverse direction, you can make the value negative.

### Revolve ver1.04

Performs a circumferential movement.
Unlike the Dynamic Animation template of the same name, Butler returns to its original position.
```
<D-Motion: revolve />
```
![Image](https://image.gif)

By default, it makes one rotation with a radius of 100 pixels.
You can change the radius with "radiusX" and "radiusY", and change the rotation angle with "radX" and "radY".
```
<D-Motion: target & revolve > // Revolve the target
frame = 20
radiusX * = 1.5 // Radius in the X direction (150 pixels)
radiusY * = 0.75 // Radius in the Y direction (75 pixels)
radX * = 3 // Rotation angle in the X direction (3 rotations)
radY * = 3 // Rotation angle in the Y direction (3 rotations)
</ D-Motion>
<D-Animation /> // Animation
```
![Image](https://image.gif)

Similarly, "* = 3" means the original value x 3.

Head ver1.09

Move towards the subject's head.
In RPG Maker MZ, the function to change the position of the animation to "overhead" or "foot" has disappeared. It is an alternative function.
```
<D-Motion: crash & jump & head /> // Jump above the target
<D-Animation: head /> // Animation overhead
<D-Motion: return /> // Return
```
![Image](https://image.gif)

### Foot ver1.09

Move towards the target's feet.
```
<D-Motion: near & foot /> // Approaching the target's feet
<D-Animation: foot /> // Animation at the feet
<D-Motion: return /> // Return
```
![Image](https://image.gif)

＞ Return to
DynamicMotion MZ Plugin ＞Return to DynamicMotion Plugin ＞ Return to
RPG Maker MZ & MV Table of Contents