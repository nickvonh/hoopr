<template>
    <div id="graph">
        <div class="graph-container">

        </div>
    </div>
</template>

<script>
import RadarChart from '../graph/radar-chart.js'
import d3 from 'd3'
console.log(RadarChart)

export default {
    name: 'graph',
    props: ['player'],
    data() {
        return {
            graphData: [
                [
                    {axis: 'scoring', value:4},
                    {axis: 'handling', value:2},
                    {axis: 'iq', value:3},
                    {axis: 'athleticism', value:2.5},
                    {axis: 'defense', value:.5}
                ]
            ]
        }
    },
    mounted(){
        //Call function to draw the Radar chart
        RadarChart(".graph-container", this.graphData);
    }
}
</script>

<style lang="stylus">
@import '../stylus/resources.styl'
#graph
    height 100%
    background bgGray
    center()
.legend
    font-size 2em
    fill blu
</style>
