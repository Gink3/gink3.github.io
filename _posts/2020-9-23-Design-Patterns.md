---

layout: post
title: Design Patterns

---

## Meta talk
So first off I think I need to make these posts longer in general and cover more in depth topics. I have been looking over some of my original posts and they really don't have
much in the way of substance. I also think the formating needs to be improved so I will try to take more time and format my posts as well.

Starting this week I am going to try for a post about once a week to just talk about my on going projects in my computer science classes and in general what I have been doing in my non programming time.

## Weekly Updates

### 3600 - Principles of Systems Programming
This week I started the first major assignment which focuses on bitwise operations. The goal was to use bitwise operators to implement a few different functions with each member being responsible for 1 function. The functions to choose from were
* Count Leading Zeros
* Endian Swap
* Rotate Right
* Parity

I took the initiative and implemented a basic menu system for the console, that looked like the example below, and setup our projcet with a makefile. 
I chose Count Leading Zeros for my function.

```
Enter the menu option for the operation to perform:
(1) Count Leading Zeroes
(2) Endian Swap
(3) Rotate-right
(4) Parity
(5) EXIT
```

For each function we are given a 32 bit integer to work with in our function. I used the idea that I can shift the number right until it equals zero then subtract the
number of times we shifted from 32. This would give us the number of leading zeros because we effectively count the number of spaces until the largest on bit.
``` 
int clz(int num) {
    int lz = 32;    //zeros possible

    //shifts right until integer is 0
    //decrementing possile zero count 
    while(num!=0) {
        num = num >> 1;
        lz--;
    }

    return lz;
}
```

It took longer than I am willing to admit. My inital attempt I was stuck beating my head for a couple of hours trying to figure out a way to compare the most significant bit. After realizing that it wasnt going to work I took a power nap at school, woke up and decided to look at how the bitwise operators worked. This gave me an idea to use the right shift operator. Another idea now that I think about it is to shift it left until the value of the number is equal or greater to `2147483648` since that would be the most significant bit for a 32 bit ineger.


### Personal Project

This week I decided to finally start building my own roguelike. Right now I have a place holder name `myrl` but I can change that later. The game will be a cool case study of procedural generation and given me hands on experience with python 3 as a Object Oriented language. Up to this point I have only used it as a scripting language for small batch tasks. So far the transition from that mind set has been hard and it is becoming evident that I will have a lot of refactoring to do. Anyways back to the game though, I want it to be a blend of hack n' slash and roguelike. I want to make a fun game with some progress. The best part is with a good procedural system we can do infinite content and leveling. I want the game to be broken and with insane combinations of mechanics. It will have enemy and loot scaling, and ideally some kind of player housing to trick out with loot and trophies from all the adventures to different zones and dungeons.

This will also be a great opportunity to get experience with writing unit tests. There are a lot of objects that will be interacting with each other all with a lot of their own methods. I've never had a good chance to implement these at this level or scale and it should be a lot of fun to work on everything. I am electrified to be able to build something on my own using the high level concepts taught in my college courses.


### Readings

Finally to the title section of this post, I have been struggling with how to design and implement the road map for my roguelike project. I have no experience designing anything of this scale and definetly need to take some time to redesign the steps I want to take. I made the mistake of getting to excited and jumping head first into the projec. I didn't take the time to think everything through and make a solid plan

Currently what I have is the language I want to use and the graphics library, being python and libtcod. Libtcod is able to do graphical output and window management, with some built in functionality for roguelikes.

Reading [this](http://people.cs.ksu.edu/~schmidt/300s05/Lectures/Lecture0.html) article from Kansas State University has been fairly informative. I think I will be using their ideas for flow charts to diagram out the game process as well at the menu system. I did not consider how I want to be process and was kind of developing bricks without realizing which ones I needed.

Next I read [this](https://en.wikibooks.org/wiki/Introduction_to_Computer_Information_Systems/Program_Development#:~:text=Program%20development%20life%20cycle%20(PDLC,implementing%20and%20maintaining%20application%20software "link") which talks about modeling how the data will be stored as well as the methods and function I will need. More specifically it pairs those diagrams with control structures which is what the first article talks about using.

### Music

I am also going to try and talk about what music I have been listening to while either coding or doing homework. Its always changing and I just like to listen to new stuff.
This week I have really been in a country mood, mainly HARDY with his new album `A Rock`, more specifically his new song `BOYFRIEND` which my girlfriend really seems to enjoy. Its about this guy who doesn't want to be her boyfriend anymore and talks about how he wants to propose, which I think is really sweet in a twisted way. Its really clever in the way he talks about simple ideas and that is what HARDY is best at. He has a line in the song that goes
```
I wanna call up your dad
Spend all of my coffee can cash
And ask you, "What's it gon' be?"
Puttin' one knee on the floor
'Cause I don't wanna be your boyfriend anymore
```
and it is so different in the way he doesn't directly state whats happening and has this play on words for proposing. Its just refreshing too see a different take and shows genuine affection for his girlfriend.

In case anyone is interested here is my [country playlist](https://open.spotify.com/playlist/2ZfCjrhMTLq0JLQCNigeV0?si=r3GcBN-fSo6ZlHaH1eLX0g). Side note, I can never remember how to write links in markdown so [this](https://www.markdownguide.org/basic-syntax/) has been a life saver.
Another banger is `Diamond In My Pocket` by Cody Johnson who is more traditional country.