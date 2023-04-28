<script>
	import Footer from './Footer.svelte';
	import '../styles/app.css';
</script>

<svelte:head>
	<!-- <meta name="theme-color" content="{currentAccentColor.themeHexCode}" />
	<link rel="icon" href="/favicon/lonnie-favicon-{currentAccentColor.name}.png" /> -->
</svelte:head>

<div class="circle-wrapper">
    <div class="circle" style="order: 1;"></div>
    <div class="circle" style="order: 2;"></div>
    <div class="circle" style="order: 3;"></div>
    <div class="circle" style="order: 4;"></div>
    <div class="big-circle"></div>
</div>

<main>
    <slot/>
</main>

<Footer />

<style>
    .circle-wrapper {
        position: fixed;
        top: -50px; right: 0; bottom: 0; left: 0;
        margin: auto;
        height: 100px;
        width: 100%;
        display: flex;
        justify-content: space-evenly;
        flex-flow: row wrap;
        gap: 20px;
    }
    
    .circle {
        display: flex;
        height: 100px;
        width: 100px;
        min-height: 100px;
        min-width: 100px;
        border-radius: 100%;
        background-color: white;
        -webkit-animation: circleAnimationOne ease 0.50s;
        -moz-animation: circleAnimationOne ease 0.50s;
        -ms-animation: circleAnimationOne ease 0.50s;
        -o-animation: circleAnimationOne ease 0.50s;
            animation: circleAnimationOne ease 0.50s;
        animation-iteration-count: 1;
        animation-fill-mode: forwards;
        visibility: hidden;
    }

    .circle-wrapper div:nth-child(1) { animation-delay: 0.2s }
    .circle-wrapper div:nth-child(2) { animation-delay: 0.65s }
    .circle-wrapper div:nth-child(3) { animation-delay: 1.10s }
    .circle-wrapper div:nth-child(4) { animation-delay: 1.55s }
    .circle-wrapper div:nth-child(5) { animation-delay: 2.05s }
    .circle-wrapper div:nth-child(6) { animation-delay: 2.05s }

    .big-circle {
        display: flex;
        order: 5;
        height: 100px;
        width: 100px;
        min-height: 100px;
        min-width: 100px;
        border-radius: 100%;
        background-color: white;
        -webkit-animation: circleAnimationTwo ease 4.00s;
        -moz-animation: circleAnimationTwo ease 4.00s;
        -ms-animation: circleAnimationTwo ease 4.00s;
        -o-animation: circleAnimationTwo ease 4.00s;
            animation: circleAnimationTwo ease 4.00s;
        animation-iteration-count: 1;
        animation-fill-mode: forwards;
        transition: 2s ease;
        visibility: hidden;
    }

    main {
        -webkit-animation: mainAnimation ease 10s;
        -moz-animation: mainAnimation ease 10s;
        -ms-animation: mainAnimation ease 10s;
        -o-animation: mainAnimation ease 10s;
            animation: mainAnimation ease 10s;
        animation-iteration-count: 1;
        animation-fill-mode: forwards;
    }

    @keyframes mainAnimation {
        0% {
            opacity: 0;
        }

        45% {
            opacity: 0;
        }

        60% {
            opacity: 1;
        }
    }

    @keyframes circleAnimationOne {
        0% {
            visibility: visible;
            opacity: 0;
        }

        50% {
            opacity: 1;
            visibility: visible;
        }

        100% {
            opacity: 1;
            visibility: hidden;
        }
    }

    @keyframes circleAnimationTwo {
        0% {
            position: fixed;
            top: calc(50% - 75px);
            left: calc(90% - 75px);
            visibility: visible;
            opacity: 0;
        }

        10% {
            position: fixed;
            top: calc(50% - 75px);
            left: calc(90% - 75px);
            opacity: 1;
        }

        60% {
            opacity: 0.5;
        }

        99% {
            position: fixed;
            top: calc(50% - 75px);
            left: calc(50% - 75px);
            transform: scale(15, 15);
            visibility: visible;
            opacity: 0;
        }

        100% {
            position: fixed;
            top: calc(50% - 75px);
            left: calc(50% - 75px);
            transform: scale(15, 15);
            visibility: hidden;
            opacity: 0;
        }
        
    }
</style>