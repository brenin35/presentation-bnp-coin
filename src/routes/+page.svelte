<script lang="ts">
	import Slides from '$lib/components/slides.svelte'
	import '../app.css'
</script>

<svelte:head>
	<title>Presentation</title>
</svelte:head>

<div class="background-animation">
	<div class="circle circle-1"></div>
	<div class="circle circle-2"></div>
	<div class="circle circle-3"></div>
	<div class="artifact artifact-1"></div>
	<div class="artifact artifact-2"></div>
	<div class="artifact artifact-3"></div>
	<div class="lines-container">
		<div class="line line-1"></div>
		<div class="line line-2"></div>
		<div class="line line-3"></div>
	</div>
</div>

<Slides />

<style>
	.background-animation {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		overflow: hidden;
		z-index: -1;
		pointer-events: none;
	}

	.circle {
		position: absolute;
		border-radius: 50%;
		filter: blur(100px);
		opacity: 0.14;
		animation-timing-function: ease-in-out;
		animation-iteration-count: infinite;
	}

	.circle-1 {
		width: 600px;
		height: 600px;
		background: radial-gradient(circle, #ff9900, #ff6b00);
		top: 15%;
		left: 5%;
		animation: float1 25s infinite;
	}

	.circle-2 {
		width: 700px;
		height: 700px;
		background: radial-gradient(circle, #ff9900, #d66d00);
		top: 50%;
		right: 10%;
		animation: float2 30s infinite;
	}

	.circle-3 {
		width: 650px;
		height: 650px;
		background: radial-gradient(circle, #ff9900, #ff8800);
		bottom: 10%;
		left: 30%;
		animation: float3 28s infinite;
	}

	/* Geometric artifacts */
	.artifact {
		position: absolute;
		opacity: 0.05;
		animation-timing-function: ease-in-out;
		animation-iteration-count: infinite;
	}

	.artifact-1 {
		width: 200px;
		height: 200px;
		border: 3px solid #ff9900;
		border-radius: 20px;
		top: 20%;
		right: 20%;
		animation: rotate-artifact 40s linear infinite;
		transform-origin: center;
	}

	.artifact-2 {
		width: 150px;
		height: 150px;
		background: linear-gradient(135deg, transparent 30%, #ff9900 30%, #ff9900 70%, transparent 70%);
		bottom: 25%;
		left: 15%;
		animation: pulse-artifact 15s ease-in-out infinite;
	}

	.artifact-3 {
		width: 180px;
		height: 180px;
		border: 2px solid #ff9900;
		border-radius: 50%;
		top: 60%;
		left: 50%;
		animation: scale-artifact 20s ease-in-out infinite;
	}

	/* Animated lines */
	.lines-container {
		position: absolute;
		width: 100%;
		height: 100%;
	}

	.line {
		position: absolute;
		background: linear-gradient(90deg, transparent, #ff9900, transparent);
		opacity: 0.05;
		animation-timing-function: ease-in-out;
		animation-iteration-count: infinite;
	}

	.line-1 {
		width: 100%;
		height: 2px;
		top: 30%;
		animation: slide-horizontal 35s infinite;
	}

	.line-2 {
		width: 2px;
		height: 100%;
		left: 60%;
		animation: slide-vertical 40s infinite;
	}

	.line-3 {
		width: 100%;
		height: 1px;
		bottom: 40%;
		animation: slide-horizontal-reverse 30s infinite;
	}

	@keyframes float1 {
		0%, 100% {
			transform: translate(0, 0) scale(1);
		}
		33% {
			transform: translate(150px, 200px) scale(1.2);
		}
		66% {
			transform: translate(-80px, 120px) scale(0.9);
		}
	}

	@keyframes float2 {
		0%, 100% {
			transform: translate(0, 0) scale(1);
		}
		33% {
			transform: translate(-180px, -150px) scale(1.25);
		}
		66% {
			transform: translate(90px, 180px) scale(0.85);
		}
	}

	@keyframes float3 {
		0%, 100% {
			transform: translate(0, 0) scale(1);
		}
		33% {
			transform: translate(120px, -180px) scale(1.15);
		}
		66% {
			transform: translate(-150px, 90px) scale(1.1);
		}
	}

	@keyframes rotate-artifact {
		0% {
			transform: rotate(0deg) scale(1);
		}
		50% {
			transform: rotate(180deg) scale(1.2);
		}
		100% {
			transform: rotate(360deg) scale(1);
		}
	}

	@keyframes pulse-artifact {
		0%, 100% {
			opacity: 0.03;
			transform: scale(1);
		}
		50% {
			opacity: 0.10;
			transform: scale(1.3);
		}
	}

	@keyframes scale-artifact {
		0%, 100% {
			transform: scale(1);
			opacity: 0.08;
		}
		50% {
			transform: scale(1.5);
			opacity: 0.10;
		}
	}

	@keyframes slide-horizontal {
		0% {
			transform: translateX(-100%);
		}
		100% {
			transform: translateX(100%);
		}
	}

	@keyframes slide-horizontal-reverse {
		0% {
			transform: translateX(100%);
		}
		100% {
			transform: translateX(-100%);
		}
	}

	@keyframes slide-vertical {
		0% {
			transform: translateY(-100%);
		}
		100% {
			transform: translateY(100%);
		}
	}
</style>