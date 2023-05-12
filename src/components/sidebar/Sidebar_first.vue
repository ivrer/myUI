<!-- sidebar 透明毛玻璃，响应式， -->

<template>
      <div class="container">
        <nav>
            <div class="brand">
                <img src="./images/avatar.png" alt="...">
                <p>
                    <span>Hello world</span>
                    <span>ivrer</span>
                </p>
            </div>
            <hr class="line">
            <ul class="list">
                <li class="active">
                    <i class="iconfont icon-home"></i>
                    <span>Dashboard</span>
                </li>
                <li>
                    <i class="iconfont icon-exit"></i>
                    <span>Accounts</span>
                </li>
                <li>
                    <i class="iconfont icon-doc"></i>
                    <span>Orders</span>
                </li>
                <li>
                    <i class="iconfont icon-data"></i>
                    <span>Charts</span>
                </li>
                <li>
                    <i class="iconfont icon-telephone"></i>
                    <span>Support</span>
                </li>
                <hr class="line">
                <li>
                    <i class="iconfont icon-people"></i>
                    <span>Logout</span>
                </li>

            </ul>

        </nav>

      </div>
</template>

<script>
import "./style/iconfont.css"
export default {

}
</script>

<style scoped>

@keyframes fadeIn {
    to{
        opacity: 1;
        transform: translateX(0);
    }
    
}

.container {
    height: 600px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: url('./images/bg.png');
    background-repeat: no-repeat;
    background-position: bottom;
}
.container nav {
    width: 100px;
    /* height: min-content; */
    height: inherit;
    padding: 10px;
    border-radius: 12px;
    backdrop-filter: blur(18px);
    background: rgba(230, 235, 240, .7);
    border: 1px solid rgba(230, 235, 240, .7);
    box-shadow: 0 0 30px rgba(0, 0, 0, .05);
    /* transition: .6s cubic-bezier(0.8, 0.5, .5, .8); */
    transition: 0.5s cubic-bezier(0.5,0.1,0.7,0.8);
    box-sizing: border-box;


}
.container nav:hover {
    width: 320px;
}

nav .brand {
    width: 100%;
    display: flex;
    align-items: center;
}
nav .brand img {
    width: 65px;
    border-radius: 50%;
    border: 2px solid rgba(230, 235, 240, .8);
}
nav .brand p {
    color: #505257;
    font-weight: 500;
    font-style: italic;
    text-align: left;
    line-height: 22px;
    margin: 0 0 0 12px;
    opacity: 0;
    pointer-events: none;
    transform: translateX(20px);
}
nav .brand p span {
    color: #3c3e43;
    display: block;
    font-size: 26px;
    font-style: normal;
    white-space: nowrap;
    overflow: hidden;
}

nav:hover p{
    animation: fadeIn 0.5s linear forwards;
}

nav .line {
    width: 100%;
    height: 2px;
    margin: 20px 0;
    border-radius: 30%;
    background: #87a3af;
}

nav .list {
    width: 100%;
}
nav ul{
   padding: 0;
   margin: 0;
   list-style: none;

}


nav .list li {
    display: flex;
    margin: 12px 0;
    padding: 20px;
    cursor: pointer;
    border-radius: 8px;
    transition: .4s ease-in-out;
}

nav .list li:hover {
    background: rgba(230, 235, 240, .4);
}

nav .list li.active {
    background: #3681f6;
}

nav .list span {
    opacity: 0;
    pointer-events: none;
    transform: translateX(20px);
}
nav .list li.active span {
    color: #fff;
}

nav:hover .list span{
    animation: fadeIn 0.5s linear forwards;
}

nav .list i {
    font-size: 20px;
    background: linear-gradient(
        -135deg,
        #3c3e43,
        #838487
    );
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

nav .list span {
    color: #505257;
    font-size: 18px;
    font-weight: 500;
    margin: 0 0 0 12px;
}

</style>
