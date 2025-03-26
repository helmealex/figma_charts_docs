---
title: 'Data Source'
date: 2019-02-11T19:30:08+10:00
draft: false
weight: 1
summary: Charts builder can plot charts with random or Google sheet values.
---

# Random Data Source

![image](https://github.com/user-attachments/assets/6912a1ef-026d-4a56-98de-6411879ee7c4)

You can make the plugin generate random datasets by choosing the **Random data** option from the upper-right dropdown.

There are a few options available to be configured for the random data:
+ **Count** - represents the number of datasets
+ **Length** - represents the length of each dataset
+ **Min Value** - represents the lower point of the interval in which data points are generated
+ **Max Value** - represents the upper point of the interval in which data points are generated

Important: ❗ The above configuration options are not available for all chart types

# Google sheets Data Source

In order to load data from **Google Sheets** you have to follow the following steps.

## Step 1: Open Your Google Sheets Document
1. Go to [Google Sheets](https://sheets.google.com).
2. Open the document you want to make public or create a new one.

## Step 2: Click the "Share" Button
In the top right corner of the page, click the **Share** button.

## Step 3: Adjust Sharing Settings
1. In the "Share with people and groups" window, look for the section titled **General Access**.
2. Under the **General Access** section, click the dropdown that may say **Restricted**.

## Step 4: Change Link Access
1. Select **Anyone with the link**. This will allow anyone who has the link to view, comment, or edit the document, depending on the access level you choose.
2. Choose the type of access you want to provide as **Viewer** - Allows people to only view the document.

## Step 5: Copy the Link
Once you've adjusted the settings, click **Copy link** to copy the link to your clipboard.

## Step 6: Paste the link in the Figma plugin
1. In the plugin window select **Google sheets** from the upper-right menu. An URL input should appear beneath it
   ![image](https://github.com/user-attachments/assets/b39291fd-b144-48a5-bdd5-1cffd0389450)
2. Paste the Google sheets copied URL in the input. The data from the sheet should successfully be loaded

# Data formatting

Depending on the type of charts you selected the data you enter in the Google sheet should look different:

## Bar / Line / Area & Radar charts

[Here](https://docs.google.com/spreadsheets/d/1GBpzleFFwKTv3Qq6Bn8YH91BP3g75dswdKnXz4ePrAk/edit?gid=1498389673#gid=1498389673) is an example for these types of charts

|             | Dataset 1 | Dataset 2  |
|-------------|-----|-------------|
| Label 1       | 25  | 12    |
| Label 2        | 30  | 22    |
| Label 3    | 35  | 34     |

**The first line** with the headers will ignore the first cell and the next cells need to contain the names of the datasets (they will be displayed in the legend)

**The first colum** starting from the second line will contain the names of the lables which will be displayed alongside the X axis for bar, line and area charts and around the ends for radar chart.

**All the other cells** from the second line and second column should contain numeric values representing data points. Each column from column number 2 represents a dataset. 

You can create as many columns as you wish, but you have to make sure you respect the above mentioned rules.

## Pie / Doughnut / Polar area charts

[Here](https://docs.google.com/spreadsheets/d/1tVn5lqKgo6q8e61_JIgBfkuvdyUNlcWrioQtGrUmlmY/edit?gid=812464488#gid=812464488) is an example for these types of charts

|             | Data | 
|-------------|-----|
| Label 1       | 25  | 
| Label 2        | 30  | 
| Label 3    | 35  | 

**First column** from second line represents the dataset labels represented in the legend

**Second column** from second line should contain numeric values representing the values of a pie.

## Scatter chart

[Here](https://docs.google.com/spreadsheets/d/1Lu9w10A5uPCnfyUTDlu1X72WL1Zns2QMot3Mz9i_foU/edit?gid=1961939755#gid=1961939755) is an example for this type of chart.

|   Dataset 1          |  | Dataset 2| |
|-------------|-----|---|---|
|12      | 25  | 12|34|
| 33        | 30  | 34|45|
| 44    | 35  | 22|36|

**First line** should contain the dataset names separated by one empty cell.

**Second line** below should contain for each dataset x and y coordinates for the scatter points. The values are below the dataset name - for example **12** and **25** represent the **x** and **y** coordinates for a point from **Dataset 1**.

## Bubble chart 

[Here](https://docs.google.com/spreadsheets/d/12_lAMVPOm64ZT9Menlms8YBI40oR5FJTh86nv2WKMUU/edit?gid=1620552751#gid=1620552751) is an example for this type of chart.

|   Dataset 1          |  | | Dataset 2| | |
|-------------|-----|-----|---|---|-----|
|12      | 25  | 12|34| 12 |10|
| 33        | 30  | 34|45| 33| 5|
| 44    | 35  | 22|36| 12| 44|

It is similar to the scatter chart, exception is that it has an additional column for each dataset that represents the **radius** of the bubble.  For example **12**, **25** and **12** represent the **x**, **y** and **radius** of a bubble from **Dataset 1**.
