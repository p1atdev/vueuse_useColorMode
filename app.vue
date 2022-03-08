<script lang="ts" setup>
const color = useColorMode({
    modes: {
        red: "red",
        blue: "blue",
    },
})

const toggleColor = () => {
    color.value = color.value === "red" ? "blue" : "red"
}
</script>

<template>
    <main>
        <button @click="toggleColor">Toggle Color</button>
        <div>
            <p>current: {{ color }}</p>

            <div v-if="color == 'red'" class="onlyForRed">This is only for red</div>
        </div>
    </main>
</template>

<style>
main {
    height: 100vh;
    margin: 0;
    padding: 0;
}

html.red {
    background: #eb2946;
}
html.blue {
    background: #52b4f7;
    color: #fafafa;
}

.onlyForRed {
    font-size: xx-large;
}
</style>
