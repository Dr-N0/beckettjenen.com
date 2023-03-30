<script>
	export let programs = {
		projectName: "Apple",
		projectLink: "https://apple.com",
		projectSkills: "Software Engineering Intern",
		photoSrc: "src/assets/bryx.jpg",
		description: ""
	}
</script>

<div class="projects-card">
	<img
		src={programs.photoSrc}
		alt={`${programs.projectName}'s logo`}
		width=100px height=100px>
	<h3><a href="{programs.projectLink}">{programs.projectName}</a> | {programs.projectSkills}</h3>
	<slot/>
</div>

<style>

	.projects-card {
		display: block;
		min-height: 100px;
		margin-bottom: 50px;
	}

	h3 {
		margin-top: 10px;
		margin-bottom: 5px;
	}

	a {
		text-decoration: none;
	}

	img {
		float: left;
		border-radius: 10px;
		margin-right: 15px;
	}

	.projects-card {
		margin-bottom: 40px;
		text-align: left;
	}

	@media only screen and (max-width: 480px) {
		img {
			float: none;
			display: block;
		}
	}

</style>