<template>
    <div id="tips">
        <div class="header">
            <h2>quick tips</h2>
        </div>
        <div class="contents">
            <div class="tip">
                Your three pointers are higher than your two pointers. We suggest considering settling for less three's.
            </div>
            <div class="cta primary">
                tell me more
            </div>
            <div class="cta secondary">
                want another tip?
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'tips',
    data() {
        return {
            data: false
        }
    }
}
</script>

<style lang="stylus">
@import '../stylus/resources.styl'
#tips
    flexbox()
    flex-direction(column)
    justify-content(space-between)
    height 100%
    .header
        height 16%
        flexbox()
        align-items(center)
        padding-left 4%
        border-bottom 3px solid bgGray
        text-transform uppercase
        h2
            color oj
            font-weight 500
            font-size 20px
    .contents
        grid('column','','')
        flex(1)
        height 84%
        *
            border-radius 4px
            text-align center
        .tip
            cell(2,4)
            center()
            padding 0 4%
            background bgGray
            font-size .9em
            font-weight 600
            color #41515c
        .cta
            cell(1,4)
            center()
            color white
            text-transform uppercase
            font-size .9em
            font-weight 600
            cursor pointer
        .primary
            background blu
        .secondary
            background oj
</style>
