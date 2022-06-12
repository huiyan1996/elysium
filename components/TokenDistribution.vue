<template>
    <div class="bg-middle py-4">
        <h1 class="text-center text-white mt-4 mb-3">
            <b>Token Distribution</b>
        </h1>

        <div class="container">
            <!-- <div class="row justify-content-center">
                <div class="col-md-8">
                    <svg viewBox="0 0 64 64" class="pie">
                        <svg style="font-size: 2px;">
                            <circle r="25%" cx="50%" cy="50%" style="stroke-dasharray: 6.75 100">
                            </circle>
                            <text x="70%" y="57%">Dev (6.75%)</text>
                        </svg>
                        <svg style="font-size: 2px;">
                            <circle r="25%" cx="50%" cy="50%" style="stroke-dasharray: 15 100; stroke: green; stroke-dashoffset: -6.75; animation-delay: 0.25s">
                            </circle>
                            <text x="60%" y="70%">Team (15%)</text>
                        </svg>
                        <svg style="font-size: 2px;">
                            <circle r="25%" cx="50%" cy="50%" style="stroke-dasharray: 26.25 100; stroke: blue; stroke-dashoffset: -21.75; animation-delay: 0.5s">
                            </circle>
                            <text x="10%" y="70%" width="10px">Marketing (26.25%)</text>
                        </svg>
                        <svg style="font-size: 2px;">
                            <circle r="25%" cx="50%" cy="50%" style="stroke-dasharray: 54 100; stroke: orange; stroke-dashoffset: -48; animation-delay: 0.75s">
                            </circle>
                            <text x="45%" y="30%" width="10px">Aub (52%)</text>
                        </svg>
                    </svg>
                </div>
            </div> -->
            <div id="chartdiv"></div>
            <!-- <div class="row justify-content-center mt-3">
                <div class="col-md-8">
                    <ul class="graphItem text-white">
                        <li>Dev (6.75%)</li>
                        <li>Team (15%)</li>
                        <li>Marketing (26.25%)</li>
                        <li>Aub (52%)</li>
                    </ul>
                </div>
            </div> -->
        </div>
    </div>
</template>

<script>

export default {
  name: 'TokenDistribution',
  component: {
  },
  data() {
      return {
        chartData: [
            {display: "Dev", percentage: 6.75},
            {display: "Team", percentage: 15},
            {display: "Marketing & Collaboration", percentage: 26.25},
            {display: "Hub", percentage: 52},
        ],
      }
  },
  mounted() {
    let {am4core, am4charts, am4themes_animated, am4themes_dark} = this.$am4core();
    let chart = am4core.create("chartdiv", am4charts.PieChart);

    chart.data = this.chartData
    chart.responsive.enabled = true;

    let pieSeries = chart.series.push(new am4charts.PieSeries());
    pieSeries.dataFields.value = "percentage";
    pieSeries.dataFields.category = "display";
    pieSeries.labels.template.text = "{display}: {percentage}%";
    pieSeries.slices.template.tooltipText = "{display}: {percentage}%";
    pieSeries.labels.template.fill = am4core.color("white");
    pieSeries.slices.template.stroke = am4core.color("#72c7b7");
    // pieSeries.alignLabels = false;
    pieSeries.alignLabels = false;
    // pieSeries.labels.template.fill = am4core.color("white");

    chart.innerRadius = am4core.percent(40);
    chart.legend = new am4charts.Legend();
    chart.legend.labels.template.fill = am4core.color("#fff");
    chart.legend.valueLabels.template.fill = am4core.color("#fff"); 
  },
}
</script>

<style>
.pie {
  /* background: #f06; */
  border-radius: 50%;
}

.pie circle {
  fill: none;
  stroke: gold;
  stroke-width: 32;
  animation: rotate 1.5s ease-in;
}   

#chartdiv {
    height: 500px;
}
</style>
