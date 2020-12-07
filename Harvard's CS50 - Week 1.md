## CS50 - Week 1

The second week of CS50, also known as week 1 when you count like a programmer (thanks zero-based indexing!), brought with it a new language - C.

This past week consisted of two main projects written in C:

  - [mario.c](https://github.com/jckubik/CS50/blob/main/mario.c)
  - [credit.c](https://github.com/jckubik/CS50/blob/main/credit.c)
  
  ## Mario.c
  
 With the first program, mario.c, we had to create a way to make stair-like structures that you see in the Mario game by printing #s based on an input of height from 1-8.
 
 The goal was to look something like this with an input of 4:
 
       #  #
      ##  ##
     ###  ###
    ####  ####

Since the input range was from 1-8, then the first order of business was to limit inputs to an integer ranging from 1-8. For this, I just used a do-while loop that kept asking for an input until you gave an acceptable answer for the height.

I then added a for-loop to give me the overall height of the stairs. If you input 8, then my for-loop would run eight times, and so on.

The next challenge was to print the structure correctly. The part that stumped me for a bit was getting a relationship going between the number of layers, the number of hashtags to include on each level, and the correct amount of space. The program also couldn't include extra spaces after the printed structure. They wanted it to be efficient!

I eventually figured out how to print the right amount of spaces and tags using for-loops that played off the height input and the current layer to be printed. I also added an if statement to check whether or not more spaces should be added (ie. If you just printed the second structure, then no more spaces).

  ## Credit.c
  
The next program we had to work on was one that could verify a credit card number. Thought all those numbers were random? Well, turns out that's not the case at all. Those 13-16 digit numbers are actually based on a mathematic formula - Luhn's Algorithm.

Here are the steps that we had to mimic with our code:

> 1. Multiply every other digit by 2, starting with the number’s second-to-last digit, and then add those products’ digits together.
> 2. Add the sum to the sum of the digits that weren’t multiplied by 2.
> 3. If the total’s last digit is 0 (or, put more formally, if the total modulo 10 is congruent to 0), the number is valid!

However, we first had to let the user input an integer for us to verify. Which in this case was actually a 'long' rather than an integer variable. The 16 digits that were possible were too long to be stored as a regular integer (16 bits compared to 32 bits in a long).

This length actually represented the first task: only accept a long with a length from 13 to 16. It didn't make sense to send a number through the program that wasn't even long enough to be a credit card number. 

I then took the number and ran it against Luhn's Algorithm. If it passed the checksum, then the next step was to figure out which type of card it was. This was done by looking at the number length and the first two digits, so I had to add a way to track the length and isolate the first two digits for analysis.

Once the program has those values, it then runs them through a round of if-statements to decide which type of card number was given.

  ## Week in Review
  
Overall, I had a lot of fun going through these two challenges. For both, the entire process felt like a giant puzzle for me to solve. Yes, I had times where I got frustrated, *but* I persevered and figured out a way to make the code work which felt amazing.

The really big annoying thing for me for the projects was the challenge of switching from coding in JavaScript to coding with C. The languages are very different. JavaScript is much more intuitive and user friendly. For instance, when creating a variable in C you had to first define what type of data was to be stored in the variable.

    int x = 1234;
    long cc = 4003600000000014;

Whereas JavaScript is just smart enough to know what type of value is being stored and you can just go ahead and declare the variable.

    let x = 1234;
    let cc = 4003600000000014;
    
This made it much more tedious and frustrating at points, but I can also see why C is taught first. You have to know more about what's going on, unlike JavaScript that somewhat hides what's actually going on behind the scenes. 

I think I learned a lot from the projects and I can't wait to dig into next week's projects soon.
