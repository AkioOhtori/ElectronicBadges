![QC 10 Badge](https://i0.wp.com/blinkylights.ninja/wp-content/uploads/2015/06/dsc_2995-edit.jpg)

# 2013 Queercon 10 - DEF CON 21

Due to drunkness in 2012, 2013 saw the birth of the Queercon 10 badge.  For the celebration of ten years of being the biggest Gender and Sexual Minority (GSM) group at DEF CON, we released our first little badge, of which we are quite proud.

The QC10 badge used at Atmel Atmega microprocessor, TI PWM LED driver, and HopeRF 433 MHz wireless module, and a Maxim 22db fixed gain microphone amplifier to create a colorful, interactive badge.  The had two concentric rings of rainbow LEDs used to indicate badge “score,” indicate when a new badge is seen, and generally just look pretty.  The badge keeps track of how many other badges are in range via the HopeRF module and gets happy any time is sees a new badge in its circle.  A RGB LED inidcates how many badges are in range by beating faster and moving up the rainbow in color, starting with red and ending in purple.

![OG Queercon Badge](https://blinkylights.ninja/wp-content/uploads/2015/06/img_20130718_093932.jpg)

Each badge owner gets “points” for seeing badges and seeing the unique Uber badges. The more unique badges seen the more of the rainbow LEDs light up when displaying this score and Uber score.  There were 10 Uber badges available, one for each member of the organizing team.  These badges were visually distinct as they were constantly using their LEDs to show off.  This increased battery consumption, but was totally worth it.

Badges also had “Party Mode” where the badges would flash the RGB led based on microphone input.  This was triggered by an Uber Badge tapping his/her microphone.  The command was then transmitted to any badge in range of said Uber, and the party would begin!

The badges were handed out for free at the Queercon mixers and events.  They immediately became a thing to have and we ran out quickly, with many, many people unrelated to the group asking for one.  DEF CON participants love shiny.

## Challenges

![Bench testing badges](https://blinkylights.ninja/wp-content/uploads/2015/06/img_20130728_215341.jpg)

The largest challenge of the QC10 badge was getting it done on time.  We did not anticipate the level of work that would go into something like then and were a little (read: very) caught off guard.  That said, I locked myself in my office for a few weeks and got the thing churned out.

Another big problem we faced was my having never worked on a battery powered design.  I specified 3xAAA batteries, which I expected to give me 4.5VDC at all times, and speced a regulator to match.  Yeah no.  Turns out batteries can go as low as 0.75V per cell when they are partially drained.  The result was the badges would work OK until the batteries were removed, but be unable to start back up after a partially depleted set was put in.  This was exacerbated by the use of extremely cheap batteries, which had even worse voltage performance.  We had two field solutions to this: (1) Laptop bag full of batteries.  (2) “Jump starting” the regulator by temporarily shorting the input and output pins.  This was a huge disappointment for the team, but did spawn a number of in jokes and memes, which still live to this day.

Other challenges were mostly software problems, such as the fine line between being able to detect tapping on the microphone and just general interaction with the outside world.  As a result Party Mode became less of a fun interesting feature and more a constant problem.  Additionally, brown-out protection was not enabled by default on the Atmega processor and resulted in many badges losing their identity when the battery voltage got too low.  Unfortunately this had the side effect of making any affected badge assume it was badge 0, which was an Uber badge capable of triggering Party Mode.  The result was a chaos of Party Mode and badge reflashes.

The long term effect of all of this, however, is future Queercon badges have had extremely good battery utilization and life, with our better designs utilizing upwards of 90% of battery charge before shutting down.

## Lessons Learned
* Brownout detect good
* Cheap batteries bad
* Not all switching regulators are created equal
* Begin the design early, prototype often
* Keep track of the BOM

## Success!

One of the thing I did not anticipate and was truly touched by what this badge meant to people.  I thought of it as a fun toy that might score me a few free drinks, but Queercon people saw it in a completely different light. (Names and faces omitted for obvious reasons)

> “The badges were absolute genius in getting people to interact, and I’m looking forward to learning more about how it works in the coming weeks.” -M

![QC10 reactions](https://blinkylights.ninja/wp-content/uploads/2015/06/queercon-win_censored.png)
