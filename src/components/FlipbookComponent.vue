<template>
     <flipbook class="flipbook" :pages="pages" v-slot="flipbook"> 
        <div class="action-bar">
            <b-button class="ml-2 p-0 action-bar-button" variant="outline" @click="flipbook.flipLeft">
                <b-icon-arrow-left :class="{ disabled: !flipbook.canFlipLeft }"/>
            </b-button>
            <b-button class="ml-2 p-0 action-bar-button" variant="outline" @click="flipbook.zoomIn">
                <b-icon-zoom-in :class="{ disabled: !flipbook.canZoomIn }"/>
            </b-button>
            <span class="mr-2 ml-3 page-num">
                Page {{ flipbook.page }} of {{ flipbook.numPages }}
            </span>
            <b-button class="ml-2 p-0 action-bar-button" variant="outline" @click="flipbook.zoomOut">
                <b-icon-zoom-out :class="{ disabled: !flipbook.canZoomOut }"/>
            </b-button>
            <b-button class="ml-2 p-0 action-bar-button" variant="outline" @click="flipbook.flipRight">
                <b-icon-arrow-right :class="{ disabled: !flipbook.canFlipRight }"/>
            </b-button>
        </div>
    </flipbook>
</template>

<script>
  import flipbook from 'flipbook-vue'
  import page1 from '../assets/page1.png'
  import page2 from '../assets/page2.png'
  import page3 from '../assets/page3.png'
  import page4 from '../assets/page4.png'
  export default {
    name:"FlipbookViewer",
    data() {
      return {
        pages: [
            null,
            page1,
            page2,
            page3,
            page4
        ]
      }
    },
    components:{
        flipbook
    },
  }
</script>

<style>
.flipbook{
  width: 100%;
  height: 80vh;
}
 .flipbook .viewport{
  width:100%;
  height: calc(100% - 30px) !important; 
}
.flipbook .viewport .container{
  max-width: 100%;
}
.action-bar {
  width: 100%;
  height: 30px;
  padding: 10px 0;
  display: flex;
  justify-content: center;
  align-items: center;
}
.action-bar-button{
  height: 25px;
  width: 25px;
}
.action-bar-button .disabled{
  color:gray
}
.action-bar .page-num {
  font-size: 12px;
}
</style>