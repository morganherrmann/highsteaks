# highsteaks

***HIGH STEAKS***
[VIDEO DEMO](https://drive.google.com/file/d/1AICjJZzCdaS4XFplcKh-Zf61H2xyxHTH/view?usp=sharing)

![Demo](https://drive.google.com/file/d/1lmmcd_J_RvdE8VsRrF_Y4l6SptjsdhLL/view?usp=sharing)

Welcome to High Steaks, a fast-paced VR competition game-- dairy cow versus alien. Set deep in the cornfields, an alien pilots a UFO while its dairy-cow counterpart attempts to reach its only hope at safety-- the rocket launcher. With power ups ranging from energy potion to cow pies, High Steaks provides a chase that’s as comedic as it is thrilling. Will the cow reach the farmhouse and shoot the alien from the sky? Or will the alien beam up a nice steak dinner?


High Steaks is implemented in Unreal Engine intended for use with the Vive Pro 2 VR platform. It requires two players and offers a uniquely asymmetrical gameplay experience.


**===USER GUIDE===**


***INSTRUCTIONS***
### Player 1 (Alien):
Select CREATE ROOM to create a shared Game Session. Once Player 2 (Cow) joins, the cow will be spawned somewhere on the farm. It is your goal to locate, chase, and capture the cow with your tractor beam.

#### CONTROLS
- Use the back trigger on each controller to grab/click.
- Grab the steering wheel and rotate left or right to rotate your ship.
- On the right hand side, grab the throttle handle and push forward to move your ship. Pull the handle pack to stop.
- On the left hand side, there are 2 buttons-- green and pink. Press the pink button to fire trap-bubbles, which, if overlapping the cow, will slow the cow down as long as the cow is in the bubbles.
- Press the green button to activate the tractor beam. The tractor beam will follow your line of sight. Keep the cow player inside the tractorbeam for 4 seconds, and you win the game.
- Make sure to watch your energy meter. It will deplete as you use your stamina and shoot your slow-down bubbles. If it reaches zero, you won’t be able to use these abilities until it recharges.

### Player 2 (Cow):
Select JOIN ROOM once Player 1 (Alien) creates a room. When prompted to join the room, point and click OK. It is your goal to navigate the farm, avoid capture and seek the rocket launcher to shoot the alien out of the sky.

#### CONTROLS
- Hold the thumb pads on each controller. Turn in the direction you wish to move, and move your arms in a walking/jogging cycle in order to advance the cow’s position. You may also move with a single arm.
- Use the back trigger button to grab coins, which become surprise powerups and resources. Once you grab this powerup, press the back trigger to fire in your direction of sight.
- Cow pies will temporarily blind the alien. Energy poison will deplete the alien’s energy, temporarily preventing them from using the tractor beam.
- Once you locate the rocket launcher, grab as you would any other powerup. Aim the rocket as described above, and fire at the UFO using the back trigger button. If you hit the UFO, you win-- otherwise, the rocket will spawn in another location.

#### Win conditions:
- PLAYER 1 (Alien) wins if they lock the cow in the tractor beam for 5 seconds.
- PLAYER 2 (Cow) wins if they hit the alien ship with the rocket.



***GAME SETUP DOCUMENTATION***


**Requirements:**
Vive Pro 2 Headset + Controllers (x2, 1 per player)
SteamVR
HighSteaks.exe (Build from Unreal Engine 5.2)


Complete all calibration steps associated with Vive Pro headset/controller setup.


Note that both players must be connected to the same network in order for the multiplayer aspect of the game to function. This allows both players to join a shared room.


After connecting to SteamVR, each player must run the HighSteaks executable on their machine.


## System Specifications

- **Operating system:** Windows 10 64-bit (Version 20H2)
- **Processor:** Six-Core Xeon E5-2643 @ 3.4GHz.
- **Memory:** 64 GB RAM
- **Internal storage:** 256 GB SSD
- **External Storage:** 2TB SSD.
- **Graphics Card:** NVIDIA GeForce RTX 2080 SUPER+


**MAJOR FEATURES**


## Multiplayer Networking
- Instantiate room
- Room search and join

## Gameplay Mechanics
- Game objects replication system
### Cow Character
- Arm-based locomotion
  - Allows the player to move in their view direction with movement from either one or two arms. Speed is proportional to frequency at which the players swing their arms.
- Item interaction system
  - The cow may reach, grab, and select items spawned within the farm environment. This includes all powerups and the rocket.
- Shooting mechanism
  - Once a powerup/item is obtained, the cow can turn, aim, and fire the powerup in hand. If it collides with the UFO, the effect of this powerup will be applied.
- Basic animation (idle and walk)
  - Animations applied to the rigged cow asset.
### Alien Character
- Steering mechanism
  - A steering wheel was implemented that let the alien player turn the ship by pressing the trigger button and moving the wheel as if they were really driving a car or flying a plane.
- Throttle mechanism
  - A throttle was implemented on the right side of the cockpit which, when pushed forward, would input a movement vector in the direction that the UFO was currently facing. If the throttle was pulled back, the UFO would stop.
- Slow down shooting mechanism
  - A pink button was implemented on the left side of the cockpit which allows the player to shoot a pink ball in the direction that the player is currently facing. Once this ball hit the ground, it would grow into an area of effect that if the cow was in the area of effect, the cow would move slower. This area would fade away after 8 seconds. The shooting costs 30% of the player’s total energy, and so it could be shot multiple, but not infinite times.
- Tractorbeam mechanism
  - A green button was implemented on the left side of the cockpit which, when pressed, would turn on the tractorbeam. The tractorbeam would slowly drain the UFO player’s energy as long as it was on, and so it needed to be used sparingly to make sure it was only used when the cow was in a compromising position. The beam pointed in the direction that the player was facing. If the cow was in the tractorbeam for a couple of seconds, the UFO player would win.

## Powerups/Abilities
### Cow Powerups
- Cow Pie
- Rocket Launcher
- Mana Steal potion
### Alien Powerups
- Slow-Down Bubbles
- Tractor Beam

## Level Design
- Farm layout/design
  - Level map design included various sections of a farm which the cow player can navigate, with a combination of obstacles and open spaces. There are many places to hide on the map, and there is enough room for players to have room to move around in and chase one another. Items are scaled to provide an immersive perspective of the cow on the farm, with the alien player taking the bird’s-eye view.
  - Initial farm included a square layout with static wheat + barn models. Final level (post-beta) introduced new design/textures/layout.

## Animated Assets
- Custom animations added to static assets including campfires, windmills, tractors, and the cow.
- Custom assets - cow pie, billboards
  - Cow pie model and texture created in Maya and imported into game.
  - Alien-warning billboards with custom textures created in-game.

## Randomized Spawn Locations
- To ensure variation in gameplay, the cow spawns at a different location in each round. In addition, powerup and rocket placement is randomized as well. The UFO and rocket are guaranteed to be placed in one of the farther spawn zones from where the cow player spawns, so even though the game has a random start, it will never be too easy for the cow to reach the rocket launcher right away, or too easy for the UFO to beam the cow up right away.



Features implemented since the beta demo are listed in bold. Various features, such as player networking, cow locomotion, and tractor beam, were continuously adjusted/improved throughout the alpha → beta → final versions.


**TECHNICAL ISSUES**


## Known Issues and Solutions

### VIVE
- Due to base station placement, gameplay views are sometimes disconnected/grayed out.
- Headset sometimes failed to connect with SteamVR and/or see base stations, preventing or delaying gameplay.
- SteamVR sometimes froze and crashed--however, this tended to occur unpredictably. When this occurred, it generally required an OS restart.

### Unreal Data Synchronization Problems
- Players transformation data update problems.
  - Initially, we experienced player transformation lag between the server and client. This is because we didn’t notice Unreal has built-in options that allow us to change the data updating rate. Eventually, we increased the refresh rate to make the player's movement smoother on both client and server. (This reminds me that the data update lag also happened when we were doing the AR project using Photon Network Plugin. I assume that is also because we didn’t change (or even notice) the refresh rate of updating data between the server and client).

- Game objects replication problems.
  - This problem happened when we were doing the win/lose condition features. At the beginning, we had no idea why everything was working perfectly when we were testing on the local single-player mode but multiplayer mode. After referring to a number of Unreal official documents, we understood that every game object needs to be replicated from client to server first and then from server to all clients. Eventually, we implemented a lot of custom events to solve the data replication problems.


**PLUGINS/ASSETS**
Low Poly Farm Pack - Provided individual, static farm assets including barns, plants, hills, and props. Animations + Level Layout created manually. https://www.unrealengine.com/marketplace/en-US/product/low-poly-farm-pack?sessionInvalidated=true 
Rigged Little Cow -- https://sketchfab.com/3d-models/rigged-little-cow-4326366e724549ea8cf2369d405481ca 

