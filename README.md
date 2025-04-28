There is a memory leak in PlayerModule.**CameraModule** & PlayerModule.CameraModule.ZoomController.**Popper**

When does this happen?
In an empty baseplate, this does not happen, tested in both studio and live publish.
In larger projects, this might be happening to your game.
In-between? Where does this start? Is there any barebones pre-rec before this is 100% reproducable? Unknown.

What happens?  Each time a player leaves, their player instance is stored in either or both of these two client side core scripts, keeping a reference in client memory. 

For Player1, if for example 50 players have left during their session, that is causing memory leak induced strain on Player1's client.  

Recomended way to source future memory leaks:
Roblox LuauHeap -> UniqueReferences 

Oldschool:
https://github.com/TheNexusAvenger/Pulse
