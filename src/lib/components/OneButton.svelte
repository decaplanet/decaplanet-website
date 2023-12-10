<script lang="ts">
	export let name: string;
	export let circleColor: string;
	export let textColor: string;
	export let darkTextColor: string;
	export let url: string | null;
</script>

<div
	class="one-project"
	style="
  		--circle-color: {circleColor};
  		--circle-transparent-color: {circleColor + '00'};
  		--circle-shadow-color: {circleColor + '4D'};
  		--text-color: {textColor};
		--dark-text-color: {darkTextColor};"
>
	{#if url !== null}
		<a class="one-project__container" href={url} target="_blank">
			<div class="one-project__container__circle">
				<div class="one-project__container__circle__gradient" />
			</div>
			<div class="one-project__container__text">
				{name}
			</div>
		</a>
	{:else}
		<div class="one-project__container">
			<div class="one-project__container__circle">
				<div class="one-project__container__circle__gradient" />
			</div>
			<div class="one-project__container__text">
				{name}
			</div>
		</div>
	{/if}
</div>

<style lang="scss">
	.one-project {
		.one-project__container {
			align-items: center;
			cursor: pointer;
			display: flex;
			flex-direction: row;
			justify-content: center;
			text-decoration: none;

			transform: scale(1);
			transition: all 0.2s ease-in-out;

			&:hover {
				padding: 0px 5px;
				transform: scale(1.1);

				@media only screen and (max-width: 650px) {
					padding: 0px 0px;
				}
				.one-project__container__circle {
					.one-project__container__circle__gradient {
						opacity: 0;
					}
				}
			}

			.one-project__container__circle {
				background-color: var(--circle-color);
				border-radius: 50%;
				box-shadow: 0px 20px 40px var(--circle-shadow-color);
				height: 25px;
				margin-right: 8px;
				position: relative;
				width: 25px;
				z-index: 5;

				@media (prefers-color-scheme: dark) {
					background-color: var(--dark-text-color);
					box-shadow: 0px 20px 60px var(--circle-shadow-color);
				}

				.one-project__container__circle__gradient {
					background: linear-gradient(180deg, var(--circle-color), var(--circle-transparent-color));
					border-radius: inherit;
					height: 25px;
					mix-blend-mode: multiply;
					opacity: 0.5;
					position: relative;
					transition: all 0.2s ease-in-out;
					width: 25px;
					z-index: 10;

					@media (prefers-color-scheme: dark) {
						opacity: 0.7;
						background: linear-gradient(0deg, var(--circle-color), var(--circle-transparent-color));
					}
				}
			}

			.one-project__container__text {
				color: var(--text-color);
				font-size: 14px;
				font-weight: 650;
				transition: all 0.2s ease-in-out;

				@media (prefers-color-scheme: dark) {
					color: var(--dark-text-color);
				}
			}
		}
	}
</style>
