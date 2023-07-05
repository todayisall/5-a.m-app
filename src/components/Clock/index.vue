<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref } from 'vue';

const deg = 6;

const timer = ref<Timer>(-1);
// 组件加载完成启动定时器.
onMounted(() => {
    const hr: HTMLElement | null = document.querySelector('#hr');
    const mn: HTMLElement | null = document.querySelector('#mn');
    const sc: HTMLElement | null = document.querySelector('#sc');

    // 如果空直接返回.
    if (hr === null || mn === null || sc === null) return;
    timer.value = setInterval(() => {
        let day = new Date();
        let hh = day.getHours() * 30;
        let mm = day.getMinutes() * deg;
        let ss = day.getSeconds() * deg;


        hr.style.transform = `rotateZ(${(hh) + (mm / 12)}deg)`;
        mn.style.transform = `rotateZ(${mm}deg)`;
        sc.style.transform = `rotateZ(${ss}deg)`;

    }, 500);
})


// 组件销毁前clearInterval
onBeforeUnmount(() => {
    clearInterval(timer.value)
})

</script>
<template>
    <div class="clock">

        <div class="hour">
            <div class="hr" id="hr"></div>
        </div>

        <div class="min">
            <div class="mn" id="mn"></div>
        </div>

        <div class="sec">
            <div class="sc" id="sc"></div>
        </div>

    </div>
</template>

<style lang="css" scoped>
.clock {
    display: flex;
    width: 350px;
    height: 350px;
    margin: 0 auto;
    justify-content: center;
    align-items: center;
    background: url(@/assets/clock-sam.png);
    background-size: cover;
    border: 4px solid #191919;
    border-radius: 50%;
    box-shadow: -4px -4px 10px rgba(67, 67, 67, 0.5),
        inset 4px 4px 10px rgba(0, 0, 0, 0.5),
        inset -4px -4px 10px rgba(67, 67, 67, 0.3),
        4px 4px 10px rgba(0, 0, 0, 0.3);
}

.clock:before {
    content: "";
    position: absolute;
    width: 15px;
    height: 15px;
    background: #747474;
    border-radius: 50%;
    z-index: 999;

}

.clock .hour,
.clock .min,
.clock .sec {
    position: absolute;
}

.clock .hour,
.hr {
    width: 160px;
    height: 160px;
}

.clock .min,
.mn {
    width: 190px;
    height: 190px;
}

.clock .sec,
.sc {
    width: 230px;
    height: 230px;
}

.hr,
.mn,
.sc {
    display: flex;
    justify-content: center;
    /*align-items: center;*/
    position: absolute;
    border-radius: 50%;

}

.hr:before {
    content: "";
    position: absolute;
    width: 8px;
    height: 80px;
    background: #ffb510;
    z-index: 9;
    border-radius: 6px 6px 0 0;
}

.mn:before {
    content: "";
    position: absolute;
    width: 4px;
    height: 90px;
    background: #8b8b8b;
    z-index: 10;
    border-radius: 6px 6px 0 0;
}

.sc:before {
    content: "";
    position: absolute;
    width: 2px;
    height: 150px;
    background: #e5e5e5;
    z-index: 11;
    border-radius: 6px 6px 0 0;
}
</style>