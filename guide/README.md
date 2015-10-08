Guide to Programming with Music Blocks
======================================

Music Blocks is a programming environment for children interested in
music and graphics. It expands upon Turtle Blocks in that it has a
collection of features relating to pitch and rhythm.

The Turtle Blocks guide is a good place to start learning about the
basics. In this guide, we illustrate the music features walking the
reader through numerous examples.

Getting Started
---------------

Music Blocks is designed to run in a browser. Most of the development
has been done in Chrome, but it should also work in Firefox (although
you may need to disable hardware acceleration). You can run it from
the [github
repo](http://rawgit.com/walterbender/musicblocks/master/index.html) or
github io](http://walterbender.github.io/musicblocks) or by
downloading a copy of the code and running directly from the file
system of your computer.

For more details on how to use Music Blocks, see [Using Music
Blocks](http://github.com/walterbender/musicblocks/tree/master/documentation)
and for more details on how to use Turtle Blocks, see [Using Turtle
Blocks
JS](http://github.com/walterbender/turtleblocksjs/tree/master/documentation).

ABOUT THIS GUIDE
----------------

Many of the examples given in the guide have links to code you can
run. Look for RUN LIVE links that will take you to
http://turtle.sugarlabs.org.

THE GRAPHICAL NOTATION MATRIX
-----------------------------

<img src='https://rawgithub.com/walterbender/musicblocks/master/guide/matrix1.svg'</img>

Once you've launched Music Blocks in your browser, start by clicking
on the Graphical-notation Matrix that appears in the middle of the
screen. (For the moment, ignore the Start block.) You'll see a grid
organized vertically by pitch and horizontally by rhythm.

<img src='https://rawgithub.com/walterbender/musicblocks/master/guide/matrix2.svg'</img>

Because the matrix had three pitch blocks, you see three rows, one for
each pitch. (A fourth row at the bottom is used for specifying the
rhythms associated with each note.)

Because there is just one Rhythm block, which specifies three quarter
notes, there are just three columns for selecting notes.

<img src='https://rawgithub.com/walterbender/musicblocks/master/guide/matrix2x.svg'</img>

By clicking on individual cells in the grid, you should hear
individual notes (or chords if you click on more than one cell in a
column). In the figure, three quarter notes are selected (black
cells). First Re 4 (D4), followed by Mi 4 (E4), followed by Sol 4
(G4).

<img
src='https://rawgithub.com/walterbender/musicblocks/master/header-icons/play-button.svg'
height="36"</img> If you click on the Play button (found in the top
row of the grid), you will hear a sequence of notes played (from left
to right): D4 E4 G4.

<img
src='https://rawgithub.com/walterbender/musicblocks/master/header-icons/download.svg'
height="36"</img> Once you have a group of notes (a "chunk") that you like, click on the
Save button (just to the right of the Play button). This will create a
stack of blocks that can used to play these same notes
programtically. (More on that below.)

You can rearrange the selected notes in the grid and safe other chunks
as well.

<img
src='https://rawgithub.com/walterbender/musicblocks/master/header-icons/close-button.svg' height="36"</img> Or hide the grid by clicking on the Close button (the
right-most button in the top row of the grid.)

<img
src='https://rawgithub.com/walterbender/musicblocks/master/header-icons/erase-button.svg' height="36"</img> There is also an Erase
button that will clear the grid.

Don't worry. You can reopen the grid at anytime and since you can
define as many chunks as you want, feel free to experiment.

<img src='https://rawgithub.com/walterbender/musicblocks/master/guide/matrix3.svg'</img>

The chunk created when you click on the matrix is a stack of
blocks. The blocks are nested: an Action block contains three Note
blocks, each of which contains a Pitch block. The Action block has a
name automatically generated by the matrix, in this case, chunk0. (You
can rename the action by clicking on the name.). Each note has a
duration (in this case 4, which represents a quarter note). Try
putting different numbers in and see (hear) what happens. Each note
block also has a pitch block (if it were a chord, there would be
multiple pitch blocks nested inside the Note block's clamp). Each
pitch block has a pitch name (Re, Mi, and Sol), and a pitch octave; in
this example, the octave is 4 for each pitch. (Try changing the pitch
names and the pitch octaves.)

To play the chuck, simply click on the action block (on the word
action). You should hear the notes play, ordered from top to bottom.

<img src='https://rawgithub.com/walterbender/musicblocks/master/guide/matrix3x.svg'</img>

Every time you create a new stack, Music Blocks creates a new block
specific to that stack. (The new block is found at the bottom of the
Block palette, found on the left edge of the screen.) Clicking on this
block is the same as clicking on your stack. In the example above, the
chunk0 block is inside of a Start block, which ties it to the Run
button in the upper-left corner of the screen (the Rabbit button). Try
clicking on the Run button. Also try the Run Slow button (the Turtle).

About the Pitch Block
---------------------

<img src='https://rawgithub.com/walterbender/turtleblocksjs/master/guide/matrix4.svg'</img>

As we have seen, Pitch blocks are used inside the Graphical-notation
Matrix block to indicate pitches you may want to select. They are also
used inside of Note blocks to specify the pitch(s) to be played when
the Note block is run.

You can plug different values into the Pitch block name and octave
slots. Some examples are shown above. The pitch name in the top Pitch
block is specified using a Solfege block; the pitch name in the middle
Pitch block is specified using a Pitch-name block; the pitch name in
the bottom block is specified using a Text block. The octave is always
specified using a number block and is restricted to whole numbers.

About the Rhythm Block
----------------------

<img src='https://rawgithub.com/walterbender/turtleblocksjs/master/guide/matrix5.svg'</img>

Rhythm blocks are used to generate rhythm patterns in the
Graphical-notation Matrix. The top argument to the Rhythm block is the
number of notes. The bottom argument is the duration of the note. In
the top example above, three columns for quarter notes would be
generated in the grid. In the middle example, one column for an eighth
note would be generated. In the bottom example, seven columns for 16th
notes would be generated.

<img src='https://rawgithub.com/walterbender/turtleblocksjs/master/guide/matrix5x.svg'</img>

<img src='https://rawgithub.com/walterbender/turtleblocksjs/master/guide/matrix5xx.svg'</img>

You can use as many Rhythm blocks as you'd like in side the
Graphical-notation Matrix block. In the above example, two Rhythm
blocks are used, resulting in three quarter notes and six eighth
notes.

Creating Tuplets
----------------

<img src='https://rawgithub.com/walterbender/turtleblocksjs/master/guide/matrix6.svg'</img>

<img src='https://rawgithub.com/walterbender/turtleblocksjs/master/guide/matrix6x.svg'</img>

Tuplets are a collection of notes that get scaled to a specific
duration. Using tuplets makes it easy to create groups of notes that
are not based on a power of 2. In the example above, three quarter
notes -- defined in the Rhythm block -- are played in the time of a
single quarter note. The result is three twelfth notes.

You can mix and match Rhythm blocks and Tuplets when defining your
grid.

Using individual notes in the matrix
------------------------------------

<img src='https://rawgithub.com/walterbender/turtleblocksjs/master/guide/matrix7.svg'</img>

You can also use individual notes when defining the grid.

PROGRAMMING WITH MUSIC
----------------------

The remainder of this guide discusses how to use the chunks created by
the Graphical-notation Matrix when programming (You can also program
with chunks you create and/or modify by hand).

1. A chunck of notes
--------------------

<img src='https://rawgithub.com/walterbender/turtleblocksjs/master/guide/matrix3.svg'</img>

There are several ways to play a chunk...
