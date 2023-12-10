<script lang="ts">
	import type { ButtonConfig } from '../types.d.ts';
	import OneProject from './OneButton.svelte';

	const projects: ButtonConfig[] = [
		{
			name: 'formatto',
			circleColor: '#C39587',
			textColor: '#7C584E',
			darkTextColor: '#F5C4B3',
			url: 'https://github.com/decaplanet/formatto'
		},
		{
			name: 'discord-gpt',
			circleColor: '#78AACE',
			textColor: '#4E637C',
			darkTextColor: '#B8D6F5',
			url: 'https://github.com/decaplanet/discord-gpt'
		}
	];
</script>

<div class="center-box">
	<h1 class="center-box__heading">featured_projects();</h1>
	<div class="center-box__project-box">
		{#each projects as project, index}
			<OneProject
				name={project.name}
				circleColor={project.circleColor}
				textColor={project.textColor}
				darkTextColor={project.darkTextColor}
				url={project.url ?? null}
			/>
		{/each}
	</div>
</div>

<style lang="scss">
	.center-box {
		display: flex;
		flex-direction: column;
		justify-content: flex-start;
		align-items: center;

		.center-box__heading {
			color: #868686;
			font-size: 24px;
			font-weight: 650;
			letter-spacing: -0.5px;
			margin-bottom: 20px;

			@media (prefers-color-scheme: dark) {
				color: white;
			}

			@media only screen and (max-width: 350px) {
				font-size: 23px;
			}
		}

		.center-box__project-box {
			display: flex;
			flex-direction: row;
			gap: 18px;

			@media only screen and (max-width: 350px) {
				display: flex;
				flex-direction: column;
				gap: 14px;
			}
		}
	}
</style>
