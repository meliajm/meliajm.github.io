---
layout: post
title:      "Up and Atom Lab"
date:       2020-05-14 16:03:44 +0000
permalink:  up_and_atom_lab
---


For my final project, I built a React frontend using javascript and a Rails backend. I incorporated Redux and thunk for manage state across my application and allowed for dispatching of functions in action creators as opposed to only objects, respectively.

Up and Atom Lab is an interactive and educational experience where the goal is to help the user understand fundaments in chemistry including the atoms of the Periodic Table of Elements and ionic and covalent bonding. The target user is high school age or so but anyone is able to learn here.

Let's go over the user experience of Up and Atom Lab. The user can sign up and once authenticated, the user can see the periodic table on the home page. The mouse also changes when it is over an element. The user can click any element on the Periodic Table and see that atom's information and a model of that atom.

The user can head over to Intro and start learning the foundations of chemistry related to an atom and goes through a few lessons by clicking links at the bottom of each lesson. The lessons have interactive features where the user can move the electrons around. The electrons are bound to the atom and the radius of the boundary changes depending on if the electron is closer or farther from the nucleus to explain bonding electrons. The last lessons are mostly visual and interactive where the user can form ionic and covalent bonds with different atoms and a different number of atoms. Examples are bonding sodium and chlorine to form salt and hydrogen and oxygen to form water. Salt here consists of 2 ions while water consists of 3 elements.

To form an ionic bond, the user must move that metallic atom's electron(s) to the non-metallic atom. Each atom starts off with a color in the nucleus and the electrons are the same color. So let's look again at salt, sodium starts of purple and chlorine is green. Once sodium's electron is transferred to chlorine, this purple electron changes colors to chlorine's green. And a similar idea is used for covalent bonding, where both atoms' electrons change colors to a different color to indicate sharing versus transfer.

Right now, the user can also see all other users.

How I built the periodic table: 
I used a javascript package called Konva and I used the react version so it's react-konva to draw a canvas or stage. I broke down the period table into columns and built each one separately. Also note, I used atomic information from the NIH as a json and seeded my database with this information so I would have access to the elements. First, I got each element from a column into an array, so I would have an array of all the elements in the first column and an array for each column. Except for the bottom two rows of the Table. From there, I had to create a rectangle for each atom in the array and space them out properly using the x and y positions on the canvas. My database did not have information on the exact column of each element. That information would have made this process slightly more simplified and I could always add that information to my database. I added also text for the rectangles to label the atom.

Future goals: add audio to listen to text and describe visuals, add sidebar navigation showing which lesson the user is on and if they have completed that lesson (table of contents), add a question form so the user can save all of her questions, add a friend feature.
