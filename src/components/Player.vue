<template>
    <div id="player">
        <div class="item">
            <h2>Player (you)</h2>
            <i class="material-icons flip">subdirectory_arrow_left</i>
        </div>
        <div class="profile">
            <div class="meta">
                <h2>{{player.meta.name}}</h2>
                <h4>{{player.meta.team}}</h4>
            </div>
            <div class="card">
                <div class="bg" :style="{backgroundImage: 'url('+player.meta.bg+')'}">
                </div>
                <div class="number">
                    {{player.meta.number}}
                </div>
                <div class="img" :style="{backgroundImage: 'url('+player.meta.img+')'}">
                </div>
                <div class="position">
                    {{player.meta.position}}
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'player',
    props: ['player'],
    data() {
        return {
            data: false
        }
    }
}
</script>

<style lang="stylus">
@import '../stylus/resources.styl'
#player
    flexbox()
    flex-direction(column)
    justify-content(space-between)
    height 100%
    background bgGray
    .item
        flexbox()
        height 16%
        justify-content(space-between)
        align-items(center)
        margin 1px 0
        padding-left 5%
        cursor pointer
        text-transform uppercase
        font-size .8em
        background white
        border-top-left-radius 4px
        border-top-right-radius 4px
        position relative
        color oj
        border-bottom 3px solid bgGray
        &>h2
            font-weight 400
        .flip
            transform rotate(180deg)
            font-size 1.5em
            color white
            height 100%
            background oj
            padding 0 8%
            center()
    .profile
        background white
        flex(1)
        flexbox()
        flex-direction(column)
        justify-content(space-between)
        align-items(center)
        text-align center
        text-transform uppercase
        .meta
            padding 1%
            height 30%
            &>h2
                color oj
                font-weight 600
                font-size 20px
            &>h4
                font-weight 600
                font-size 14px
        .card
            flex(1)
            flexbox()
            justify-content(space-around)
            align-items(center)
            position relative
            width 100%
            padding 0 5%
            .bg
                position absolute
                right 0
                bottom 0
                height 100%
                width 100%
                z-index 1
                background-repeat no-repeat
                background-size 40%
                background-position 120% 150%
                opacity .4
            .img
                width 150px
                height 150px
                border 3px blu solid
                background-size cover
                background-position 50%
                overflow hidden
                border-radius 50%
                z-index 2
            .number,.position
                transform translateY(-150%)
                width 50px
                height 50px
                overflow hidden
                border-radius 50%
                center()
            .number
                color blu
                border 3px blu solid
            .position
                color oj
                border 3px oj solid

</style>
