RARA Forklift Kit v1.0.0 (forklift and pallets)

A drivable forklift and pallets you can really lift and carry (10,000 / 50,000 / 100,000 ticket cartons). Drop them into any
VRChat world.


Requirements

- Unity 2022.3 (a VRChat world project)
- VRChat SDK - Worlds 3.10.5 (tested); it uses the UdonSharp that comes with the SDK
- A VRCWorld (VRC Scene Descriptor) in the scene
- No TextMeshPro or other assets needed


Setup

1. Import RARA_ForkliftKit_v1.0.0.unitypackage (it goes to Assets/RARA/ForkliftKit).
2. Drop what you like from Assets/RARA/ForkliftKit/Prefabs into your scene:
   - RARA_Forklift: the drivable forklift (as many as you like)
   - RARA_Pallet_10k / 50k / 100k: pallets of the RARA lottery-ticket cartons
   - RARA_Pallet_10k_Plain / 50k_Plain / 100k_Plain: plain cardboard pallets
   - RARA_ForkliftReturnButton: a button that brings forklifts and pallets back to where you placed them (optional)
3. Put them on the floor. Leave about 4 m free in front of a forklift (the way the forks point).
4. Upload as usual. The forklifts and pallets are linked to each other automatically on Play, on build and on scene save
   (by hand: Tools > RARA Forklift Kit > Link forklifts and pallets in the open scene).

Tools > RARA Forklift Kit > Check the open scene reports what it finds. Demo/RARA_FK_Demo.unity is a sample scene with a ramp,
walls and a curb.


Controls

Get in: click the forklift (VR: trigger).

Desktop
  W / S       forward / back
  A / D       steer
  E / Q       forks up / down
  Up / Down   seat height
  Click or H  horn
  Hold X      back to the start position
  Space       get out

VR
  Left stick                          drive
  Right stick up / down               forks up / down
  Right grip + right stick up / down  seat height
  Trigger                             horn
  [Respawn] on the dash               back to the start position
  Jump                                get out

[EN] / [日本語] on the dash switches the language (it starts in your VRChat language).


Lifting a pallet

1. Drive the forks straight into a pallet with the forks at floor height. The dash says "Forks lined up" when they are.
2. Lift the forks a little: the pallet is on.
3. Carry it, then lower the forks all the way to set it down (anywhere flat and clear).
Any of the four sides works. It can't be set down on a slope or on top of something.


How it behaves

- One driver per forklift. Others see it move smoothly; late joiners see everything where it is.
- It never pushes or moves players: it slows down near people and stops in front of them.
- It stops at walls and objects. It climbs steps up to 12 cm and slopes up to 14 degrees.
- When the driver leaves the instance, the forklift (and the pallet on its forks) goes back to the start position.
- The seat height is saved per player (PlayerData key "rara_fk_seat").


Layers

By default it bumps into and drives on the Default and Environment layers. If your floors or walls use other layers, add them
to "Obstacle Layers" (what it bumps into) and "Ground Layers" (what it drives on) on RARA_Forklift and on the pallets.


FAQ

Q. I can't drive / it doesn't move.
A. Check that the floor's collider is on one of the Ground Layers (Tools > RARA Forklift Kit > Check the open scene).

Q. It keeps stopping.
A. Something is in front, a step is higher than 12 cm, or the slope is too steep. The dash says why. If the forks hit the floor,
   lift them a little.

Q. I'm stuck.
A. Hold X (VR: [Respawn] on the dash) to go back to the start position.

Q. A pallet won't lift.
A. Lower the forks to the floor and drive them all the way in, straight, from one side of the pallet; then lift.

Q. How do I put everything back?
A. Place a RARA_ForkliftReturnButton: anyone can press it (forklifts in use stay).

Q. Can it go back by itself?
A. Set "Idle Return Seconds" on RARA_Forklift: after that long without a driver it returns to its start (0 = never).


License

See LICENSE.txt. The models, textures and sounds are original. The text font is a subset of Noto Sans JP (SIL Open Font License).

RARA
