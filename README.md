# Mixed-Reality-Construction-Simulation-Capstone-Project
When you're an engineering student at my university, instead of a senior thesis, we do capstone. It's basically a group project you work on for 2 semesters. Mine was a research-based mixed reality project and this was my experience. 
## What was the project about?
The school of construction is wanting to give an alternate, inexpensive way to give building experience to their students. To do this, Computer Science and Informatics students built a virtual playhouse that would allow students to modify it in order to meet the needs of different--often opposing--stakeholders. They are able to order items from a catalog, paint them, drill them, return them, trash them, and move them.<br>
Over the course of an hour, the application records what items they order and return, calculating how much they spend, how much time they spend, the average sustainability score of the objects, and an average fun score. Some of these are shown in the application to the player, others are shown afterward to invite the player to reflect on what they could have done differently. Because this is a research project, the users fill out surveys and the proctor follows a script to keep internal validity.<br>
I was on the developer team, however, there was also a distributor team who was in charge of making the application more accessible so anyone could modify it to fit their needs, even non-programmers. My sponsor was passionate about the idea of the application set up being as easy as a PowerPoint.<br> 
## Tools we used for Mixed Reality:
GitHub - to help collaboration between everyone on my team and everyone on the distributor team and the Ph.D sponsor who was in charge of both teams.<br>
Unity - used to hold assets and modify the application.<br>
Visual Studio - Used for creating/debugging scripts (code--all in C#) enabling objects to act in certain ways.<br>
Hololens 2 - our tool to run the application<br>
Photoshop - I used this for the color picker function<br>
Blender and 3DS Max - used to create or fix models<br>
## What is Mixed Reality?
If Virtual Reality is putting yourself into a virtual space via a headset and augmented reality is putting digital objects into the real world (like in Pokemon Go or Snapchat filters), mixed reality is being able to do both simultaneously. You can have both digital and real-world objects to interact with.<br>
[https://youtu.be/XwOnHqiNAeU] - a demonstration video for Microsoft HoloLens 2<br>
## Did you have previous experience working with Mixed Reality?
No, but this was not my first time working with Unity. The last time I worked on a Unity project was in 2018 for a game development class and I was still a mechanical engineering student. I'd say there was a lot to learn.<br>
The first semester I was doing my internship and my mixed reality capstone project at the same time working a total of about 60 hours a week (although I’d say capstone sometimes took more than that especially near the end). It wasn’t as stressful as I thought it’d be but the second semester was a lot easier since I only had capstone to deal with (and finding a job post-graduation).<br>
## First Semester Experience:
### What did you do for the mixed reality project?
Initially, I showed interest in textures. At our first work session, I made walls around the playhouse with fairly nice-looking brick. So I was tasked with fixing the painting mechanic that wasn't working quite right and I fixed the ability to change the floor. Next semester, we changed how it worked so I had to tweak it further. I also helped populate an array by hand because it was roughly 150 objects, each with its own properties.<br>
That's Not A Lot..
You're right. I had several really good plans and several of them didn't work out. Stubbornly, I wanted to fix it by myself so as not to take away from what my teammates were doing. I learned my lesson doing a few almost all-nighters in a row and didn't do that in the second semester.
So what was your plan?
My first plan was to make sort of a master script that would be assigned to every object and you could tag objects as a paint bucket (and grab the color), wooden objects that you could paint, plastic objects you could order in other colors, and metal objects that could not be painted or ordered in other colors. Some of our models had multiple materials in them you couldn't separate so it didn't work. The idea was to condense 5 scripts into 1 but that failed. Then I had the idea to try and separate out everything so I could get it working in smaller scripts but that didn't work out either.
Here's how my mixed reality painting actually works:
There are 4 scripts for this to work. Two of them act as booleans. One where we can mark an object as a paint bucket, the other to mark an object as paintable. The third script takes care of all the sound effects and honestly, I didn't touch it much. Lastly is our script that runs the show. First, it checks if you have grabbed the paintbrush, then it checks what you’ve collided with. If you’ve collided the paintbrush with something marked as a paint bucket or paintable, it'll respond. If you’re a paint bucket it’ll grab the color, change the end of the paintbrush color, and then if you collide the paintbrush with a paintable thing it’ll make it that color. During the first semester, I made paint buckets with very specific wood texture colors to make this work but I later changed it.
All the paint buckets I made
Results from the morning I got it to work:
 


It may not seem like much but it worked and didn't paint anything it wasn't supposed to. I was super happy.
Second Semester Experience:
Since I took the first semester over the summer, there were about 2 weeks between the first and second semesters. I remember the whole team saying none of us took the time off 🤣. One of the immediate tasks of this semester was to get a baseline version of the mixed reality program working perfectly because our sponsor was going to start doing user testing every day. After that, we made a few major improvements that were nice-to-haves. 
Perfecting the Program To Do List:
Quintuple check the array items for the catalog are correct.
We have a script that keeps track of what you spend and a couple of other things but it didn't keep track if what you returned so we needed to fix it. We also have a laptop interface that tells you how much you spend but if you returned something, it needed to give you money back. It took three of us and a few hours😊
That same script calculates arbituary fun and sustainable scores for every object and my sponsors wanted to change the number of decimals it spits out.
We had new objects to add to the catalog.
Every building-like object is supposed to have screws to aim your drill but we missed a couple.
I expanded painting so that you could do any color you wanted.
I like to describe the voice commands as hard of hearing. Turns out some of the voice commands were just problematic so we slightly changed them to work better. 😉
We started an excel sheet to communicate with the distrubitor team how the scripts work. 
    Cleanup Comand:
When we received feedback from user testing, there was a big problem with losing your tools. The simple solution at the time was to be able to order more of your tools for free but I thought it could be better so I made the cleanup command. When you say “Cleanup”, if your tools are not at their starting position, they will go back to their starting position. I put a workbench there to kinda mark the space and have it make more sense. 
How it works:
So I made copies of the drill and paintbrush, these tools are invisible but in the exact same starting location. The invisible drill has a "drillOpos" tag (drill original position), and the invisible paintbrush has a "paintOpos" tag. In the tools / workbench parent is Cleanup script. From there, the cleanup command just stores the position of the hidden tools, and when you say "cleanup" assigns the position of the visible to the invisible.  
The Tutorial:
My main add-on for the second semester was making a tutorial for our application. Because this was a mixed reality project, you can't really use Unity's built-in user interface features. However, mixed reality comes with a lot of built-in features that you can customize somewhat so that's what I used to make the tutorial.
What's user interface?
User Interface is basically anything you interact with as an end-user. Think menus, buttons, etc. You don't have to code them as an end-user to use them but someone coded their functionality.
Mixed Reality Tutorial Part One: Grab tutorial
Hand coach + instructions
When you start up our application, it starts off a void with a pop can so you can tell the program where your floor is by grabbing it and setting it on the ground. One of the things our Ph.D. student sponsor needed was a better way to teach people how to grab something. Luckily, I found a hand coach built into Hololens that conveniently teaches people to grab stuff in mixed reality. It disappears after you say "set space".
Part Two: Tools tutorial
An important aspect of the mixed reality tutorial is it needed to be reusable so that if you forget, all of the information you need is readily available. One of my solutions to this was to have labels for all of the tools that told you how to use each item. As you move, they turn towards you for better visibility. 
Label for all of your tools and what they do 
However I wanted to do more. In the space, the laptop is quite small, and the text you see initially is fine but I wanted to give the end-user more information. So if you interact with the "???" button you'll see this:
Web browsers 
I call them web browsers because that's what they look like. Each browser can be closed and reopened if this looks too busy but each has a pupose. Below are clearer pictures of each web browser. 
The Right Browser with a full list of voice commands available 
On the right, are your voice commands and what they do. All of the web browsers are titled www.ResourcesYouNeed.com which is not a real website but accurately describes what its purpose is. 

Your receipt
On the left, is your receipt that will tell you everything you've ordered and how much it costs. It updates as you order items. In the picture, I ordered blue paint, a 2x4x1, red stairs, and a yellow firepole as an example. It can comfortably fit around 30 items on this page which is plenty for its current purpose.  
Catalog with slider 
Normally during user testing, our end-users would have access to a physical paper printed catalog of items they can order. I transferred it into the application and put it on this middle web browser with a slider so you can look through all the pages of things you can order. I promise it shows up better in mixed-reality than on my computer. 🙂
Tutorial Task Board 
Lastly, I added a tutorial task board with check boxes you can check off if you need direction. If you don't, you are welcome to play with the playhouse and modify it as you see fit.
Capstone the class
On top of the mixed reality project, capstone had a lecture once a week with assignments. Most of the assignments were SCRUM sprint reports to make sure work was being done every couple of weeks.
