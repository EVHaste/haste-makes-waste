---
layout: post
title:  "Square Enix Is Using Stolen Fanart for the Steam Port of Final Fantasy VIII"
date:   2025-03-18 13:00:00 -0800
categories: news, gaming, tech, muckraking
featured_image: '/images/featured/steam_cap.png'
excerpt: "The 2013 Steam port for Final Fantasy VIII uses the work of French artist Antoine Retaureau as its library cover image without attribution. The artist’s signature has been cropped out and the image mirrored, inhibiting reverse image searches. This has gone largely unnoticed for almost five years."
---

The 2013 Steam port for Final Fantasy VIII uses the work of French artist Antoine Retaureau as its library cover image without attribution.

The artist’s signature has been cropped out and the image mirrored, inhibiting reverse image searches. This change was made after the game's release, and has gone largely unnoticed for almost five years.

Retaureau __________. Contacted for a statement, Square Enix ____________.

### Receipts, Please

Here is a screencap of the game as it appears in an owner’s library today:

![](/images/featured/steam_cap.png)

The source illustration, titled “Squall Berserk at Dollet”, was originally posted to deviantART in May of 2009 by Antoine Retaureau under the username “Shiroho-Art”.

![](/images/ff8-investigation/squall_berserk_at_dollet.jpg)

What’s unusual about this piece is that it contains some mild gore. Squall is depicted cutting a man in half with his gunblade, exposing the blood and viscera of his foe. This is important for two reasons.

First, the Steam release shares the original game’s ESRB rating of “Teen”. This clash in tone makes it immediately apparent that it is not official concept art, and is what prompted me to investigate to begin with. It was hard to imagine Square commissioning someone to produce this just for the port.

But perhaps more importantly, deviantART applies its “mature content” filter to it; that means it cannot be viewed by users who are not logged in, and as a result cannot be easily scraped. It is infrequently rehosted. You are unlikely to find it via common search terms like “Squall”, “gunblade”, or even “Final Fantasy 8 fanart”. Reverse image searching only returns a few decades-old forum posts and signatures. You can Google it by name and not find it.

So setting aside that it is conspicuously mirrored, darkened, and cropped for its use in the Steam interface, this isn’t likely to be a “grabbed the first placeholder image I saw and forgot about it” sort of mistake. You kind of have to go looking for this one.




## HEADING

Here’s the effect it had on the creator. He says he was notified of the situation years ago, but was afraid to speak up.

I contacted Retaureau and confirmed that he didn't license the image. I was surprised to learn that he already knew about it.



He says that a friend brought it to his attention years ago, although he couldn't say with confidence when it happened.

That's where I come in.

### I can not only pinpoint *when* this happened...

## ...I believe I can even tell you why.

---

## Let's Build a Timeline

In 2019, Steam released an update to the library’s UI.

Previously, color-treated screenshots from each game (including ones manually taken by the user) were set as a backdrop for each game. In the new interface, games would require several different sized assets, including a cover image, logo, and a few different sized thumbnails for big picture mode, etc.

By 2019, there were well over 30,000 games listed on the platform; each would require new art in order to display properly in the modern interface.

Steam first announced this change at the March 2019 GDC, and sent periodic reminders as the beta and public launches each approached. In these reminders, Steam asked all developers to return to previously released projects and update their assets, which would otherwise display only as text. Below is a copy of two such emails; one sent in June, another October.

[embed]

From a developer or publisher’s perspective, the threat is: update your game’s artwork, or it’s going to look ugly very soon.


Next, using the game’s Steam App ID (39150), we can request the current library image from Steam’s content delivery network, or CDN. The URL looks like this:

```
http://cdn.akamai.steamstatic.com/steam/apps/39150/library_hero.jpg
```

Which, when visited, produces the current hero image:

![](/images/ff8-investigation/library_hero.jpg)

By viewing the response header in our browser’s network tab, we can see when this file was last updated (the part we care about is the “Last-Modified” field):

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

This tells us when it was last changed, so we know that’s the absolute latest time it could have been updated. But it doesn’t necessarily indicate when exactly the theft occurred; this could, after all, be an automated adjustment by Steam, resizing or compressing the file (which is made all the more likely by the fact that this file does not match Steam’s specifications for such an image). All this gives us is the ceiling.


So next let’s look at the app’s update history using SteamDB, a service which scrapes and aggregates metadata from Steam’s catalogue.

Scrolling back, we can see that “library_hero.jpg” was added in Changelist #6217477, made on May 8th 2019, and information about its positioning was updated two days later. No other changes have occurred since then.

This date fits within the window Square Enix would have been alerted to the need for additional artwork, after the March GDC announcement, but before the public beta. This also matches the first instance of a user questioning the artwork mismatch that I can find, posted to Reddit on September 18th, 2019, with a screenshot that matches today’s implementation. This would have been during the public beta. Since there are no updates to the file since May 8th 2019, and we have a record of what it looked like in September of that year, I’m confident that this is the change in which the stolen artwork was added.

The stolen image was called out at least two additional times on the official Steam forum for the game; once in 2020, and again as recently as 2023. Its important to note that developers are defacto moderators for their game’s Steam Community forums, though I haven’t found any indication that they are still actively monitoring the space.

Finally, the “Remastered” edition of Final Fantasy 8 (which does not feature the stolen artwork) was released on September 3rd, 2019, but it appears in the database in _________, with its app ID being created as early as January. So at the time Retaureau's fanart was selected, Square Enix was aware that a superior, competing project was in development, and it was released before the public launch of the new Steam UI. That product received its own dedicated art assets.





Contacted for comment, a representative of Square Enix said __________.

---

Next, I wanted to see if I could rule out the case of an engineer testing out new functionality and forgetting to remove the placeholder, as I anticipated this would be offered as an explanation. So, I made a table of all of Square Enix’s games released on the platform before 2020, along with their release dates and when their hero images were first introduced to the client by filtering SteamDB changelogs by the key “common_library_assets”.

Excluding 5 games with indeterminate release dates, this leaves 45 titles, total. You can find that metadata summarized below, or review my work in the original spreadsheet here:[^3]



Based on my review of the data, the stolen artwork was updated as part of a batch on May 8th, 2019, along with hero images for at least six other titles (Final Fantasy X/X-2 HD Remaster, Mobius Final Fantasy, NieR: Automata, Final Fantasy XV, and Dragon Quest XI). This is the earliest instance on record of any Square title receiving a library hero image.

Of those six, all of them received at least one edit within 10 days, with some receiving as many as three. However, in every case, that edit was to aspects of its positioning; to the best of my knowledge none of them have ever had their hero image replaced.

---

* **So our final timeline of events looks like this:**
  * In March of 2019, Steam announces their upcoming UI update at GDC.
  * From that time until the public launch in October of that year, Valve periodically nagged developers to update the art for their old games.
  * Between March and May, someone modified _____’s fanart in such a way that frustrates identification, but not enough to meet the specifications in the provided developer documentation.
  * On May 8th, 2019, this file was included in changelist #6127477, as “library_hero.jpg”. At least five other games were modified that day, using official artwork.
  * On May 10th, the positioning of the this and other images are adjusted, but none are replaced.
  * On August 20th, Final Fantasy 8 Remastered receives its own hero image, made from official artwork, in advance of its launch.
  * On September 3rd, Final Fantasy 8 Remastered releases.
  * Later that month, the public beta of Steam’s new UI begins. The stolen work is noticed and discussed on third party platforms, but this doesn’t go anywhere.
  * In October, the new library UI launches publicly. Now anyone who owns the game can see it.
  * In 2020, another thread about the artwork is created, this time in the official Steam Discussion forum. It is either not seen or not responded to.
  * This occurs again in 2023.
  * It’s 2024 now, if you can believe it.

---

#### So, does the placeholder claim hold up?

Overall, the results are inconclusive. On one hand, the stolen image was included in the May 8th batch of hero images. These are the earliest examples of Square using them during the beta period, and that would support a claim that this was due to internal testing.

On the other, the changes to Final Fantasy 8 do not appear to have been made in isolation, but as part of a larger set. According to the data, all of them (including the image in question) had their positioning values modified again just days later, which would provide an additional opportunity for quality review. Meanwhile, none of the other images in that subset seem to have been treated as placeholders. I would also expect “are we using the correct image” to be acceptance criteria, to begin with.

Based on my time working in software development, I would expect even engineer-improvised graphics to be images which are readily accessible, not ones which require a site membership to obtain. I also would not expect there to be any need to modify those placeholders to the extent this one has been; in my experience, artists are more likely to prototype within their graphic design software using brand-safe assets, and engineers are unlikely to care enough to make cosmetic adjustments to images that they plan to immediately replace. This behavior doesn’t serve much practical purpose beside obfuscating the art’s source, which it was very successful at doing.

Given all of these data points, **I personally remain skeptical of this explanation**, but I concede that it is unfalsifiable with the resources I have available to me at this time. You are of course free to come to your own conclusion.




## HEADING

Today, ____________________.

He has some advice for aspiring artists: _____________.


He also provided a few pages from his last comic project, which he's given me permission to share here. The name, he says, is a secret.







Also, this is totally besides the point but it’s not a very good port. The soundtrack is distorted, and it’s a pain in the ass to fix via modding.

And you know what? I actually really like the art. It's not like, tonally consistent with the game or anything, but I think it looks pretty good. I've set it as a custom background in my client, so now we're back where we started.

Except I sized it correctly.
