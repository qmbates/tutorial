---
layout: default
title: more
permalink: /more-tableau/
---

# more Tableau charts

now that you know how to create basic charts, let's look at some more ways to sort and visualize our listening data.

***

### other filters

we already saw how the **Top** filter works. but what do the other filter options do?

* **General** allows you to pick and choose from the entire list of distinct entries for a field. this could be useful if we want to compare and contrast
only a few certain entities at once.

<img width="99%" alt="general" src="https://github.com/user-attachments/assets/14972224-997a-4d81-a00d-cf33abc12884" />

* **Wildcard** allows you to to easily exclude a certain entry, or even filter by first or last letter. we can narrow our results down only to `artists` whose
names begin with the letter **k**, for instance.

<img width="99%" alt="wildcard" src="https://github.com/user-attachments/assets/5b7fc9d6-b3c8-4627-ad3c-33fa88f6542e" />

* **Condition** allows you to filter only to entries that meet a certain condition. for example, we could filter `tracks` to ones we have listened to
at least 50 times.

<img width="99%" alt="condition" src="https://github.com/user-attachments/assets/babcdd4f-ca44-4e86-9707-5a5f4d7eb3a7" />

**! to clear filters, you can click and drag them out of the _Filters_ box.**

***

### measuring over time

your Spotify data comes with a timestamp for every instance of a track playing. however, Spotify formats the timestamp in a way that Tableau cannot read.
fortunately, Tableau allows us to create a **Calculated field** in order to format all of our timestamps in one go!

* go back to the **Data Source** tab.

* in the window on the bottom right, scroll all the way to the right until you get to the `ts` field.

* click the dropdown, then choose **Create Calculated field**.

* remove the content inside of the box, then paste this: `"DATEPARSE(YYYY-MM-dd'T'HH:mm:ss'Z'",[Ts])`

* rename the field.

* click **Apply**, then **OK**.

<img width="99%" alt="dateparse" src="https://github.com/user-attachments/assets/a5edda63-64f6-41b3-b86d-e560d242914f" />

you have created a new timestamp field that is usable by Tableau. let's see what it can do with an example.

* go back to the **Sheet 1** tab.

* put the `artist` field up into the **Rows** bar. filter to a specific artist.

* put our new `timestamp` field into the **Columns** bar. a new graph will populate!

* when you put `timestamp` into **Columns**, it will automatically select **YEAR** as the format. change the format to **Exact Date** instead.

this graph shows us each instance that we listened to our selected artist.

<img width="99%" alt="instance" src="https://github.com/user-attachments/assets/81d379d2-4b4c-40b3-a064-bd55b1c40d8c" />

we can take it a step further and create a more tangible visualization that shows how our listening trended over time.

* add the `ms played` field to the **Rows** bar.

* in the menu for `ms played`, go down to **Quick Table Calculation** and select **Running Total**.

voila! now we have a chart that displays our listening trends for the chosen artist. the sharper the incline, the more we were listening
to that artist over that period of time.

<img width="99%" alt="trend" src="https://github.com/user-attachments/assets/fde9a3c1-acaf-4239-8c7f-0d776d08f94e" />
