# 📈 Vue-D3-Chart

This project comprises of a Vue web app that renders a chart using the D3.js library. 

## ⚙️ Code explanation

- An svg element is added to the template
- A [data] array is created to store the data values that are rendered in the chart
- Mounted () is used to select where the chart will be rendered (svg)
- timeParse is used to convert the strings of the array date strings to JS Date objects
- The d3-scale module is used to the data values into pixels
- The d3-shape module is used to the shape that will follow a sequence of points in the chart
- The x and y axis are attached using axisBottom and axisLeft
- A path is appended to the chart, which is what draws the line according to the data that we stored in the [data] array

## 📖 Key takeaways from this project

 - Improved my knowledge of D3.js
 - Gained experience using other libraries within Vue apps

[Edit on StackBlitz ⚡️](https://stackblitz.com/edit/vue-xhyfco)
