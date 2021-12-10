<template>
    <div class="box" v-click-outside="hide">
        <input type="text" @focus="show">
        <div v-show="isShow ">  
            面板
        </div>
    </div>
</template>
 <<script>
 export default{
     name:'clickOutSide',
     directives: {
        clickOutside:{
            bind(el,bindings,vnode) {
                const handler = (e) => {
                    if(!el.contains(e.target)) {
                       let fn = vnode.context[bindings.expression] 
                       fn()
                    }
                }
                el.handler = handler
               document.addEventListener('click',handler)
            },
            unbind(el) {
                document.removeEventListener('click',el.hander)
            }
        }
     },
     data() {
         return {
             isShow: false
         }
     },
     methods: {
         show() {
             this.isShow = true
         },
         hide() {
             this.isShow = false
         }
     },
    
 }
 </script>

 <<style>
 .box {
     display: inline-flex;
     flex-direction: column;
     border: 1px solid red;
 }
 </style>
 