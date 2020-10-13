# DynamicMotion Acting template [RPG Maker MV plug-in]

This page is part of the description of the Dynamic Motion plug-in .

I will introduce acting templates.
There is some overlap with the basic usage page.
However, this is just a brief explanation. Please see there for details.

### Attack
Swing the equipped weapon.
```
<D-Motion:attack/> // 武器振り
<D-Animation/> // アニメーション
```
![Image](https://image.gif)

By the way, <D-Animation /> can be omitted, but in that case, the animation will be played after the weapon swing is completed.

If you specify the weaponId, you can also change the display of the weapon.
Also for creating special techniques such as magic swords.
```
<D-Motion:attack> // 武器振り
weaponId = 2 // id = 2（斧）
</D-Motion>
<D-Animation/> // アニメーション
```
![Image](https://image.gif)


### Attack R (attackR)

Plays the attack motion in reverse.
R stands for reverse.
```
<D-Motion:attackR/> // 武器振り（逆）
<D-Animation/> // アニメーション
```
![Image](https://image.gif)

For example, if you use a sword, it feels like you're swinging it up ...
Depending on the graphics, it may look better.

### Attack 0 / Attack 1/ Attack 2

Each poses with the attack motion stopped in a specific pattern.
The pattern is in the order of 0 → 1 → 2 motion.
```
<D-Motion:attack2/> // 攻撃パターン2
<D-Animation/> // アニメーション
```
![Image](https://image.gif)

If you combine this with the weapon graphic settings, you may find a way to use it.

### Thrust

Perform the thrust motion with your bare hands.
As it is, it seems that it can be used for bare hand skills.
```
<D-Motion:thrust/> // 突き
<D-Animation/> // アニメーション
```
![Image](https://image.gif)


### Swing

Make a swing motion with your bare hands.
How about a throwing technique?
```
<D-Motion:swing/> // 振り
<D-Animation:shot/> // アニメーションを飛ばす
```
![Image](https://image.gif)


### Missile

Perform the motion of the missile with your bare hands.
…… Hmm, what can I use it for?
Assuming a bow etc., it seems that the motion is such that the left hand protrudes forward. One-two punch ...?
We will leave the usage to you.
```
<D-Motion:missile/> // 飛び道具
<D-Animation:shot/> // アニメーションを飛ばす
```
![Image](https://image.gif)


### Magic (spell)

Performs the motion when the magic skill is activated.
When a motion is specified with this plug-in, the activation motion will not be taken.
Specify this if required.
```
<D-Motion:spell/> // 魔法モーション
<D-Animation:spell/> // 発動アニメーション
<D-Animation/> // 攻撃アニメーション
```
![Image](https://image.gif)

I tried to set it with the activation animation.
The size and transparency of the activation animation have been adjusted for easy viewing.

### Skill

Performs the motion when the general-purpose skill is activated.
When a motion is specified with this plug-in, the activation motion will not be taken.
Specify this if required.
```
<D-Motion:skill/> // スキルモーション
```
![Image](https://image.gif)