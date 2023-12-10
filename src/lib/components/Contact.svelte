<script lang="ts">
	import type { ButtonConfig } from '$lib/types';
	import { onMount } from 'svelte';
	import OneButton from './OneButton.svelte';

	const buttonConfigs: ButtonConfig[] = [
		{
			name: 'github',
			circleColor: '#BDBDBD',
			textColor: '#868686',
			darkTextColor: '#EEEEEE',
			url: 'https://github.com/decaplanet'
		},
		{
			name: 'email',
			circleColor: '#BDBDBD',
			textColor: '#868686',
			darkTextColor: '#EEEEEE',
			url: 'mailto:deca@decaplanet.com'
		}
	];

	let displayTime = false;
	let date = new Date();

	onMount(() => {
		const interval = setInterval(() => {
			date = new Date();
		}, 1000);

		return () => {
			clearInterval(interval);
		};
	});

	$: kstTime = date.toLocaleString('en-US', {
		timeZone: 'Asia/Seoul',
		hour12: true,
		hour: 'numeric',
		minute: 'numeric'
		// second: 'numeric'
	});

	const isJsEnabled = typeof window !== 'undefined';
	if (isJsEnabled) {
		displayTime = true;
	}
</script>

<div class="center-box">
	<h1 class="center-box__heading">"If you're interested.."</h1>
	<p class="center-box__p pretendard">Feel free to check my Github and contact me via email.</p>
	{#if displayTime}
		<p class="center-box__p pretendard">
			My time zone is <span>“UTC +9 (KST) / {kstTime}”</span>.
		</p>
	{:else}
		<p class="center-box__p pretendard">
			My time zone is <span>“UTC +9 (KST)”</span>.
		</p>
	{/if}

	<div class="center-box__buttons">
		{#each buttonConfigs as button, _}
			<OneButton
				name={button.name}
				circleColor={button.circleColor}
				textColor={button.textColor}
				darkTextColor={button.darkTextColor}
				url={button.url ?? null}
			/>
		{/each}
	</div>
</div>

<style lang="scss">
	.center-box {
		align-items: center;
		display: flex;
		flex-direction: column;
		justify-content: flex-start;

		.center-box__heading {
			color: #559eff;
			font-size: 28px;
			font-weight: 650;
			letter-spacing: -0.5px;
			margin-bottom: 12px;
			text-align: center;

			@media only screen and (max-width: 650px) {
				font-size: 27px;
			}
		}

		.center-box__p {
			font-size: 13px;
			font-weight: 500;
			text-align: center;
			line-height: 1.5;

			span {
				font-weight: 700;
			}
			&:not(:last-of-type) {
				margin-bottom: 2px;
			}
			&:last-of-type {
				margin-bottom: 30px;
			}
		}

		.center-box__buttons {
			display: flex;
			flex-direction: row;
			gap: 22px;
		}
	}
</style>
