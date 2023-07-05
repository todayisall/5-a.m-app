
<template>
    <div class="grid">
        <button class="square-lg">
            <svg class="square-lg__gradient-text" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 140 64">
                <defs>
                    <linearGradient id="grad1" x1="0%" y1="100%" x2="100%" y2="0%">
                        <stop offset="0%" stop-color="#fdff01"></stop>
                        <stop offset="20%" stop-color="#fab451"></stop>
                        <stop offset="78%" stop-color="#cb3070"></stop>
                    </linearGradient>
                </defs>
                <text fill="url(#grad1)" x="50%" y="60%" dominant-baseline="middle" text-anchor="middle">Weak Up!</text>
            </svg>
        </button>
    </div>
</template>

<style lang="css" scoped>
.grid {
    width: 100%;
    text-align: 100%;
}
button {
    font-size: 18px;
    line-height: 18px;
    padding: 0 8px;
    position: relative;
    border: 3px solid rgba(255, 255, 255, 0);
    outline: none;
    text-align: center;
    transition: all 250ms ease-in-out;
}

button:hover {
    box-shadow: none;
    border-color: rgba(67, 67, 67, 0.5);
}

button {
    box-shadow: 8px 8px 12px -2px rgba(0, 0, 0, 0.5), -6px -6px 12px -1px rgba(67, 67, 67, 0.5);
    cursor: pointer;
}

button:active {
    box-shadow: inset -4px -4px 6px -1px rgba(0, 0, 0, 0.5), inset 2px 2px 8px -1px rgba(67, 67, 67, 0.5);
    border-color: rgba(255, 255, 255, 0);
}

button>* {
    vertical-align: middle;
}

button>span:last-child {
    padding-left: 8px;
}

/* 转换为dark mode */
@media (prefers-color-scheme: dark) {
    .square-lg__gradient-text {
        fill: #fff;
    }
}

.square-lg {
    width: 84%;
    height: 180px;
    grid-row-start: 1;
    grid-row-end: 3;
    position: relative;
    border-radius: 24px;
    font-size: 64px;
    background-color: transparent;
}

.square-lg__gradient-text {
    width: 100%;
    height: 64px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
</style>