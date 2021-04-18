# RayTracingMazeCppOLC

Simple ray tracing game in C++, originally developed in [Python](https://github.com/FinFetChannel/pytracingMaze). As you may have guessed, things started to get a bit heavy for Python and my poor optimization skills, still, developing the proof of concept with Python was worth it.

## Intro

### Rays

The basic approach is to trace rays of light in the reverse direction, starting from the camera and interacting with the environment, with three basic types of rays:

* Vision rays - Initial ray that shoots from the camera and returns the coordinates where it has hit something
* Reflection rays - Secondary rays that start where the vision ray has hit something and goes in the direction of the light
* Reflection rays - Secondary rays cast when a vision ray hits a reflective surface, the new direction is the reflection of vision ray in relation to the normal vector of the surface, can have several bounces (reflections inside reflections)

### Maps

Maps are defined by grids, with different maps for different features: wall positions, colors, heights, reflectivities, textures and geometry (spheres or prisms). The maps are generated randomly, so each level and each game is a bit different. For that, a random walker algorithm is used, removing some walls from the map while traversing it, giving preference to pre-existing paths carved randomly.

### Game logic

The player starts on one side of the map and has the objective of finding a blue floor patch on the opposite side of the map. At each level the size of map gets bigger, with a total of.

### Inputs

Basic inputs are similar to FPS games, with WASD for movement and mouse for orientation (optionally QERF), the esc key is reserved for quitters.

## Code

The code is a bit messy, following the basic structure:

* Variables initialization
* Level loop
  * Initialize level - OnUserCreate()
  * Game loop - OnUserUpdate()
    *Check inputs  
