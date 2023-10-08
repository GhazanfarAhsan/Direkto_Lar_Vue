<template>
    <div>
        <div class="dropdown" @mouseover="show()" @mouseleave="hide()">
            <div v-if="state == 'Pendiente' && active == true">
                <span class="bg-red-500 px-2 py-[2px] mr-2"><i class="fa fa-flag text-white"></i></span>
                <span class="text-red-500"> Pendiente <i class="fa fa-chevron-down pl-2"></i></span>
            </div>
            <div v-if="state == 'Pendiente' && active == false">
                <span class="bg-gray-500 px-2 py-[2px] mr-2"><i class="fa fa-flag text-white"></i></span>
                <span class="text-gray-500"> Pendiente <i class="fa fa-chevron-down pl-2"></i></span>
            </div>
            <div v-if="state == 'Proceso'">
                <span class="bg-[#dd6b20] px-2 py-[2px] mr-2"><i class="fa fa-flag text-white"></i></span>
                <span class="text-[#dd6b20]"> Proceso <i class="fa fa-chevron-down pl-2"></i></span>
            </div>
            <div v-if="state == 'Completa'">
                <span class="bg-green-600 px-2 py-[2px] mr-2"><i class="fa fa-flag text-white"></i></span>
                <span class="text-green-600"> Completa <i class="fa fa-chevron-down pl-2"></i></span>
            </div>
        </div>
        <div class="dropdown-content" :class="dis == true ? 'block' : 'hidden'" @mouseover="show()" @mouseleave="hide()"> 
            <div v-if="state != 'Pendiente'" class="py-[2px]" @click="hide()">
                <span class="bg-red-500 px-2 py-[2px] mr-2"><i class="fa fa-flag text-white"></i></span>
                <span class="text-red-500"> Pendiente </span>
            </div>
            <div v-if="state != 'Proceso'" class="py-[2px]" @click="hide()">
                <span class="bg-[#dd6b20] px-2 py-[2px] mr-2"><i class="fa fa-flag text-white"></i></span>
                <span class="text-[#dd6b20]"> Proceso </span>
            </div>
            <div v-if="state != 'Completa'" class="py-[2px]" @click="hide()">
                <span class="bg-green-600 px-2 py-[2px] mr-2"><i class="fa fa-flag text-white"></i></span>
                <span class="text-green-600"> Completa</span>
            </div>
        </div>
    </div>
</template>
  
<script> 
export default {
    name: "dropdown-component",
    props: {
        state: String,
        active: Boolean,
    },
    data: function () {
        return {
            dis: false,
        };
    },
    methods: {
        show: function () {
           this.dis = true;
        },
        hide: function () {
           this.dis = false;
        },
    },
    components: {
    },
};
</script>
<style>
.dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-content {
  position: absolute;
  background-color: #f9f9f9;
  min-width: 110px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  padding: 5px 5px;
  z-index: 1;
}
</style>