There is a memory leak in PlayerModule.**CameraModule** & PlayerModule.CameraModule.ZoomController.**Popper**

What happens?  Each time a player leaves, their player instance is stored in either or both of these two client side core scripts, keeping a reference in client memory. 

For Player1, if for example 50 players have left during their session, that is causing memory leak induced strain on Player1's client.  

Recomended way to source future memory leaks:
Roblox LuauHeap -> UniqueReferences 

Oldschool:
https://github.com/TheNexusAvenger/Pulse
