<script>
export default {
    name: 'AppLoader',
    props: ['label'],
}
</script>

<template>
    <div class="loader">
        <div class="text">{{ label }}</div>
        <svg class="a-loader" viewBox="0 0 96 96" xmlns="http://www.w3.org/2000/svg">
            <title>Loading</title>
            <circle cx="48" cy="48" r="42" />
        </svg>
        <div class="text">
            Loading...
        </div>
    </div>
</template>

<style lang="scss" scoped>
.loader {
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center;
    width: 100%;
    height: 100%;
    background-color: white;
}

.a-loader {
	animation: a-loader 4s linear infinite;
	color: black;
	fill: none;
	height: 3rem;
	stroke: currentColor;
	stroke-dasharray: 263.467529296875;
	stroke-dashoffset: 263.467529296875;
	stroke-linecap: butt;
	stroke-linejoin: miter;
	stroke-width: 10;
	vertical-align: top;
	width: 6rem;
    align-self: center;
    margin: 20px 0;
}

@keyframes a-loader {
	100% {
		stroke-dashoffset: 0;
	}
}

.text {
    text-transform: uppercase;
    letter-spacing: 2px;

}
</style>
