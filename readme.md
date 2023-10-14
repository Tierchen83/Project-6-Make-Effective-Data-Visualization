# Visualizing baseball data with Dimple  / D3

&nbsp; &nbsp; &nbsp; 
In this visualization we are presenting the performance of 1157 baseball players. The data itself is offering different information:

- Player's name
- Handeness: left, right or both hands
- Height: player's height
- Weight: players weight
- Average: average batting performance
- HR: Homeruns



## Approach

&nbsp; &nbsp; &nbsp; We want to visualize the data in regards to two aspects:

1) Visualize possible correlations between the height and the average batting performance of the players. For this, we use a bubble chart and filter on the 
    top players having an average > 0,28 to avoid having too many data points.</li>
2) We want to visualize, if the handedness (left, right, both) has an impact on the average of the average batting performance

## Initial design decisions

### 1. First chart: height vs batting performance

Given the number of over 1000 entries, it was clear to use a scatter or bubble diagram to check for the relationships between different variables. I took the decision to go for a bubble plot instead of a scatter plot to visualize the Batting Average, the height but as well the Homeruns (HR) via the Z axis after collecting some first feedback on the scatter plot (see feedback section)

First tries to visualize all 1157 results resulted in overlapping data points. 

![](/img/initial1.PNG)

I thought of different options such as aggregating or reducing the size. However, the results remained unclear so I went for a filter on the average performance > 0,28 to get the best players

Also, I saw that a relation weight/avg relationship would not be very intuitive so I rather went for the height:

![](/img/initial2.PNG)



Applying the filter resulted in a less overloaded picture 

![](/img/initial3.PNG)

Adapting and playing with the axis min/max gave me the final picture

![](/img/initial4.PNG)

### 2. Second chart: handedness vs avg of the average betting performance 

We want to know, if the handedness (left, right, both) has an impact on the average of the average batting performance and decided for a bar chart to categorize the handedness.

It was quite tricky to get the average done in dimple.js. Intermediate results only **showed the sum instead of the average**:

![](/img/initial5.PNG)

## Feedback and iterative improvement

### Feedback 1

A first feedback with a working colleague who is doing Data Visualization on a daily basis in Qlik was based on a first version of the scatter plot without having applied filters and colors. She mentioned that I should think of ways of how to reduce the data load while not losing too much data points. Also, she suggested using a bubble chart instead of a scatter

![](/img/scatter.PNG)

### Improvement 1

This is where I saw the possibility of using a bubble plot instead to have another axis. So I went for the bubble chart and started experimenting with possibilities to reduce the data points

### Feedback 2

A second feedback included my data analyst colleague who liked the reworked design, but suggested making more out of the data by making it more interactive and trying to use more of the provided information.

### Improvement 2

This is where I thought using a mouse-over effect and used the "myChart1.addSeries(["name", "handedness"], dimple.plot.bubble)" in order to add additional and useful information such as the name and handedness.

![](/img/mouseover.PNG)

### Feedback 3

The last interview was with a good friend of mine sharing a well advanced version after the first two feedbacks. He made rather small remarks like being more precise on titles and axis, reduce the radius of the bubbles to make it more visible and also think of the handedness and how it is reflected in the data

### Improvement 3

Based on this feedback I added some more detailed titles, played with the radius and developed the idea to check the average of the average batting performance.

![](/img/title.PNG)

![](/img/chart2.PNG)

## Interpretation and findings

1. Shorter players have a slightly better batting performance

![](/img/chart1.PNG)

2.  Both hand players have the best average of the average batting performance closely followed by the left-hand players. This is quite interesting and maybe both handed players have simply more options to switch and adapt.

   ![](/img/chart2.PNG)


​	

## External resources

<a href='https://stackoverflow.com/questions/33179439/d3-js-dimple-getting-a-title-on-a-graph'>1) Stackoverflow: Getting a title</a>

<a href='https://stackoverflow.com/questions/25559658/dimple-js-how-to-customize-range-of-values-on-y-axis-from-0-to-100'>2) Stackoverflow: Dimple.js how to customize range of values on Y-axis from 0 to 100?</a>

<a href='http://dimplejs.org/examples_viewer.html?id=bubbles_standard'>3) Dimple.js: Bubble Template</a>

<a href='https://www.w3schools.com/html/html_css.asp'>4) W3schools: HTML Styles - CSS</a>

<a href='https://www.w3schools.com/css/css_link.asp'>5) W3schools: HTML Styles - CSS Links</a>

<a href='https://www.udacity.com'>6) Udactiy Nanodegree: Data Visualization chapter</a>

