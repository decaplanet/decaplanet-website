<div class="center-box">
	<div class="center-box__circle" />
</div>

<style lang="scss">
	.center-box {
		align-items: flex-end;
		display: flex;
		flex-direction: row;
		height: clamp(150px, 120vw, 450px);
		justify-content: center;
		overflow: hidden;
		position: absolute;
		top: 0;
		width: 100%;
		z-index: -1;

		.center-box__circle {
			aspect-ratio: 1/1;
			background: linear-gradient(180deg, rgba(217, 217, 217, 1), rgba(217, 217, 217, 0.1));
			border-radius: 50%;
			bottom: 0;
			height: 60vw;
			left: 0;
			min-height: 800px;
			min-width: 800px;
			overflow: hidden;
			right: 0;

			@media (prefers-color-scheme: dark) {
				mix-blend-mode: multiply;
				opacity: 0.2;
			}
		}
	}
</style>
