# The Amanuensis
The Amanuensis is an automated songwriting and recording system aimed at ridding the process of anything left-brained, so one need never leave a creative, spontaneous and improvisational state of mind, from the inception of the song until its final master. The program will construct a cohesive song structure, using the best of what you give it, looping around you and growing in real-time as you play. All you have to do is jam and fully written songs will flow out behind you wherever you go.

*Right now The Amanuensis is Windows only (want to help me change that?). You will also need to have Python installed (I'm using 3.5) and Max 7.

To begin simply open Amanuensis.maxpat. When it loads, click "settings". Choose the appropriate audio driver, your drum samples folder, your VST instruments folder and where you would like the resulting recordings and project files to be saved. I generally use a 10 ms tolerance, but you may want to raise that at first until you get the feel for it, so that it's easier for the system to catch a steady rhythm. 8 seconds is a good standard maximum interval between beats. Compressors are optional but consume processing power when on.

Select a track and set up the settings for it as you see fit, depending on what instrument you want to use. Just about anything can be used to play The Amanuensis.
That's about it. Just start playing and as soon as you have a steady rhythm going you should hear it start looping along with you. I recommend first laying down a beat of some kind and then moving on to other tracks to add a melody, etc. if you're having trouble getting it to catch on, play longer, play more steadily or go back to the settings and raise the tolerance.

NOTE: There actually are some caveats to getting VSTs set up and playing at the moment. Get a hold of me or check out the open issues; I'll try to post one about it ASAP.

If you have any questions at all, please do not hesitate to contact me at to_the_sun at mail dot com!*

This version relies on MIDI to denote played notes and uses it to identify when a steady beat has been achieved. Longer steady spans are retained while the shorter ones they overlap are discarded. This is essentially the criteria used to determine which portions of your jam are "best" and works well in practice, although any other method could be implemented in future versions.

Although MIDI must always be present for The Amanuensis to work, this does not mean you can't use ordinary audio sources like acoustic drums or guitar. The program includes a versatile feature called The Singing Stream which can interpret any stream of data into MIDI, whether that be audio or readings from an external controller or a Kinect. This MIDI can then simply accompany that audio source (or another) in order to run the rhythmic analysis, or be used to play VST instruments or samples.

These VSTs and samples are preloaded into The Amanuensis itself so no other software is needed to play MIDI. In addition, the PGUP and PGDN hotkeys allow you to quickly cue up a new sound at random or cycle back to previous ones. This either means a random plug-in from your specified VST folder with a random preset already selected or a new random sample from your specified drum sample folder for each pitch. These hotkeys are basically the only deliberately controlled functions that exist in the system; everything else is meant to be as automatic as possible. But if you're not feeling the sound you're working with, switching to another can be tedious and take you out of the moment. This alleviates that.

For increased automation, there is a function that will "shuffle" your instrument at specified intervals of time or after periods of silence. In addition to giving you a new sound this will also switch you to a random MIDI channel, thereby allowing you to work with another layer of the song. Each song can be comprised of up to 16 tracks (one for each MIDI channel) which are each analyzed for rhythm and built independently, as well as simultaneously. This means an entire band can write a song together or a single player can rotate through every instrument. The number keys as well as + and - can also be used to jump to other channels.

**If you're interested in using The Amanuensis or helping develop it, feel free to get a hold of me and I'll be glad to help you get it up and running!**

## Version 2.0

At this point perhaps one use of an open-source effort might be in creating a brand-new version 2.0 from the ground up. One major upgrade would be to decouple The Amanuensis from its reliance on MIDI. Although more difficult to get working correctly, this would be more streamlined and straightforward from a user's perspective, as well as address certain idiosyncrasies such as what happens when MIDI notes have long attacks or when dealing with glissando in vocals or other instruments. This could be accomplished by reworking the algorithm that judges what parts of the music are best. Instead of relying entirely on analyzing rhythm, i.e. specific moments in time, a more comprehensive machine learning approach could be implemented.

I imagine a deep neural net focused on spectral analysis that on the lowest level is looking at a period of time equivalent to that of maybe a beat, determining where in that window an onset is likely to occur. This would be the layer that judges rhythm, by taking notice of any deviance in their positions. The next layer might look at windows the length of a measure and be able to identify repeated riffs and the like. Additional layers would find patterns on the scale of whole choruses and verses. In theory, deviations in pitch from an established scale could also be detected implicitly. A rating could then be derived based more heavily on the essentials like rhythm, but also taking into account the repetition of higher-level motifs.

At any given moment then, a percentage score could be calculated based on what the user is actually playing versus what the program expected would be most likely to hear. 100% would not necessarily be ideal; good music requires the establishment of patterns and then the breaking away from them. So perhaps a target percentage more like 50 or 75% similar to the expected could be used. At this point, it would be only a small step further to imagine an AI for you to jam right along with. The algorithm could actually generate the audio it expects to come next, rather than just judging based upon it. It would probably be ideal if the AI trained on each instrument it heard independently, so it could truly play alongside you with a different instrument than yours rather than the same one right on top of you, which would be jarring. This is also one of the issues of a player using the system by themselves: as soon as it starts looping, it's often playing the same thing (not quite) totally in sync with you. An AI would be something to brace against while you got going and you wouldn't even need to hear the audio in the track currently being captured until later.

It is also the eventual goal for this system to blend seamlessly into any situation, so music truly can flow out from you wherever you go. I imagine walking down the street and because the sensors on your feet are picking up a steady repetition, a beat starts up spontaneously. Then, as you're compelled to start tapping your fingers on your thigh, the sensors there begin adding a melody of some kind to this inchoate song. A personal soundtrack of new, original music at all times. This is basically my goal in life. The first requirement in moving toward this reality would be an Amanuensis for mobile devices. For this reason it might be ideal to write version 2.0 using JUCE, which I hear is totally cross-platform. A more in-depth framework and one I have not used, but if it's going to be done, it should probably be done right.

## Versions Beyond

The absolute best way to play music is with other people. If your band's not around and the AI (trained to play just like you) isn't stimulating enough, it would be great to be able to jump online and write music with any random person in the world. I find this feedback loop, the give and take with foreign minds, to be essential. Sites like JamKazam.com are great, but if augmented with The Amanuensis, they could be taken to another level. Jamming with The Amanuensis becomes a lot like a game, a far more open-ended version of Guitar Hero with the goal to score highly and create the best music possible. An online matchmaking system could be every bit like those in videogames, throwing players together to compete against (or with) each other to write songs.

And I'll raise the ante once more. There's no reason this sort of pattern detection system has to be limited to audio. If your instrument plays video in addition to audio, you're basically describing what happens in a videogame. In the same way The Amanuensis currently plays back bits of audio that you must interact and deal with, a video Amanuensis would also send visual obstacles and enemies back your way that would then inform and determine your future playing. If you're not familiar with the game Crypt of the Necrodancer, I highly recommend checking it out. What I have in mind would be something like that but on a grander scale, with a soundtrack and even the levels themselves created by and evolving with you as you play, instead of ones that are set from the beginning.