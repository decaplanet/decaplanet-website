<script>
	import Background from '$lib/components/Background.svelte';
	import FeaturedProjects from '$lib/components/FeaturedProjects.svelte';
	import Title from '$lib/components/Title.svelte';
	import Work from '$lib/components/Contact.svelte';
</script>

<Background />
<div class="title">
	<Title />
</div>
<div class="featured-projects">
	<FeaturedProjects />
</div>
<div class="work">
	<Work />
</div>

<style lang="scss">
	:global(body) {
		background-color: #ffffff;
		color: #7f7f7f;
		transition: background-color 0.3s;

		@media (prefers-color-scheme: dark) {
			background-color: #181817;
			color: #ffffff;
		}
	}

	.title {
		margin-top: 120px;
		margin-bottom: 260px;
	}

	.featured-projects {
		margin-bottom: 110px;
	}

	.work {
		margin-bottom: 130px;
	}
</style>
