---
layout: default
title: starting with Tableau
permalink: /starting-with-tableau/
---

# starting with Tableau

Tableau is a data visualization and analytics software that is engineered to be intuitive.

Tableau has many online tutorials on using all of their features. today we will only be highlighting 
the ones that will be most useful for this project.

in this tutorial we will be using Tableau Desktop. Tableau's Desktop edition is 
<a href="https://www.tableau.com/products/desktop">free to download here</a>; after installing it, 
all you will need to do to start using the software is create and log in to an account.

***

### importing your data

* open Tableau Desktop. in the menu on the left under **To a File** click **JSON file**.
 
* browse to your chosen dataset. (depending on how old your Spotify account is, you could have a few or many .json files.
each file contains your listening data from a certain period of time.)

* select a file and click **open**. when prompted, click **OK**.

your data has been loaded! you will see all of the included fields in the window on the bottom left.

for more information on the fields in this dataset, you can refer to the **READMEFIRST** file that was included with your data files.

<img width="99%" alt="tableauopendata" src="https://github.com/user-attachments/assets/edb95dc4-d615-49f1-8991-8aa99103f2db" />

we will need to open up the sheet page to start creating visualizations. click the **Sheet 1** tab in the bottom left.

when you open Sheet 1, you will see all of the data fields in a menu on the left. these are the data fields that we will be
using. some of the names are straightforward, but others make it difficult to navigate.

you can rename fields by clicking the dropdown menu on the field or right-clicking the field. hovering over a field shows you its full name.
i recommend renaming the `artist`, `album`, and `track` fields to make them easier to remember. (these are the fields that begin with
"`master_metadata`".)

<img width="99%" alt="namechange" src="https://github.com/user-attachments/assets/3405506a-46d9-454c-9534-f6b5b96288d6" />

***

### basic visualizations

now we can start making charts!

in the data menu on the left, you will see <a href="https://help.tableau.com/current/pro/desktop/en-us/datafields_typesandroles.htm">two groups</a> 
of fields. the top group (blue icons) are called **dimensions** and the bottom group (green icons) are called **measures**. to make a simple bar chart we will need one of each.

the measure that we will be using for this tutorial will be `ms played`. This measure counts the milliseconds that each track or podcast episode
was played. combined with dimensions such as artist or track, we can start to create simple charts.

* click and drag the `ms played` field up into the **Columns** bar.

* choose a dimension (here i chose `artist`) and drag it up into the **Rows** bar.
  * (if your data contains many different entries for a field, the software will ask you to confirm that you would like to load all of them.)


* a chart will be created automatically. you can sort this chart using the **Sort** buttons in the top menu. hovering over any option shows the total amount of time it was played.

<img width="99%" alt="simple artist chart" src="https://github.com/user-attachments/assets/b670304b-1d27-47c1-abd7-7ff865a23e09" />

now we have a chart that shows us a ranked order of how long we spent listening to every artist we listened to!

total time played can be a useful measure, but what if we want to see how many times we listened to a song by each artist? to do so, we will need to change the value
that our **measure** field is counting. 

* click the dropdown or right-click on the `ms played` field. go down to **Measure (sum)** and change it to **Count**.

your chart will change! (for instance, although you may have spent more time listening to artist A than artist B, you may have listened to artist B's songs
more times because they are shorter.)

while we are at it, we can also clean up our chart by **filtering** it. you can do all sorts of cool things with filters, but for now, let's just shorten our chart to our
top ten artists.

* click the dropdown or right-click on the `artist` field. choose **Edit filter**, then go to the **Top** tab.
 
* click **By field** and input however many results you would like. click **Apply**, then **OK**.

<img width="99%" alt="count and filter" src="https://github.com/user-attachments/assets/4c18b0c8-d2e0-4582-a9bb-c2ce3a71279a" />

***

you now know the basics of creating your own listening charts. try messing around using `track` and `album` instead of the `artist` field.

when you're ready to try some slightly more complicated charts, head to the <a href="/tutorial/more-tableau/">more tableau</a>page.
