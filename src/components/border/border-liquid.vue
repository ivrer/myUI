<template>
    <div class="box-container">
        <div class="box"></div>
        <div class="title">边框水滴效果</div>
    </div>
</template>

<script>

</script>

<style scoped>
.box-container{
  display: flex;
  justify-content: center;
  background-color: #13afda ;
}
.box{
    position: relative;
    width: 300px;
    height: 300px;

    /* border: solid 1px black; */
    border-radius: 30% 70% 70% 30% / 30% 30% 70% 70% ;
    box-shadow: inset 10px 20px 30px rgba(0, 0, 0, 0.5),
                10px 20px 20px  rgba(0, 0, 0, 0.3),
                15px 15px 30px rgba(0, 0, 0, 0.05),
                inset -10px -10px 15px rgba(255, 255, 255, 0.8);
    animation: actionMove 5s linear infinite alternate;
 }

.box::after{
    content: "";
    width: 20px;
    height: 20px;
    position:absolute;
    background-color: white;
    top: 20%;
    left: 25%;
    border-radius:30% 70% 51% 49% / 30% 59% 41% 70%  ;
    animation: actionWith 3s linear infinite alternate;
    
}
.box::before{
    content: "";
    width: 10px;
    height: 15px;
    position:absolute;
    background-color: white;
    top: 30%;
    left: 23%;
    border-radius:76% 24% 30% 70% / 30% 59% 41% 70%   ;
    animation: actionWith 3s linear infinite alternate;
}
.box:hover{
    animation-play-state: paused;
}
/* 如何在伪元素上添加hover效果？ */

@keyframes actionMove {
    25%{
        border-radius: 78% 22% 17% 83% / 30% 59% 41% 70% ;
    }
    50%{
        border-radius: 51% 49% 48% 52% / 30% 42% 58% 70% ;
    }
    100%{
        border-radius: 78% 22% 79% 21% / 30% 63% 37% 70% ;
    }
}

@keyframes actionWith {
    25%{
        transform: translate(10px,10px);
    }
    50%{
        transform: translate(15px,15px);
    }
    100%{
        transform: translate(20px,20px);
    }
}
</style>