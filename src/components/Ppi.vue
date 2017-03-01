<template>
    <div id="ppi">
        <div class="header">
            <h2>quick ppi overview</h2>
        </div>
        <div class="filter">
            <span>based on the last</span>
            <div class="dropDown">
                <span>
                    20 games
                </span>
                <i class="material-icons">expand_more</i>
            </div>
        </div>
        <div class="compare">
            <div class="categories">
                <span>your ppi</span>
                <span>avg ppi, division</span>
                <span>best ppi, division</span>
            </div>
            <div class="stats">
                <span>{{player.meta.ppi}}</span>
                <span>{{division.avgPpi}}</span>
                <span>{{division.bestPpi}}</span>
            </div>
            <div class="summary">
                <div>
                    Congrats Stephen!<br /><br />
                    Your PPI score is {{player.meta.ppi}}. You are doing better than 64.32% of players in your division.
                </div>

            </div>
        </div>
    </div>
</template>
<script>
export default {
    name : 'ppi',
    props: ['player', 'division'],
    data(){
        return {
            data : false
        }
    }
}
</script>
<style lang="stylus">
@import '../stylus/resources.styl'
#ppi
    flexbox()
    flex-direction(column)
    text-transform uppercase
    height 100%
    .header
        height 16%
        flexbox()
        align-items(center)
        padding-left 2%
        border-bottom 3px solid bgGray
    .filter
        height 16%
        padding-left 2%
        flexbox()
        justify-content(space-between)
        align-items(center)
        border-bottom 1px solid bgGray
    .dropDown
        font-size .9em
        color white
        height 100%
        background oj
        padding 0 2%
        cursor pointer
        center()
    h2
        color oj
        font-weight 500
        font-size 20px
    h4
        font-weight 600
        font-size 14px
    .compare
        height 32%
        .categories
            height 40%
            grid('row','center','')
            font-size .9em
            font-weight 600
            text-align left
            color oj
            padding-left 2%
            border-bottom 1px solid bgGray
            span
                cell(1,3,g:30)
                margin 0
        .stats
            grid('row','center','')
            text-align left
            padding-left 2%
            span
                cell(1,3,g:30)
                margin 0
                color blu
                font-weight 600
                font-size 1.5em
        .summary
            padding 2%
            div
                padding 2%
                font-size .9em
                font-weight 600
                text-align center
                background bgGray
                text-transform none
                color #41515c


</style>
