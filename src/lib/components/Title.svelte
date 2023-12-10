<script lang="ts">
	import { base } from '$app/paths';
</script>

<div class="center-box">
	<div class="center-box__profile-picture">
		<img src="{base}/images/deca.png" alt="profile-pic" />
	</div>
	<h1 class="center-box__heading">"Hello, World!"</h1>
	<p class="center-box__p pretendard">
		I'm a self-taught programming enthusiast with a Graphic Design background.
	</p>
	<p class="center-box__p pretendard">
		I usually write programs in <span>Rust</span>,
		<span>TypeScript</span>, and Python.
	</p>
</div>

<style lang="scss">
	@keyframes floater {
		0% {
			transition: ease 0.5s;
			transform: translateY(-2px);
		}
		50% {
			transition: ease 0.5s;
			transform: translateY(10px);
		}
		100% {
			transition: ease 0.5s;
			transform: translateY(-2px);
		}
	}

	.center-box {
		align-items: center;
		display: flex;
		flex-direction: column;
		justify-content: flex-start;

		.center-box__profile-picture {
			animation: floater 6s infinite;
			border-radius: 50%;
			height: 70px;
			margin-bottom: 25px;
			position: relative;
			width: 70px;

			img {
				border-radius: inherit;
				box-shadow: 0px 20px 40px rgba(79, 146, 230, 0.5);
				max-height: 100%;
				max-width: 100%;
				position: absolute;
			}
		}

		.center-box__heading {
			color: #559eff;
			font-size: 32px;
			font-weight: 650;
			letter-spacing: -0.5px;
			text-align: center;
		}

		.center-box__p {
			font-size: 13px;
			font-weight: 500;
			padding: 0px 20px;
			text-align: center;
			line-height: 1.5;

			span {
				font-weight: 700;
			}
			&:first-of-type {
				margin-bottom: 2px;
				margin-top: 15px;
			}
		}
	}
</style>
