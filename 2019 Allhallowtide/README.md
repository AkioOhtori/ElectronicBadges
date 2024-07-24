![alt text](https://blinkylights.ninja/wp-content/uploads/2019/10/dsc_7842-edit.jpg)

# ALLHALLOWTIDE 2019

In 2019, I found myself with a little time on my hands.  This is almost always a good/bad thing, and in this case it inspired so George, co-creator 
of the Queercon Badge, and I cooked up an “Allhallowtide” badge in the weeks before Halloween. Start to finish the badge took about two weeks, with 
the electrical design going from concept to production in three days, a record turnaround at that time.

The design borrows hardware from at least three QC badges and features two captouch buttons, an Amphenol Rotaconnect for badge-to-badge communication, and five RGB LEDs. Power is provided by a CR123A, which is fed unregulated into the TI MSP430FR2522IPW16. Most components were bench stock from previous badges, which helped keep the cost down.

The badge artwork is an SVG licences from the creator, Michael Hassler, and implemented into Altium using AutoCad Mechanical as an intermediary. The 
back artwork is a mix of the licensed material any my own work. The PCB is white soldermask with black silkscreen and our board house, PCBWay, 
really crushed it on the silk screen. Usually you’d expect some transparency and bleed, but these came out perfect.

Overall cost is about $10 each, excluding bench stock parts. A little high, but given the quick turn around and quality, we’re not complaining! Badges are to be given out at our annual halloween party to encourage conversation/interaction and to look cool.

Functiality is pretty simple.  In idle, the badge just looks cool, cycling through RGB patterns in the crown of flowers.  Upon connection with another badge, both badges display a special pattern at enhanced brightness.  Additionally, the two badges’ heart LED begins to beat.  The color of the heart LED is based on the two badges’ ID and meant to be somewhat unique to the pairing.  The beating stops about about a minute to encourage pairing.  Additionally, pairing with more badges increases the number of patterns available for the roses.  Patterns are switch by pressing the eye button.  Lastly, the nose can be “booped,” causing the rose LEDs to briefly display bright colors, a concept we’ve uhh… “borrowed” from the DC Furs badge.

Overall we’re really happy with how the badge turned out and happy to have it in our design bandoleer.

![badge back](https://i0.wp.com/blinkylights.ninja/wp-content/uploads/2019/10/dsc_7867-edit.jpg)
