---
layout: post
title:  "Square Enix Is Using Stolen Fan Art for the Steam Port of Final Fantasy VIII"
date:   2024-03-26 01:00:00
categories: news, gaming, tech, muckraking
featured_image: '/images/featured/steam-screenshot.jpg'
excerpt: "The 2013 Steam port for Final Fantasy VIII uses the work of French artist Antoine Retaureau as its library cover image without attribution. The artist’s signature has been cropped out and the image mirrored, inhibiting reverse image searches. <br><br>This has gone largely unnoticed for almost five years."
---


The 2013 Steam port for Final Fantasy VIII uses the work of French artist Antoine Retaureau as its library cover image without attribution. The artist’s signature has been cropped out and the image mirrored, inhibiting reverse image searches.

It didn't launch in this state; Square Enix specifically updated the title to include the stolen artwork six years after its initial release on the platform, following an update to Steam’s store and product asset requirements.

#### This has gone largely unnoticed for almost five years.

Below is a screenshot of the game as it appears in an owner’s Steam library today:

![](/images/featured/steam-screenshot.jpg)

And here is the source illustration. Titled “Squall Berserk at Dollet”, it was [originally posted to deviantART](https://www.deviantart.com/shiroho-art/art/Squall-Berserk-At-Dollet-123107375) in May of 2009 by Antoine Retaureau under the username “Shiroho-Art”.

![](/images/ff8-investigation/squall_berserk_at_dollet.jpg)

The signature, which in some versions of the image is also hand-signed in the lower left corner, matches this [Wayback Machine archive](http://web.archive.org/web/20130606174918/http://laplumemanquante.com/) of Retaureau's personal website circa 2013. More recently, it can be found on his now-defunct [Artstation Profile](https://www.artstation.com/shiroho) and [Facebook groups](https://www.facebook.com/TheArtOfShiroho/).

![](/images/ff8-investigation/retaureau-screenshot.png)


## So here’s the mystery:

I wanted to understand why Square Enix, an international publishing behemoth worth billions of dollars, would feel compelled to update a decade-old product with uncredited fan art ripped from dA.

#### And I now believe I know the answer.

In this article, I will provide records showing precisely when the theft would have occurred; document previous attempts to alert Square Enix to the issue which went unacknowledged; and outline the market forces that are likely to have motivated its use.

#### Square Enix did not respond to requests for comment for this story.

---

## “Art is a brutal world.”

Antoine Retaureau was not surprised when I reached out to him.

He says he first learned about Square Enix’s unauthorized use of his art several years ago, when a friend recognized his work in the wild. He isn't sure exactly when it happened. But then, as now, he felt powerless to fight against an industry titan like Square.

“I didn’t know what to do,” says Retaureau, “I was struggling a lot to make my way in the professional world back then. So, like a lot of artists, I never dared to confront Square Enix.”

A self-described “huge, huge fan” of Final Fantasy at that time, Retaureau recalls the complex emotions of seeing such a beloved game company take his work:

“I was really surprised, happy, and saddened at the same time because of that ‘theft’ feeling.”

He admits he once held out hope that, somehow, the exposure might at least lead to more visibility or recognition in his field. But that big break never materialized.

Unable to support himself with his artwork, he's since left the industry entirely.


## Let’s Build a Timeline

Using the game’s Steam App ID (39150), we can request the current library image from Steam’s content delivery network, or CDN. The URL looks like this:

```
http://cdn.akamai.steamstatic.com/steam/apps/39150/library_hero.jpg
```

In the event they've *finally* corrected it by the time you're reading this, you can find a Wayback Machine archive of its state today at [this link](http://web.archive.org/web/20240319195841/http://cdn.akamai.steamstatic.com/steam/apps/39150/library_hero.jpg).

But, as of writing, the request produces this image:

![](/images/ff8-investigation/library_hero.jpg)

By viewing the response header in our browser’s network tab, we can learn a bit about this file, most importantly when it last modified:[^1]

```
HTTP/1.1 200 OK
Server: nginx
Content-Type: image/jpeg
Content-Length: 375041
Last-Modified: Mon, 02 Sep 2019 20:49:19 GMT
ETag: "5d6d804f-5b901"
Access-Control-Allow-Origin: *
Accept-Ranges: bytes
Cache-Control: public, max-age=507689
Expires: Sun, 24 Mar 2024 18:51:21 GMT
Date: Mon, 18 Mar 2024 21:49:52 GMT
Connection: keep-alive
```

So now we know the absolute latest time it could have been updated. The image has not been replaced since at least September 2nd of 2019.

But that doesn’t necessarily indicate the *exact date it was introduced*; this could, after all, be logging an automated adjustment by Steam, resizing or compressing the file (which is made all the more likely by the fact that this file does not match Steam’s specifications for such an image, more on that later).

All this gives us is the ceiling. We need more information.

So next, let’s examine the app’s update history using [SteamDB](https://steamdb.info/), a service which aggregates metadata from Steam’s catalogue every day and tracks when those elements are changed.

App #39150 was released on December 5th, 2013. Scrolling back through its history, we can see that a new file, “library_hero.jpg” was added six years later in [Changelist #6217477](https://steamdb.info/changelist/6217477/), on May 8th 2019.

![](/images/ff8-investigation/steamdb-log.jpg)

Two days later, on [May 10th](https://steamdb.info/changelist/6229410/), elements of that file’s width and height were updated. Filtering by the key “common_library_assets”, we can verify that these are the only instances on record of the file being modified, throughout the entirety of the game's history.

![](/images/ff8-investigation/steamdb-log2.jpg)

We'll come back to this in a second, but for now...

## I have a hypothesis.


In 2019, Steam released an update to the library’s UI.

Previously, color-treated screenshots from each game (including ones manually taken by the user) were set as a backdrop for each game. This screenshot is taken from a [press release in 2010](https://store.steampowered.com/uiupdate):

![](/images/ff8-investigation/steam-2010.jpg)

In the modern interface, games would require several different sized assets, including a static cover image, logo, and a few different sized thumbnails for big picture mode, etc. Such as the library_hero image we’ve been studying.

According to Steamdb, [there were well over 30,000 games](https://steamdb.info/stats/releases/) already listed on the platform in 2019; each would require new art in order to display properly in the modern interface.

Steam first announced this change at the [March 2019 Game Developers Conference (GDC)](https://steamdb.info/blog/steam-business-update-at-gdc-2019/), and sent periodic reminders as the beta and public launches each approached. In these reminders, Steam asked all developers to return to previously released projects and update their assets, which would otherwise display only as text. Below is a copy of two such emails that I have reviewed; one originally sent in June 2019, the other October.

<div class="gallery" data-columns="2">
	<img src="/images/ff8-investigation/email-june.jpg">
	<img src="/images/ff8-investigation/email-october.jpg">
</div>

From a developer or publisher’s perspective, the warning is: update your game’s artwork quickly, or it’s going to look ugly very soon.


#### I believe that “Squall Berserk at Dollet” was added in response to this update.

Its date of introduction fits within the window Square Enix would have been alerted to the need for additional artwork; after the March GDC announcement, but before the public beta.

It also lines up with the earliest instance of a user calling out the artwork that I can find, which was [posted to Reddit](https://www.reddit.com/r/FinalFantasy/comments/d69kvn/where_does_the_ffviii_library_banner_art_in_the/) on September 18th, 2019 along with a screenshot identical to today’s implementation. This post would have been during the beta, but before the public launch. Since there are no recorded updates to the file since May 8th 2019, and we have this record of what it looked like in September of that year, now I’m confident that [Changelist #6217477](https://steamdb.info/changelist/6217477/) is when the stolen artwork was added.

To further test my hypothesis, I manually assembled a table of all of Square Enix’s games released on the platform before 2020. If I was correct, I would expect to find that Final Fantasy VIII (2013) is among the first games in Square Enix's catalogue to receive such an image.

Excluding 5 games with indeterminate release dates, that list comes out to 45 games total. In addition to the date of introduction of each game’s hero image, I also tracked the number of times they were modified, and what about them was changed.

![](/images/ff8-investigation/spreadsheet-export.png)

{:style="color:gray; font-size: 80%; text-align: center;"}
The full table is available [here](https://www.dropbox.com/home?preview=Square+Enix+Change+History.xlsx), if you want to check my work or need screenreader support.

Based on my review of the data, the stolen artwork was updated alongside at least five other titles (Final Fantasy X/X-2 HD Remaster, Mobius Final Fantasy, NieR: Automata, Final Fantasy XV, and Dragon Quest XI), with each receiving their first hero image on that same day. I've highlighted each of them for convenience.

Of those six, all of them received at least one edit within 10 days, with some receiving as many as three. However, in every case, that edit was to aspects of its positioning; to the best of my knowledge none of them have ever had their hero image replaced.

And yes, this set is the earliest instance on record of any Square title receiving a library hero image. No other Square Enix title predates them.[^2]

While we’re looking at Square’s catalogue, I have one more observation; a partially-upscaled “Remastered” edition of Final Fantasy 8 (which does not feature the stolen artwork) was released on September 3rd, 2019, and it appears in the database as early as February of that year.

So at the time in which “Squall Berserk at Dollet” was selected for use in the 2013 version, a replacement product would have been in active development. The remaster was released during the public beta of Steam’s new UI, and it does not use Retaureau’s artwork.

![](/images/ff8-investigation/remastered_library_hero.jpg)

{:style="color:gray; font-size: 80%; text-align: center;"}
The Remastered edition, released just a few months after Retaureau's image was taken, uses official art as one would expect.

## Mistake, or Cut Corner?

I wanted to see if I could rule out the case of an engineer testing out the image as a placeholder and forgetting to remove it, as I anticipated this might be offered as an explanation. While obviously I cannot definitively disprove it, I do have some evidence which casts doubt upon it.

First, referring to the previous data, we can see that none of the other games which were updated alongside Final Fantasy VIII used placeholders. In fact, as far as I can tell every other game launched with the production graphics which are used to this day.

Second, the subsequent positioning updates for each file suggest that at least one additional review of the image may have been performed post implementation (although I cannot confirm whether those entries indicate an actual human review, or simply an automated adjustment by Steam).

Third is that the image is heavily modified. It’s been mirrored, the colors have been darkened, and the artist’s signature is cropped out. There are valid reasons to make adjustments like these to an image, but they also just so happen to be common techniques to frustrate reverse image searches.

Besides, the entire point of a placeholder is that any old image will do; at the point at which aesthetics are being evaluated, most engineers are going to ask for production-ready assets. And I don’t believe any professional artist handed it to them, because it’s *not even a good copy of the image*; it does not meet the recommended dimensions for Steam’s new header images [as per their partner guidelines](https://partner.steamgames.com/doc/store/assets/libraryassets#hero), and as a result of being resized contains obvious artifacting.


#### But to me, the most compelling counter-argument can be found in the source image, itself.


What’s unusual about this piece, which you may have noticed already, is that it contains some mild gore. Squall is depicted cutting a man in half with his gunblade, exposing the blood and viscera of his foe.

The Steam release shares the original game’s ESRB rating of “Teen”. This clash in tone makes it immediately apparent that it is not official concept art, and is what prompted me to investigate to begin with. It was hard to imagine Square commissioning someone to produce this just for the port.

But perhaps more importantly, because of the violent imagery, deviantART applies its “mature content” filter to it; that means it cannot be viewed by users who are not logged in, and as a result cannot be easily scraped. It is infrequently rehosted. You are unlikely to find it via common search terms like “Squall”, “gunblade”, or even “Final Fantasy 8 fanart”. Reverse image searching only returns a few decades-old forum posts and signatures. You can Google it *by name* and not find it.

I was able to produce it just three times outside of deviantART: once in a post to an RP forum in 2011, once on Pinterest (where it is also uncredited), and ironically the last was the same reddit thread linked above, in which a user questions what the hell it's doing on Steam.

So even setting aside that it is conspicuously modified in a way which also just so happens to prevent its identification, this isn’t likely to be a “grabbed the first placeholder image I saw and forgot about it” sort of mistake. You kind of have to go looking for this one.



#### Overall, I cannot definitively prove whether the image was meant as a placeholder.

On one hand, that the image was included in the earliest batch of hero images would support a claim that this was a missed relic of internal testing.

On the other, none of the other images in that subset seem to have been treated as placeholders. I would also expect “are we using the correct image” to be acceptance criteria, to begin with. The image itself is difficult to find, bordering rare, has been modified in a way common to art thieves, and contains mature elements which would render it immediately and very obviously inappropriate for the product.

Even if it was an honest mistake, using it in this way would have been unprofessional, so the best case scenario isn’t much better.

Ultimately though, only Square Enix can answer why this specific image was used.

Given all of these data points, I personally remain skeptical that it could have been a forgotten placeholder, but I concede that it is unfalsifiable with the resources I have available to me at this time. You are of course free to come to your own conclusion.

## Does Square Enix Even Know?

#### Maybe!

In addition to my own press inquiry last week, I can count at least six other times this has been raised via a channel Square Enix could reasonably be expected to monitor: the official Steam community forums for the game.

The earliest was in [2020](https://steamcommunity.com/app/39150/discussions/0/2143092024473284728/), then [again in 2022](https://steamcommunity.com/app/39150/discussions/0/3469478215315104659/). It [came up](https://steamcommunity.com/app/39150/discussions/0/3881597531955506153/) twice more [in 2023](https://steamcommunity.com/app/39150/discussions/0/3766733548880842594/), and then [two more](https://steamcommunity.com/app/39150/discussions/0/4291439686298112336/) popped up [this week](https://steamcommunity.com/app/39150/discussions/0/4291439686298110710/) as I was waiting for Square's response to this story.

The common consensus seems to be, *yeah, it's obviously stolen, what are you going to do about it?* No moderator has ever responded to one, though I did spot two instances of Valve employees locking other threads for necromancy, as recently as 2023.

Valve has not shared a public policy that I can find on how ownership for these spaces is determined, but [this Vice article from 2018](https://www.vice.com/en/article/d3j7km/steam-moderating-forums-valve-game-developers) suggests that it resides with the developer by default.

As of writing, I have not seen any indication that Square Enix is moderating the board. But it’s definitely out there, if they care to look.

---

Retaureau thinks that you can know someone’s soul if you ask them their quality ranking of Final Fantasy games, and he shared his with me unprompted.[^3] When asked if Square Enix’s plagiarism has changed his relationship with the series he once adored, Retaureau says it definitely has.

“They probably made some of the best games ever made, but today I hate Square Enix with all my soul… I can still admit they make beautiful things today, but it’s never for the good reasons.”


## “I canceled everything.”

#### Unfortunately, this would not be the last time his work was stolen.

He claims that, at one point in his career, it occurred as much as two to three times per week. Often it was his fans that found them, and he remains grateful for their support.

Eventually, though, he was overwhelmed.

“I can’t count it in my mind,” he says, “at some point… it would have been a huge loss [to fight them individually], especially when you have no tools to defend yourself. Call a lawyer? With what money? You’re an artist…”

Retaureau says that this lack of protection, combined with the precarity, poor working conditions for independent artists, and his own personal health needs, forced him to abandon his dream career.

“I don’t draw anymore,” he says, “I’m totally disgusted about it.”

His greatest regret is that his passion project, which he had poured years of work into, remains unfinished. Retaureau describes it as a “adult/seinan manga-euro comic”, set in a fantasy-steampunk world. He says he hopes he can see it completed someday, but because of his physical health and anxiety, it just isn’t an option right now.

![](/images/ff8-investigation/BaniereAxonefBorderless1600x400.png)

{:style="color:gray; font-size: 80%; text-align: center;"}
Art by Antoine Retaureau. Reproduced *with permission*.

His ArtStation has been quiet for several years, but I did notice he broke the silence this February to post a couple of sketches to Facebook. I hope he can rediscover the joy of creating someday.

For now, he has this advice for patrons of the arts:

“Keep cheering your favourites, but not just the popular [artists]. Don’t forget the newbies. They need that too, because we need many ‘art soldiers’ against AI.”


Incidentally, Square Enix CEO Takashi Kiryu [just announced in January of this year](https://www.hd.square-enix.com/eng/news/2024/html/a_new_years_letter_from_the_president_4.html) that the company will be “aggressive in applying AI and other cutting-edge technologies to both our content development and our publishing functions” going forward.

And when he says that, I believe him.

Clearly they're too busy innovating exciting new ways to extract value from artists, to take responsibility for any of their old ones.

[^1]: A huge thank you to Chaz Schlarp and Natalie Jameson for teaching me how to find this data, and to Hayden Neumeyer for hyperfixating on old Steam logs with me.

[^2]: I did find one interesting anomaly: Lighting Returns uses a unique method of fetching its header image that I have not seen elsewhere. It does not have a library_hero at all; if you use its app ID to request it, you get back a 404. And yet, an image *does* display within the client. This confused me for a while, but instead it seems to be pulling it directly from the Steam store page's screenshot list. I have no idea what manner of black magic makes this possible, but as far as I can tell Final Fantasy VIII (2013) has never used this method, anyway.

[^3]: I guess our souls are incompatible because I don’t agree with his tier list, but I’m glad he has one, kupo.
