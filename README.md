# my-popupbox

> A Vue.js project
## 该插件包含了message，tooltip，confirm，dialog应用；
## 应用该插件，需首先在项目中引入：
```
import Vue from 'vue'
import vDialogJf from '../../node_modules/vue-dialog-jf/index.js'
Vue.use(vDialogJf)
```
### message使用方式
```
this.$v_message({
        message:'this is message',
        time:5000
      })
```
<table>
    <tr>
    <td>参数名称</td>
      <td>类型</td>
      <td>默认值</td>
      <td>描述</td>
  </tr>
   <tr>
    <td>message</td>
      <td>String</td>
      <td>-</td>
      <td>显示的信息</td>
  </tr>
    <tr>
    <td>time</td>
      <td>Numkber</td>
      <td>-</td>
      <td>提示信息显示的时间</td>
  </tr>
  </table>
  
### message使用方式
```
this.$v_confirm({
        title:'确认',
        width:'300px',
        height:'200px',
        content:'this is my confirm '
      },function(){
          alert('ok');
      },function(){
          alert('cancel');
       })
```
<table>
  <tr>
      <td>参数名称 </td>
      <td>类型 </td>
      <td>默认值 </td>
      <td>描述 </td>
    </tr>
  <tr>
      <td>title </td>
      <td>String </td>
      <td>- </td>
      <td>确认框的名称 </td>
    </tr>
   <tr>
      <td>width </td>
      <td>String </td>
      <td>- </td>
      <td>确认框的宽度，示例：'300px' </td>
    </tr>
   <tr>
      <td>height </td>
      <td>String </td>
      <td>- </td>
      <td>确认框的高度，示例：'200px' </td>
    </tr>
   <tr>
      <td>content </td>
      <td>String </td>
      <td>- </td>
      <td>确认框的内容 </td>
    </tr>
   <tr>
      <td>function1 </td>
      <td>Function </td>
      <td>- </td>
      <td>点击确认后触发的函数 </td>
    </tr>
  <tr>
      <td>function2 </td>
      <td>Function </td>
      <td>- </td>
      <td>点击取消后触发的函数 </td>
    </tr>
  </table>
#### dialog使用方式

var dia = this.$v_dialog(options);

```
var dia = this.$v_dialog({
        title:'创建账号',
        width:'400px',
        height:'300px',
        multi:false,  //多步操作传true
        render:test,
        appData:{name:that.num,description:'good boy'},
        complate:function(data){
            that.num = data
        },
    }); 
```
### options参数
<table>
  <tr>
    <td>参数名称</td>
    <td>类型</td>
    <td>默认值</td>
    <td>描述</td>
  </tr>
  <tr>
    <td>title</td>
    <td>String</td>
    <td>-</td>
    <td>弹出框的头部标题</td>
  </tr>
  <tr>
    <td>width</td>
    <td>String</td>
    <td>-</td>
    <td>弹出框的宽度,示例：'600px'</td>
  </tr>
  <tr>
    <td>height</td>
    <td>String</td>
    <td>-</td>
    <td>弹出框的高度，示例：'400px'</td>
  </tr>
  <tr>
    <td>multi</td>
    <td>Boolen</td>
    <td>false</td>
    <td>是否多步弹出框</td>
  </tr>
   <tr>
    <td>appData</td>
    <td>Array</td>
    <td>-</td>
    <td>向弹出框传递的数组</td>
  </tr>
  <tr>
    <td>render</td>
    <td>modules</td>
    <td>-</td>
    <td>弹出框要显示的模板</td>
  </tr>
   <tr>
    <td>complateFun</td>
    <td>Function</td>
    <td>-</td>
    <td>弹出框点击完成时触发的函数</td>
  </tr>
  <tr>
    <td>cancelFun</td>
    <td>Function</td>
    <td>-</td>
    <td>弹出框点击取消时触发的函数</td>
  </tr>
 <table>

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
