![](https://blinkylights.ninja/wp-content/uploads/2015/06/clouds1-e1435536402265.png)

# 2015 Queercon 12 - DEF CON 23

For the 2015 Queercon, we’ve tried to build on the successes and learning of the last two years.  We decided to continue the trip down Nostalgia Ave and pair it with the interactivity so craved by the users by capitalizing on one of the most love and reviled pieces of technology from our mutual past: the Tamagotchi.  Few pieces of technology can make so many people feel such mixed emotions.  Naturally, we set out to make something that resembled Tamagotchi, but was still a Queercon badge: bright, blinky, unusual, and eye catching.

The user interacts with the badge via the three buttons on the face, which control the menus and interactions with a pseudo-random character shown on a 0.96″ SMT OLED display.  Five high power RGB LEDs mounted on the edge of the board provide additional feedback for actions and help to indicate the “mood” of the character.  The left and right buttons almost always scroll options to the left and right.  The middle button acts as a “soft key” whose function is indicated on the bottom of the screen.

![Black and white QC12 badges](https://blinkylights.ninja/wp-content/uploads/2015/08/dsc_3067-edit.jpg)

As with previous years, badges can interact with each other via a 915MHz HopeRF radio module, as per our apparent norm.  This year, however, explicit pairing between badges is accomplished via menu options and the radio, rather than the IR module of last year.  The brains of the operation comes from a MSP430FR59, with 64K of FRAM to avoid some of the memory problems of last year.  An additional flash chip was included, but not used.

In addition to the classic egg shape, the three buttons, and the screen, we decided we should try out a stacked board.  We had many reasons for doing this, chief among which is that I’d never done anything like that before.  However, the idea of mounting powerful LEDs on the back of the board and having them shine out from between the two boards seemed like it could create a really powerful effect.  An added bonus was by sandwiching the batteries between the two boards this gives the badge a much more packaged and complete look.  The two boards are connected via 0.875″ partially (single side) removable standoffs and a 1.25″, 14-pin ribbon cable.

Learning from mistakes of the past, board power is provided by two AA (R8 or Size 15, for our international friends) batteries feeding two boost regulators, one for the 3.3V and one for the 4.1V display power.  In the past we’ve always been right on the edge of what a switching or LDO regulator can handle when the batteries get low.  By switching to a full boost system we are much closer to the ideal operating range of the regulator, though a bit short of watt-hours. Also, this year marks the first design to have a power switch of sorts.  Battery power is fed into the ribbon cable such that if the cable isn’t plugged into both boards, no component of the system will power up.  Fun little trick, if i do say so myself!

## Software

Each badge had a character composed of different head, feet, and bodies compiled from a common pool. Every badge had only one other badge with the same character (their “twin”), but would share elements with others. Organizer badges had custom built characters and also were built in matte black.

The badges communicated with nearby badges via the 915MHz network, indicating the presence of other badges both by flashing the LEDs faster and showing a count in the menu. The badges kept track of which other badges (based on name and unique ID) it had seen, explicitly “friended”, and been around the most. Friending was simply a menu option that allowed two badges to explicitly pair, rather than the passive “seen” pairing.

Other features included the ability to “play” with other badges (basically just make their character dance and lower his mood a bit) and, after the feature was unlocked, have other badges flash the LEDs in the colors of your chosen flag. Flag options were various, but included the rainbow, bi, trans, ally, leather, and bear flags. Titles were awarded for doing certain things like attending events of friending all the organizer badges as well. Cheat codes were available too.

## Supporting Hardware

![Prototype](https://blinkylights.ninja/wp-content/uploads/2015/08/2015-07-21-20-25-31.jpg)

We also had many, many support boards this year.  We started in late 2014 with a display development board to help us choose displays.  We also created a tester board to test the ribbon cables, and this year created a completely custom basestation, which handled check-ins and flag unlocking, that included some… special hardware.

## Design Challenges

Electrically, the major challenges with the badge were actually mechanical, which is counter-intuitive.  The board shape, an egg, was outside of my drafting capabilities and well outside the board design program’s.  Untimely a CAD import of the shape was used to produce the board outline.

Additional complications came when it went to produce the board.  The complex shape meant complex routing (or rout) to de-panelize.  Having never manually done… any of that… the task was quite daunting, not to mention difficult to google due to mechanical and electrical routing both being called “routing”.  In the end the vendor coordinated the routing for me.

Lastly, connecting the boards together was surprisingly hard.  In my mind, initially, I was going to use long, standard headers and have the two boards be connected to each other only by the connecting pins. Absurdly, this did not work out.  The selection of “long” male or female headers is very small and very expensive.  Even connectors specifically designed for the task were either too short, too, long, or too expensive.  We are working on a budget here!  Additionally the thought of having to manufacture production quantity of ribbon cables by hand sounded absurd.  Then again, so did breaking apart 80-pin male headers to suit our needs.

We ended up with the ribbon cable because it was by far the cheapest option that provided everything we needed.  Keystone, who we have long used for our battery packs, made a good line of snap-in plastic standoffs with which we could cheaply connect and support the two boards.  Thus the QC12 badge was born!

![Assembly](https://blinkylights.ninja/wp-content/uploads/2015/08/2015-07-21-21-20-29.jpg)

## Field Issues

Overall, this year was much less of a shit-show than the last two.  The major issues seen were crushed displays, glue failure on displays, and issues with the ribbon cables.  A few software bugs were present, but could mostly be solved by a power cycle.

We did have an issue where the displays would glitch out and get very, very hot.  In most cases a power cycle solved the problem… for some reason.  In at least once case this caused the display to physically self destruct.  We assume this is a problem with the controller built into the display.

Overall a pretty stress free year!

## Successes

We had one early success with the badge: 5% initial failure rate with 86% successfully reworked.  Which is to say we had exactly one badge that could not be reworked.  One.  Compared at a staggering 75% failure rate and tens of badges unrecoverable last year, that is a huge success.  Against all odds this is with our same board vendor too.  The key here was clear communication with the vendor about our troubles last year, improvements in the boards being “designed for manufacturability”, and reduced component count.

Overall at the con, the badges went over well.  Many badge holders reported being stopped in the halls and asked about the badge.  As always, they were in high demand but managed to strike a balance between availability and exclusivity.

![Panelized Boards](https://blinkylights.ninja/wp-content/uploads/2015/08/34934-2_1024.png)

## Press

We actually got interviewed by a reporter… or someone posing as one!  I will post a link when the article is posed. UPDATE: Despite interviewing the badge creators specifically, the aforementioned article in the Washington Blade didn’t really include any info on the badge.  Pity.

Hackaday also did an excellent [write-up of all of the “elite” badges of Defcon](http://hackaday.com/2015/08/10/all-the-unofficial-electronic-badges-of-def-con/), in which we were included.  It is a touch light on details but was nice to be included!  I added some info in the comments section too.  For the record, we do not technically sell the badges, but do reward high dollar donors with a guaranteed badge.

[Violet Blue](http://www.engadget.com/2015/08/14/def-con-23-pr-stunts-and-hackers/) over at Engadget also did an awesome, if somewhat jaded, write-up of Defcon in general, which included a lot of nice things about Queercon and our badge.

[Luna Lindsey](http://www.lunalindsey.com/2015/08/defcon-23-putting-confidence-in-con.html) did another great write up on Defcon, Queercon, and the Queercon badge!  As usual I am totally flattered.  Honestly her write up of the software features is better than mine.  Also she has all of the cheats posted over there, as well as how to enter them, so well worth a visit!

> “And the badge. Oh this badge. Last year’s QC badge astounded as a feat of modern engineering, but this year’s topped even that!” -Luna

We also had a ton of tweets and facebook posts about the badges, which was really cool to see.

![lit up badges](https://i0.wp.com/blinkylights.ninja/wp-content/uploads/2015/08/2015-08-08-21-24-47.jpg)
