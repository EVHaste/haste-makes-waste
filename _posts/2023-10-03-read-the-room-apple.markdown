---
layout: post
title:  "Read the Room, Apple 🎉💀"
date:   2023-10-03 07:00:00 -0400
categories: tech
featured_image: '/images/featured/hooray.jpg'
excerpt: "Gestures are frequently triggering at inappropriate times, in the best case simply ruining a solemn moment with tasteless commentary. In others, it’s creating legitimate panic and discomfort for patients in mental health care settings."

---

From an engineering standpoint, the new iOS 17’s newest Facetime feature, Gestures, is working exactly as intended.

But from a product perspective, it’s a nightmare.

Gestures are frequently triggering at inappropriate times, in the best case simply ruining a solemn moment with tasteless commentary. In others, it’s creating legitimate panic and discomfort for patients in mental health care settings.

## “I had to look at a lot of dead bodies.”

A close friend of mine was telling me over FaceTime about a difficult civic tech project they had just launched; a tool for the CBC which scrapes the [National Centre for Missing Persons and Unidentified Remains](https://www.canadasmissing.ca/index-eng.htm) databases, combines them, and allows journalists to make matches between the two. Analysis of the data has also revealed potential biases in the ways that missing persons cases are classified, based on gender and ethnicity.

It’s grim work, they were explaining, but it’s important, as the RCMP is historically either unable or unwilling to do it themselves. The mood was heavy, but I was (and am) really proud of them.

One of their first contributions was to replace images in the developer environment with less graphic placeholders, but this still necessitated some testing. In this moment, they were confiding in me the immense toll it had on their mental health.

“Some of them stuck with me,” they told me, “I still see them everywhere. After the presentation, I broke down in a grocery store parking lot, called my—“

Suddenly the screen was filled with colorful balloons. Hooray! 🎈

We were both absolutely stunned. What the fuck just happened?
It took a while for us to figure it out.

It turns out, my friend had counted on two fingers while talking about two particular faces of the deceased that they couldn’t get out of their mind.

FaceTime, which had apparently been updated between iOS 16 and 17 to scan camera inputs for its new Gesture feature, had interpreted their hand position as a peace sign, and decided what they really needed was some help celebrating.

> This person is sad, deploy the party immediately!

And I mean, the mood had definitely changed, I’ll give it that. From solemn, to violated.

“That’s so disgusting,” they said. “ I’m so upset right now. I don’t even have words.”

This did not happen just once, but four times in the same two-hour conversation.

The second time, we were talking about gun violence; my friend and I are both queer, and as someone of mixed race they’re at a particularly elevated high risk of being a target of a hate crime. Being a stupid American, I’d asked them if concealed carry was an option for them, and they explained that wasn’t legal in Canada. There were two sets of laws, one for Long guns and another for handg—

Then confetti rained down on both of our screens.

They had held up two fingers again, on each hand, and this triggered another bespoke and completely inappropriate animation.

“Who the fuck thought this was a good idea?”
I honestly don’t remember which one of us said this, and it doesn’t matter. It’s a sentiment we both shared. They decided to count using the German method (thumb first) for the rest of the conversation to avoid triggering it.

Except that didn’t work. Because that triggered the “thumbs up” gesture. The same happened to me later, when talking about my own experience with anti-transgender discrimination.

My hands were just folded on the desk.


*Big deal*, you might be saying, *so your precious little conversation got a little awkward. Nobody got hurt.*

And look, I’ll confess I do enjoy a bit of gallows humor now and then. But setting this particular conversation aside for a second, there’s another group of people that is being harmed by this.


## And Is This “Apple” In The Room With Us Right Now?

Recounting this story to my therapist the next day, I only got as far as the word “FaceTime” before their eyes lit up.

“Oh, this, I know exactly what you’re talking about.”

As it turns out, a non-zero number of mental healthcare professionals use FaceTime for their Telehealth practice. According to mine, the Seattle professional support group they’re a member of is currently freaking out about this sudden and unpleasant change.

Patients who are discussing deep and personal traumas have also had their sessions interrupted with inappropriate animations; balloons, confetti, hearts, and more, according to my therapist. [^1]

They hadn’t personally encountered it, as they don’t use a Mac, but they had colleagues who had.

“There’s a lot of discord right now,” they said, “nobody knows what’s going on or if there’s a privacy concern there, what information is being shared…”

Now hopefully, this is all just being done locally on-device. It would be absolutely bananas not to have thought of that. But I could say the same for the implementation of this feature. And I’m coming from a tech background; therapists probably aren’t.


## Other People Who Are Probably Confused

Users of sign language are probably also having some trouble with this. ASL signs for common words and phrases like “help”, “cigarette”, and “I love you” use hand and finger formations which are similar to the celebration, thumbs up, and (admittedly very cool) laser beam dance party animation triggers in the new FaceTime. [^2]

You do have to hold the sign in order for it to trigger, so in theory that should reduce how often this happens, but if you’re signing slowly, it could still happen.


And I’m also super curious whether they’ve accounted for regions in which the thumbs up, peace sign, and devil horns have alternative meanings.



## And Now A Word From Dr. Ian Malcolm

What I want to know is, literally who asked for this?
Who wanted this? Who does it help?

If such a person exists, which I doubt, then why don’t you bring its existence to the user’s attention? Why don’t you ask for consent, first like you already do for other types of input monitoring such as Siri trigger words? Why can’t you turn it off? (because you can’t, I checked)

It feels inherently invasive to suddenly have a new observer, or worse, a new participant, in a conversation that you were not expecting. It feels like a stranger inviting themself to your baby shower and taking a big, sloppy swig from your drink. Who are you, you don’t even go here?

I will not contest that the laser dance party is delightful to look at. But in order to use any of these things, you have to know about them. And there’s currently no way to know about them without triggering one when you weren’t intending to. So naturally we’re all finding out about it in the absolute worst moments and the vibes are just rancid.

Here’s a shitty user story for you:

#### As a person in a vulnerable mental state, I want my phone to read my camera in new ways I was neither aware of nor consented to, so that a jeering peanut gallery can invade my most private conversations with inappropriate commentary.

I personally am not convinced Gestures provide anyone with any value, other than getting another foot in the door for real-time device scanning. I’m not saying the intent here is nefarious, they probably just wanted to make somebody smile. And look, the laser dance did that. I really like the laser dance, y’all.

But it is not a good look to surprise people with the ways you are using their data immediately after the 2021 iCloud surveillance debacle. We aren’t exactly overflowing with trust for our tech right now.

Even if you disagree with me and think that this idea is great actually, in its current implementation, it is making people feel bad. That should be enough reason to change it.


Okay, now that I’ve had my fun roasting it, I guess I can try to be constructive.
If it were my job to salvage this thing, I guess I would suggest one or more of the following to make it feel less yucky.

1. Give the users the ability to disable it, preferably after an opt-in.
2. Or Use different gestures that are harder to accidentally trigger.
3. Or Pair the gesture with a Siri awake word (but this makes weird permissions edge cases)
4. Or Increase the window for holding the gesture.
5. Or throw out everything but the laser dance, the laser dance can stay.

[^1]: I obviously can't interview and provide attribution for my own therapist, what with the whole patient-client confidentiality thing. I reached out to some other folks in the field though, and if I hear back I'll do a proper piece.

[^2]: I uh, I think. I am not an authority on any kind of sign language, I just remember bits and pieces from my friends in college (probably incorrectly). Sorry to any native speakers in my audience.
