---
layout: default
---

![Version](https://img.shields.io/badge/Website Version-0.3-orange.svg)

## Welcome to Blueshift Analytics


**Strategy:** Do you know how to integrate valuable data insights to your organizational strategy?

**Consulting:** Does your organization have Data Science expertise for an upcoming (or current) project?

**Education:** Can we help your organization develop fluency in the realm of Data Science?

* * *

### Tools and Skills

![Version](https://img.shields.io/badge/C++-11-blue.svg)

```c++
if (runtimeIsCrucial == true){
    printf("C++ is our go to language\n");
}
```

![Version](https://img.shields.io/badge/Python-2.7-green.svg) ![Version](https://img.shields.io/badge/Tensorflow-0.12-yellow.svg)

```python
if (prototypingModels == True):
    print("Python is hard to beat when it comes to quick prototyping") 
```


* * *

<style>

.hexagon {
  stroke: #000;
  stroke-width: 0.5px;
}

</style>
<svg width="480" height="250"></svg>
<script src="https://d3js.org/d3.v4.min.js"></script>
<script src="https://d3js.org/d3-hexbin.v0.2.min.js"></script>
<script>

var svg = d3.select("svg"),
    margin = {top: 20, right: 20, bottom: 30, left: 40},
    width = +svg.attr("width") - margin.left - margin.right,
    height = +svg.attr("height") - margin.top - margin.bottom,
    g = svg.append("g").attr("transform", "translate(" + margin.left + "," + margin.top + ")");

var randomX = d3.randomNormal(width / 2, 80),
    randomY = d3.randomNormal(height / 2, 80),
    points = d3.range(2000).map(function() { return [randomX(), randomY()]; });

var color = d3.scaleSequential(d3.interpolateLab("white", "steelblue"))
    .domain([0, 20]);

var hexbin = d3.hexbin()
    .radius(10)
    .extent([[0, 0], [width, height]]);

var x = d3.scaleLinear()
    .domain([0, width])
    .range([0, width]);

var y = d3.scaleLinear()
    .domain([0, height])
    .range([height, 0]);

g.append("clipPath")
    .attr("id", "clip")
  .append("rect")
    .attr("width", width)
    .attr("height", height);

g.append("g")
    .attr("class", "hexagon")
    .attr("clip-path", "url(#clip)")
  .selectAll("path")
  .data(hexbin(points))
  .enter().append("path")
    .attr("d", hexbin.hexagon())
    .attr("transform", function(d) { return "translate(" + d.x + "," + d.y + ")"; })
    .attr("fill", function(d) { return color(d.length); });

g.append("g")
    .attr("class", "axis axis--y")
    .call(d3.axisLeft(y).tickSizeOuter(-width));

g.append("g")
    .attr("class", "axis axis--x")
    .attr("transform", "translate(0," + height + ")")
    .call(d3.axisBottom(x).tickSizeOuter(-height));

</script>
