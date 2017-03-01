<template>
  <div id="app">

      <div class="topbar">
          <div class="quarter block league">
              <h6>league</h6>
              <h4>Warriors, Division 3</h4>
          </div>
          <div class="third block activeBar">
              <span>dashboard</span>
               <i class="material-icons">dashboard</i>
          </div>
      </div>

      <div class="row">
          <div class="quarter block">
              <mainMenu :menu="menu"></mainMenu>
          </div>

          <div class="quarter block column">
              <player :player="player"></player>
          </div>

          <div class="half block">
              <ppi :player="player" :division="division"></ppi>
          </div>
      </div>

      <div class="row">
          <div class="quarter">
          </div>

          <div class="quarter block">
              <tips></tips>
          </div>

          <div class="half block">
              <graph></graph>
          </div>
      </div>
  </div>
</template>

<script>
import MainMenu from './components/Menu.vue'
import Player from './components/Player.vue'
import Ppi from './components/Ppi.vue'
import Tips from './components/Tips.vue'
import Graph from './components/Graph.vue'
export default {
    name: 'app',
    components: {MainMenu, Player, Ppi, Tips, Graph},
    data () {
        return {
            player : {
                meta : {
                    name : 'Stephen Curry',
                    team : 'Golden State Warriors',
                    position: 'PG',
                    number: 30,
                    ppi : 5.67,
                    img: 'http://a.espncdn.com/combiner/i?img=/i/headshots/nba/players/full/3975.png&w=350&h=254',
                    bg: 'http://www.officialpsds.com/images/thumbs/Stephen-Curry-psd109475.png'
                }
            },
            division : {
                avgPpi : 6.12,
                bestPpi : 7.43
            },
            menu : [
                {
                    value : 'dashboard',
                    icon: 'dashboard'
                },
                {
                    value : 'scores and schedule',
                    icon: 'line_style'
                },
                {
                    value : 'teams and standings',
                    icon: 'list'
                },
                {
                    value : 'league leaders',
                    icon: 'line_weight'
                },
                {
                    value : 'account',
                    icon: 'account_circle'
                }
            ]
        }
    }
}
</script>

<style lang="stylus">
@import './stylus/resources.styl'
#app
    height 100vh
    background bgGray
    flexbox()
    flex-direction(column)
    align-items(center)
    justify-content(space-around)
    .row, .topbar
        width 80%
        grid('row','center','')
        justify-content(space-between)
        margin 0
        .block
            border-radius 4px
            background white
    .topbar
        height 7%
        min-height 66px
    .row
        height 40%
        min-width 1080px
        min-height 308px
.quarter
    cell(1,4,g:40)
    height 100%
.half
    cell(2,4,g:40)
    height 100%
.third
    cell(3,4,g:40)
    height 100%
.whole
    cell(4,4,g:40)
    height 100%

.league
    flexbox()
    flex-direction(column)
    justify-content(center)
    text-transform uppercase
    padding 0 1%
.activeBar
    flexbox()
    justify-content(space-between)
    align-items(center)
    text-transform uppercase
    font-weight 600
    font-size .9em
    padding 0 1%
</style>
