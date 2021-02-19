<template>
    <div>
        <img v-bind:class="[ {reverse: isReversed}, fanClass ]" class="fan" src="../assets/fan.png">

        <br />

        <img class="pull-cord" @click="toggleSpeed" src="../assets/pull-cord-long.svg">
        <img class="pull-cord" @click="toggleReverse" src="../assets/pull-cord-short.svg">
    </div>
</template>

<script>
export default {
    name: 'CeilingFan',
    methods: {
        toggleSpeed() {
            const currentIndex = this.speedIndex;
            const nextIndex = (currentIndex + 1) % this.speed.length;
            this.speedIndex = nextIndex;
            this.fanClass = 'rotate-' + nextIndex;
        },
        toggleReverse() {
            this.isReversed = !this.isReversed;
        }
    },
    data: function() {
        return {
            isReversed: false,
            speed: ['Off','Low','Mid','High'],
            speedIndex: 0,
            fanClass: 'rotate-0'
        }
    }
}
</script>

<style scoped>
.pull-cord {
    width: 25px;
    height: auto;
    vertical-align: top;
    margin-left: 1em;
    margin-right: 1em;
    margin-top: 2em;
}

.pull-cord:hover {
    cursor: pointer;
}

.fan {
    width: 200px;
    height: auto;
}

.rotate-0 {
    animation: rotation 0s infinite linear;
}

.rotate-1 {
    animation: rotation 3s infinite linear;
}

.rotate-2 {
    animation: rotation 2s infinite linear;
}

.rotate-3 {
    animation: rotation 1s infinite linear;
}

.reverse {
    animation-direction: reverse;
}

@keyframes rotation {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(359deg);
  }
}
</style>
