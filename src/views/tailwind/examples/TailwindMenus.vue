<template>
    <div class='pt-4 mt-4 px-1 mx-1'>
        <div> 
            <span class='text-lg font-extrabold'>menu-dark-base </span>
            <menu-dark-base />
        </div>
        <div class='pt-4 mt-4'> 
        <span class='text-lg font-extrabold'>menu-light-base </span>
        <menu-light-base/>
        </div>
        <div class='pt-4 mt-4'> 
            <span class='text-lg font-extrabold'>menu-dark-with-search </span>
            <menu-dark-with-search />
        </div>
        <div class='pt-4 mt-4'> 
            <span class='text-lg font-extrabold'>menu-light-with-search </span>
            <menu-light-with-search />
        </div>
        <div class='pt-10 mt-10 text-3xl font-extrabold text-indigo-500'> Side Menus </div>
         <div class='p-4 m-4 bg-gray-200'> 
            <span class='text-lg font-extrabold'>side-menu-expandable-light </span>
            <div class='flex grid grid-cols-4'>
            <side-menu-expandable-light />
            </div> 
        </div>
         <div class='p-4 m-4 bg-gray-200'> 
            <span class='text-lg font-extrabold'>side-menu-dark </span>
            <div class='flex grid grid-cols-4'>
            <side-menu-dark />
            </div> 
        </div>
    </div>
</template>

<script>
import MenuDarkBase from "../../../components/tailwind/menus/MenuDarkBase.vue"
import MenuDarkWithSearch from '../../../components/tailwind/menus/MenuDarkWithSearch.vue'
import MenuLightBase from "../../../components/tailwind/menus/MenuLightBase.vue"
import MenuLightWithSearch from '../../../components/tailwind/menus/MenuLightWithSearch.vue'
import SideMenuExpandableLight from '../../../components/tailwind/menus/SideMenuExpandableLight.vue'
import SideMenuDark from '../../../components/tailwind/menus/SideMenuDark.vue'
export default {
    setup () {
        return {}
    },
    components:{
        MenuDarkBase,
        MenuLightBase,
        MenuDarkWithSearch,
        MenuLightWithSearch,
        SideMenuExpandableLight,
        SideMenuDark,
    }
}
</script>

<style lang="scss" scoped>

</style>