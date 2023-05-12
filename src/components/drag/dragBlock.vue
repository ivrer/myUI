<template>
    <div class="container">

        <div class="drag" ref="dragRef">
            <div class="bg" ref="bgRef"></div>
            <div class="text" ref="textRef">{{ title }}</div>
            <div class="btn" ref="btnRef">&gt;&gt;</div>
        </div>
        
    </div>
</template>

<script setup>
import { onMounted, ref } from "vue";


    let bgRef = ref(null)
    let textRef = ref(null)
    let btnRef = ref(null)
    let check = ref(false)
    let dragRef = ref(null)
    let title = ref("拖动滑块")
    let distance 
    let originWidth

    onMounted(() => {
        let drag = dragRef.value
        let btn = btnRef.value
        distance = drag.offsetWidth - btn.offsetWidth

        btn.addEventListener("mousedown",btnMouseDown)

        document.addEventListener("mouseup",() => {      
            if(!check.value){
                bgRef.value.style.width = originWidth + "px"
                btnRef.value.style.transform = `translateX(${0+ "px"})`
                drag.removeEventListener("mousemove",dragMove)

            }else{
                title.value = "验证成功"
                bgRef.value.style.backgroundColor = "green"
                btn.removeEventListener("mousedown",btnMouseDown)
                dragRef.value.removeEventListener("mousemove",dragMove)
            }
        })

        console.log(drag.offsetLeft);

    })
    let btnMouseDown = () => {
        originWidth  = bgRef.value.offsetWidth 
        dragRef.value.addEventListener("mousemove",dragMove)
    }

    let dragMove = (e) => {
        e = e||window.event
        let way = e.clientX - dragRef.value.offsetLeft
        bgRef.value.style.width = way +"px"
        btnRef.value.style.transform = `translateX(${way + "px"})`
        if(way>=(300 - btnRef.value.offsetWidth)){
            bgRef.value.style.width = 300- btnRef.value.offsetWidth + "px"
            btnRef.value.style.transform = `translateX(${300 - btnRef.value.offsetWidth+ "px"})`
            check.value = true  
        }
    }


</script>

<style scoped>
    .container{
        
        height: 300px;
        background-color:white;
    }
    .drag{
        width: 300px;
        height: 40px;
        line-height: 40px;
        background-color: white;
        position: relative;
        margin: 0 auto;
    }
    .bg{
        width: 40px;
        height: 100%;
        position: absolute;
        background-color: #ccc;

    }
    .text{
        position: absolute;
        width: 100%;
        height: 100%;
        text-align: center;
        user-select: none;
    }
    .btn{
        width: 40px;
        height: 38px;
        position: absolute;
        border: 1px solid #ccc;
        cursor: move;
        text-align: center;
        background-color: #fff;
        color: #666;
    }
    
</style>