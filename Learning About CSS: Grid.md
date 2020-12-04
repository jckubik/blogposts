## Learning About CSS: Grid

In my current project, I'm working on replicating the iPhone calculator on a webpage using JavaScript and CSS. So far, I've started by working on the CSS portion of designing the calculator how I want it to look and creating all the elements needed. 

One of the big challenges here was getting all the buttons to be in the right place, evenly spaced, the same shape, etc. I tried using flexboxes at first but was having trouble achieving the effects that I wanted. I had all the buttons there and they were lined-up next to each other in the proper order, but they were SUPER small and not the same size. One rendition of the code I tried even had the different rows of buttons severely far apart from each other. Basically, flexboxes were not working for me.

After a brief brainstorm on the project with my brother, a software engineer for Twilio, he suggested using grid instead. He thought it would work for what I was doing and gave me a big nudge in the right direction. 

I set up the the buttons like so:

    .buttonContainer {
      padding: 0 0 .5rem 0;
      display: grid;
      gap: .7rem;
      grid-template-columns: repeat(4, 1fr);
    }
    
In this bit of CSS, the "display" sets the div to be a grid container, and then the "grid-template-columns" creates 4 columns with a flex factor of one. The flex factor of 1 sets the space that each button takes up. Since they all have an equal proportion of space they're allowed to flex into, they're the same size. The "gap" references the space between the buttons giving them the separated look seen on the iPhone calculator.

However, you might also notice that on the iPhone version, the "0" button is twice the size of the other buttons. Figuring out how to change just that single button was admittedly a challenge for me, but I eventually came up with this:

    .button0 {
      border-radius: 23% / 50%;
      grid-column: 1 / 3;
    }
    
Here, the single button is referenced using the class "button0". The proper reference was the part that I kept getting wrong here. I was at first trying to use a separate ID for each button and referencing it that way, but that didn't work. Neither did a class of "0". In the latter case, it seemed like the code didn't like trying to reference a class using only an integer. It wasn't until I tried with the current class that I was able to double the size of the "0" button compared to the rest of them. 

Okay cool, I referenced the right thing, but how did I change the size? 

The sizing is done by using "grid-column" which specifies the size and location of grid-column items by referencing specific grid-lines. The grid-lines define the "grid-column-start" and "grid-column-end" of the items within the grid. In this case, it's telling the "button0" to span from grid-line 1 to grid-line 3 - a.k.a. 2 blocks of the grid (1 block would be from grid-line 1 to grid-line 2).

And that concludes my current progress on my CSS journey to a knock-off iPhone calculator. I think using a grid was definitely the way to go. That might change in the future as I keep progressing through the project, but so far it made setting up the buttons the way I wanted ~relatively~ pain-free. I really can't ask for more than that.
