<template>
    <div id="menu">
        <div v-for="each in menu" class="item">
            <span>{{each.value}}</span>
            <i class="material-icons">{{each.icon}}</i>
        </div>
        <div id="help">
            <div>
                <span>About</span>
                <span>Help</span>
            </div>
            <i class="material-icons">help</i>
        </div>
    </div>
</template>

<script>
export default {
    name: 'menu',
    props: ['menu'],
    data() {
        return {
            data: false
        }
    }
}
</script>

<style lang="stylus">
@import '../stylus/resources.styl'
#menu
    flexbox()
    flex-direction(column)
    justify-content(space-between)
    height 100%
    background bgGray
    .item
        flexbox()
        justify-content(space-between)
        align-items(center)
        flex(1)
        margin 1px 0
        padding 0 5%
        text-transform uppercase
        font-size .8em
        font-weight 600
        background white
        cursor pointer
        &:first-of-type
            background oj !important
            color white !important
            border-top-left-radius 4px
            border-top-right-radius 4px
        &:last-of-type
            border-bottom-left-radius 4px
            border-bottom-right-radius 4px
        span
            max-width 50%
    #help
        flexbox()
        justify-content(space-between)
        align-items(center)
        flex(1)
        margin 1px 0
        padding 0 5%
        text-transform uppercase
        font-size .8em
        font-weight 600
        background white
        margin-top 10px
        color blu
        border-radius 4px
        div
            width 50%
            flexbox()
            justify-content(space-between)
            span
                cursor pointer
        i
            cursor pointer
</style>
