RARA Forklift Kit v1.1.0 (forklift and pallets)

A drivable forklift and pallets you can really lift and carry (10,000 / 50,000 / 100,000 ticket cartons). Drop them into any
VRChat world.


Requirements

- Unity 2022.3 (a VRChat world project)
- VRChat SDK - Worlds 3.10.5 (tested); it uses the UdonSharp that comes with the SDK
- A VRCWorld (VRC Scene Descriptor) in the scene
- No TextMeshPro or other assets needed


Setup

1. Import RARA_ForkliftKit_v1.1.0.unitypackage (it goes to Assets/RARA/ForkliftKit).
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


Updating from v1.0.0

1. Import RARA_ForkliftKit_v1.1.0.unitypackage as usual (it replaces the old files).
2. The RARA_Forklift prefabs already in your scenes get the new dash keys ([▲ Up], [▼ Down], [Horn]) by themselves.
   Only an unpacked forklift does not: place the prefab again. Tools > RARA Forklift Kit > Check the open scene names it
   ("an older dash").
3. What changes for players and for you:
   - The desktop horn is H or B (the left click now presses the dash keys).
   - A driver who does nothing for 5 minutes is taken out of the seat ("Seat Idle Seconds" on RARA_Forklift; 0 = never).
   - The SDK may add network IDs for the new keys at the next upload. That is expected.


Controls

Get in: click the forklift (VR: trigger, phone: tap).

Desktop
  W / S       forward / back
  A / D       steer
  E / Q       forks up / down (or [▲] / [▼] on the dash)
  Up / Down   seat height
  H or B      horn
  Hold X      back to the start position
  Space       get out
  Click a dash key to press it

VR
  Left stick                          drive
  Right stick up / down               forks up / down
  Right grip + right stick up / down  seat height
  Trigger                             horn
  Jump                                get out
  Dash keys: press them with a finger, or put the line from your hand on one (it lights up) and pull the trigger

Phone / tablet
  Stick              drive
  [▲ Up] / [▼ Down]  forks: each press moves them to the next stop (floor, 0.20 m, 0.90 m, the top)
  [Horn]             horn
  [Respawn]          back to the start position
  Jump               get out

The dash keys
  Right: [Respawn] and [▲ Up] / [▼ Down]
  Left:  [EN] / [日本語] (the dash language; it starts in your VRChat language) and [Horn]
  [▲] / [▼] move the forks to the next stop; press again while they move for the stop after it. E / Q or the stick stops the move.


Lifting a pallet

1. Drive the forks straight into a pallet with the forks at floor height. The dash says "Forks lined up" when they are.
2. Lift the forks a little: the pallet is on (one press of [▲] stops right at 0.20 m).
3. Carry it, then lower the forks all the way to set it down (anywhere flat and clear).
Any of the four sides works. It can't be set down on a slope or on top of something.


How it behaves

- One driver per forklift. Others see it move smoothly; late joiners see everything where it is.
- It never pushes or moves players: it slows down near people and stops in front of them.
- It stops at walls and objects. It climbs steps up to 12 cm and slopes up to 14 degrees.
- When the driver leaves the instance, the forklift (and the pallet on its forks) goes back to the start position.
- A driver who does nothing for a while gets a warning on the dash a minute before and is then taken out of the seat
  (5 minutes by default).
- The seat height is saved per player (PlayerData key "rara_fk_seat").


Layers

By default it bumps into and drives on the Default and Environment layers. If your floors or walls use other layers, add them
to "Obstacle Layers" (what it bumps into) and "Ground Layers" (what it drives on) on RARA_Forklift and on the pallets.


Settings (RARA_Forklift)

- Idle Return Seconds: after that long without a driver it returns to its start (0 = never)
- Seat Idle Seconds / Seat Warn Seconds: how long a seated driver may do nothing before being taken out, and the warning (0 = never)
- Fork Carry / Fork Mid: where [▲] / [▼] stop (0.20 m and 0.90 m by default)
- Typing Fields: if your world has text input fields, list them here; while one is typed into, E Q X H B, the arrows and
  Space do nothing to the forklift
- Pad Log: writes every dash key press to VRChat's log (output_log), for finding out why a key does not press


FAQ

Q. I can't drive / it doesn't move.
A. Check that the floor's collider is on one of the Ground Layers (Tools > RARA Forklift Kit > Check the open scene).

Q. It keeps stopping.
A. Something is in front, a step is higher than 12 cm, or the slope is too steep. The dash says why. If the forks hit the floor,
   lift them a little.

Q. I'm stuck.
A. Hold X (VR and phones: [Respawn] on the dash) to go back to the start position.

Q. A pallet won't lift.
A. Lower the forks to the floor and drive them all the way in, straight, from one side of the pallet; then lift.

Q. A dash key does not press.
A. Desktop: put the middle of the screen on the key and click. VR: press it with a finger, or put the line from your hand on it
   and pull the trigger. If it still does not, turn on Pad Log and send the [RARA FK][PAD] lines of the log to the author.

Q. How do I put everything back?
A. Place a RARA_ForkliftReturnButton: anyone can press it (forklifts in use stay).

Q. Can it go back by itself?
A. Set "Idle Return Seconds" on RARA_Forklift: after that long without a driver it returns to its start (0 = never).


Changes

v1.1.0 (2026-10-21)
- New dash keys: [▲ Up] / [▼ Down] (each press: the next fork stop) and [Horn]. Phones can now lift and honk.
- The dash keys press reliably in VRChat. Desktop: the key under the click is pressed even when VRChat's own Interact does not
  arrive. VR: press with a finger, or aim the line from your hand (a beam, a dot and a lit key show where) and pull the
  trigger. One press is never taken twice.
- Desktop horn is H or B (the click presses keys). VR: the trigger is the horn when no key is aimed at.
- Idle driver timer (5 minutes by default, with a warning a minute before).
- Optional typing guard (Typing Fields); Ctrl + H / B does not honk.
- Broken synced values (NaN and the like) from another client can no longer upset a forklift or a pallet.
- Less work per frame while pushing against a wall and with many forklifts and pallets.
- While seated, your own forklift's boarding box and Interact are off (they no longer get in the way of the dash keys).

v1.0.0 (2026-10-09)
- First release.


License

See LICENSE.txt. The models, textures and sounds are original. The text font is a subset of Noto Sans JP (SIL Open Font License).

RARA
