---

layout: post
title: "TIL about margin convention in d3"
categories: til

---

TIL about [margin conventions in d3](https://bl.ocks.org/mbostock/3019563). When you draw a visualization inside an SVG element, you tend to lose extreme datapoints. They tend to go beyond the SVG element, like this:

![beforemargin]({{ site.url }}/images/beforemargin.png)

This happens because our circles (datapoints) are drawn with the origin as the value of [*cx* or *cy*](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/circle). So if the y-axis value happens to be 0, (x,0) becomes the origin point of our circle. Therefore, we lose half of that circle as the radius takes it down and out of svg. Same is true for cases when x value is maximum (the rightmost half-circle). A simple standard that is used in d3 community is to add margins around the visualization. Instead of drawing the graph directly inside the svg element, we define a *g* element withing the svg element and then draw our visualization (scatterplot or barplot) within that g element. Like so:

![aftermargin]({{ site.url }}/images/aftermargin.png)

Notice how all the circles are completely inside the g element now. By defining the margins beforehand and setting up a *g* element based on those margins, allows us to focus on subsequent visualizations without ever worrying about margins. 

I created a remixed version of the code [from here](https://bl.ocks.org/curran/f4ca72a38bcbb5893d37ce48ed9d4796). Two scatter plots side by side. The details of the dataset aren't important for this TIL but if interested, one on the left is the [survival results of breast cancer patients who underwent surgery](https://archive.ics.uci.edu/ml/machine-learning-databases/haberman/) while the one on right is the famous [IRIS dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data). 

![two scatter plots]({{ site.url }}/images/twoscatters.png)

Code, datasets and above visualization can be found [here](https://bl.ocks.org/rdbcasillas/a1d8def6810c6319fa118aa40aea0a8a) (you will have to click "Open" at bottom right to see the full visualization). I encourage further remixing of my code by adding X and Y axis along with some ticks. Reading the code and peaking at the dataset column names will make it obvious what X and Y axis are supposed to mean for each scatterplot. 