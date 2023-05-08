<template>
      <div class="box-container">
        <div class="box">
          <div class="switch-wrap">
            <input type="checkbox" id=switchCheckbox>
            <label for="switchCheckbox" class="switch" ref="labelRef">
            </label>
          </div>
        </div>
        <div class="title">切换</div>
    </div>
</template>

<script setup>
import { onMounted, ref } from "vue";

  let labelRef = ref(null)
  onMounted(() => {
    let el = labelRef.value
    console.log(el.getAnimations());
    console.log(el.getBoundingClientRect(),"clientRect");
    


  })

</script>

<style scoped>
  .box-container{
    display: flex;
    justify-content:center;
    background-color: red;
  }
  .box{
    width: 200px;
    height: 200px;
    background-color:white;
  }
  .switch-wrap{
    position: relative;
  }
  .switch-wrap input{
    display: none;
  }
  .switch-wrap .switch{
    display: block;
    height: 40px;
    border: 2px solid black;
    border-radius: 20px;
  }
  .switch-wrap .switch::before{
    content:"";
    width: 35px;
    height: 35px;
    border-radius: 50%;
    background-color:rgba(7, 75, 112, 0.382);
    position: absolute;
    top: 3px;
    left: 4px;
    display: block;
    /* animation: moveRight 3s linear infinite alternate; */
  }

  @keyframes moveRight {
    to{
      transform: translateX(150px);
    }
    from{
      transform: translateX(0px);
    }
  }

  .switch-wrap input:checked ~.switch::before{
     animation: moveRight 0.3s forwards linear ;
  }
  
</style>