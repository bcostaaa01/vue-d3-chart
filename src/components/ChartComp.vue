<template>
  <div>
    <h1>Chart</h1>
    <svg></svg>
  </div>
</template>
<script>

import * as d3 from 'd3'

const data = [
  {data: "1-May-2022", amount: 34.5},
  {data: "2-May-2022", amount: 35.8},
  {data: "3-May-2022", amount: 38.1},
  {data: "4-May-2022", amount: 40.5},
  {data: "5-May-2022", amount: 47.4},
  {data: "6-May-2022", amount: 48.2},
  {data: "7-May-2022", amount: 60.8}
]

mounted () {
  const width = 800;
  const height = 500;
  const svg = d3.select("svg").attr("width", width).attr.("height", height);
  const g = svg.append("g");
};

const parseTime = d3.timeParse("%d-%b-%y")

const x = d3
.scaleTime()
.domain(
  d3.extent(data, function (d) {
    return d.amount
  })
)
.rangeRound([height, 0])

const line = d3.line()
.x(function (d) {
  return x(parseTime(d.date))
})
.y(function (d) {
  return d.amount
})

g.append("g")
.attr("transform", "translate(0," + height + ")")
.call(d3.axisBottom(x))

g.append("g")
.call(d3.axisLeft(y))
.append("text")
.attr("fill", "#000")
      .attr("transform", "rotate(-90)")
      .attr("y", 6)
      .attr("dy", "0.71em")
      .attr("text-anchor", "end")
      .text("Price ($)");

g.append("path")
.datum(data)
.attr("fill", "none")
.attr("stroke", "steelblue")
.attr("stroke-width", 1.5)
.attr("d", line)

export default {
  name: "ChartComp"
}
</script>
