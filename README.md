# Waterbender!

This is a touchdesigner + LiDAR interactive project that turns any surface into an interactive playground to train epic waterbending skills.

![Website_Image3 copy](https://github.com/user-attachments/assets/00979c08-8385-493c-b9b8-f73b25c604ce)



# Process
***

## Goal

The goal of this project was to make a magical experience inspired by Avatar the Last Airbender where the audience used nothing but their bodies to control digital "water". I wanted the experience to have a tactile feel to it, and for the first iteration, it had to be adaptable to different spaces and use as lightweight a setup as possible. 

## Tech Decisions

So, given those parameters, I chose a triad of tech that was easy to set up, easy to debug, and invisible to the audience. Here's what I ended up using:

1. Projector - throws light onto any surface, portable, tiny, and ethereal
2. LiDAR - small laser-based piece of tech that can track motion even in very low light, and that can be placed very far away from the audience
3. Touchdesigner running on a laptop - ethereal, real-time graphics programme with good community plugin support for the LiDAR model I was using

![Projection](https://github.com/user-attachments/assets/851db10d-f865-41b1-87e5-cd8bfb38b2fd)


## Building
***

### Testbenching - The Process of Building Components Individually

I started out by building a few seperate projects in touchdesigner with tutorials I liked the look and feel of. Building components individually is helpful because it lets you figure out in detail how each one of them works. Once you figure that out, it's much easier to integrate them all and to debug them in a series of more and more complex testbenches. Also, never get rid of your testbenches - they're handy for debugging throughout the entire process.

| LiDAR 	|  Fluid Simulation  	|
|---	|---	|
|![LiDARTest](https://github.com/user-attachments/assets/da5a4f06-2a4e-4b0e-bf23-55450edd1a72) |<img src="https://github.com/user-attachments/assets/2f061058-8d52-4f25-ac67-d7da9c4cdf89"> |
|[Lake Heckaman's Great LiDAR tutorial](https://www.youtube.com/watch?v=fAvF2niosNA&t=0s) | [Fluid Simulation by Three Dashes](https://www.youtube.com/watch?v=2k6H5Qa_fCE) |

When working with Touchdesigner, modular builds like these are incredibly useful because they let you take parts from different projects and combine them into one project, all while still being able to debug the components individually. This is what the project looks like from above:

| Component-Based Architecture	|
|---	
| ![FromAbove](https://github.com/user-attachments/assets/01ad7e85-854e-4970-9721-0f795d972402)|


***

### Integrating and Robust Project Design

Integrating is relatively easy on these kinds of projects. Because one of the sketches is already mouse-enabled and the other one is modelling a different kind of input (LiDAR instead of mouse) all you need to do is swap the inputs from mouse to LiDAR.

| Original | Replacing the Mouse with LiDAR |
|---	| ---	|
| ![Screenshot 2024-11-18 at 23 19 25](https://github.com/user-attachments/assets/7eecc386-3807-4313-ae1a-c240e35bca55) | ![Screenshot 2024-11-18 at 23 19 252](https://github.com/user-attachments/assets/8a18510c-5b49-4789-9d05-00d2e7a841d7) |

The second part of the integration is maintaining good project structure. Lake Heckaman talks a lot about this in his tutorials, and for a good reason - if you can make a project that is built robustly, everything gets so much easier. I won't go into it here, but check out the Immersive Interactive HQ and Lake Heckaman's tutorials for more on this.

***

### Debugging

All good projects are required to come with bugs (I don't make the rules) so here are a few of the ones I encountered and how I solved them:

| Persistence of Blob Tracking	| | |
|---	|---	|---	|
|![LidarTest](https://github.com/user-attachments/assets/55733cac-68de-41cc-b155-2859dee36579) |![Screenshot 2024-11-18 at 23 31 252](https://github.com/user-attachments/assets/e7026759-7c71-460e-ac18-e775eca308ed) | ![Screenshot 2024-11-18 at 23 31 25](https://github.com/user-attachments/assets/86ee505e-7d00-4589-9cae-1867bcc14c44)|
| This project uses Touchdesigner's built-in blob functionality (that's me testing how it works with some gift wrapping paper (left)).| But even after thresholding the LiDAR readings (middle), the blobs were too feint to be reliably tracked. | So I had to go in and adjust these settings under the blob tracking component (Right). |


| Onsite LiDAR Not Working 	|
|---	|
| Cue the dramatic music. When I got on site to test the installation, the LiDAR had stopped working. To fix it, I did this: |
| 1. Check the hardware. Is it working, are the wires broken? |
| 2. Check the software. Is the data coming through? Can you see the simulation? Go into the LiDAR testbenching file to check this.|
| 3. Check the point of integration. Is the data from the LiDAR getting through to the visual part of the project? | 
| 4. Check the vision. Is the range of the LiDAR compatible with the range you need to input for the project to be interactive? This turned out to be the problem for me. To fix it, I had to change the way I was cropping the field of vision for the LiDAR and change how the project was mapped onto the wall |

***

## What I Learned

Overall, I'm very happy with how this project turned out and the kinds of reactions I got from the audiences I tested this with. If there's three key lessons learned here, it these:

1. Build modular. It's better and it saves you a headache an a half.
2. Get good footage. I had to reshoot my footage twice because it turned out blurry when I moved it onto my laptop. Test filming equipment and film good footage. You'll be very happy you did, because it shows.
3. For future versions of this, I would definitely try to make the LiDAR more invisible by adding an additional casing on top of it to camoflauge it into the wall.




