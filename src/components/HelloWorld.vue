<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <div>
      <button class='btn btn-default' @click='showbox'>message</button>
    </div>
    <div style = 'margin:15px'>
      <button class='btn btn-default'  @mouseout='tooltiphide($event)' @mouseenter='tooltip("right",$event)'>tooltipRight</button>
      <button class='btn btn-default'  @mouseout='tooltiphide($event)' @mouseenter='tooltip("left",$event)'>tooltipLeft</button>
      <button class='btn btn-default'  @mouseout='tooltiphide($event)' @mouseenter='tooltip("top",$event)'>tooltipTop</button>
      <button class='btn btn-default'  @mouseout='tooltiphide($event)' @mouseenter='tooltip("bottom",$event)'>tooltipBottom</button>
    </div>
    <div>
      <button class='btn btn-default'  @click='showconfirm'>confirm</button>
    </div>


    <div>
      <button class='btn btn-default'  @click='showdialog'>dialog</button>
    </div>
  </div>

</template>

<script>
import Vue from 'vue'
import kiko from '../../node_modules/kiko/index.js'
Vue.use(kiko)

import createNet from './test.vue'
import nextstep from './nextStep.vue'


export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods:{
    showbox(){
    
      this.$kiko_message({
        message:'this is message',
        time:5000
      })
    },
    tooltip(direction,$event){
      this.$kiko_tooltip($event,{
        content:'this is tooltip',
        direction: direction,
        background: '#65f',
        color: '#fff',
        time: 3000
      })
    },
    tooltiphide($event){

      this.$kiko_tooltip($event)
    },
    showconfirm(){
      this.$kiko_confirm({
        title:'确认',
        width:'300px',
        height:'200px'
      },function(){
          alert('ok')
      })
    },
    showdialog(){

      this.$v_dialog({
          title:'创建网络',
          width:'600px',
          height:'400px',
          multi:true,
          render:nextstep
      },function(){
          alert('this is ok')
      })
    }
  },
  components:{createNet,nextstep}

}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
