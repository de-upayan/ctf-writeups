**Flag:**
```
JUCTF{th3r3'5_th3_gr33n_ra66it}
```

We are given an image file *'f1nd_m3.jpg'* along with a plea to find my lost pet. The problem statement also contains an embedded image which, on first glance, appears to be a **green rabbit** (this will be of significance later). We also note that the statement is written in condensed SMS lingo, which also serves a distinct purpose.

![f1nd_m3](https://user-images.githubusercontent.com/96875426/227784981-8840c404-ca9d-472a-b197-6cf8ec6eb588.jpg)

Zooming into the image, we can decipher the following words written on the signboard: ``RUE DE L'ACADEMIE``

Searching this on Google Maps, we get the following results:

![img](https://user-images.githubusercontent.com/96875426/227785609-9282e071-de2b-4c21-89a2-615d519b8f8b.png)

*(Note that you might have to zoom out significantly, or get the entirety of Europe in the frame to get the exact same results)*

Here begins the tedious part of the question. One by one we scour through the Google Street Views of each of the 5 possible locations, until we find the location resembling our image. However we have a hint embedded in the problem statement itself which makes it easier to identify the correct location.

Remember the unassuming image of the green rabbit in the problem statement? Well, let's have a look at ``Rue de l'Académie, Lausanne, Switzerland``:

![img](https://user-images.githubusercontent.com/96875426/227786097-74bea7bf-d1d1-4c4d-8fde-7dc5a72f8dce.png)

Those familiar with a little bit of French will recognise that [**'Le Lapin Vert'**](https://www.google.com/maps/place/The+Green+Rabbit/@46.5235378,6.6354586,19z/data=!4m15!1m8!3m7!1s0x478c2e313aa1b7f5:0xaedacac04eae28b9!2sRue+de+l'Acad%C3%A9mie,+1005+Lausanne,+Switzerland!3b1!8m2!3d46.5234825!4d6.6357551!16s%2Fg%2F1tj3jzd8!3m5!1s0x478c2e312e2c4359:0x265902b12b81748c!8m2!3d46.5235316!4d6.6357696!16s%2Fg%2F1td6462w) is indeed French for **'The Green Rabbit'**. It is a pub in Lausanne, Switzerland. Bingo! We've found our lost pet. But where's the flag?

For this, let's go back to our oddly-phrased problem statement: ``My osm pet rn awy! Help pls 😭!``

The use of the term **'osm'** instead of 'awesome' was the hidden hint here. Googling it gives us:

![img](https://user-images.githubusercontent.com/96875426/227786508-8d38722e-f9f4-480e-9a46-a9578867d48c.png)

Once we've gone this far, the rest of the idea is quite intuitive. We copy the coordinates of 'Le Lapin Vert' ``46.52357471021502, 6.635780465080955`` and plug it into OpenStreetMap. Zooming in on the pub and turning on the **Map Notes** layer in OSM gives us a [note](https://www.openstreetmap.org/note/3610427) created by an anonymous user (aka me) 3 days ago:

![img](https://user-images.githubusercontent.com/96875426/227786882-e24c333b-75c6-48fa-9a18-18d3e9daf807.png)

**PS:** *The concerned note will disappear from the OSM Map by 31st March, 2023 by OSM Policy*
