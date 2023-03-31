<script>
	import { MetaTags } from 'svelte-meta-tags';
	import Experience from './Experience/Experience.svelte';
	import experience from './Experience/experience.json';
	import Projects from './Projects/Projects.svelte';
	import projects from './Projects/projects.json';
	import '../styles/app.css';

</script>

<MetaTags
	title="Beckett Jenen"
	description="Beckett's personal playground"
	openGraph={{
		type: "website",
		title: "Beckett Jenen",
		description: "Beckett's Corner of the Internet",
		images: [{
			url: "https://s3.csh.rit.edu/",
			width: 2400,
			height: 1260,
			alt: ""
		}]
	}}
/>

<main>
	<h1>About</h1>
	<div>
		<p>Hi I'm Beckett</p>
		<p>
			I'm a full stack developer and fourth year Computer Science Major (Computing Security Minor) at the <a id="rit-url" href="https://rit.edu" target="_blank"> Rochester Institute of Technology</a>.
		</p>
		<p>
			At RIT, I'm involved with <a id="csh-url" href="https://csh.rit.edu" target="_blank">Computer Science House</a> where I help manage our public facing websites and our <a id="blue-url" href="https://jumpstart.csh.rit.edu" target="_blank"> public facing dashboard</a>.
		</p>

		<p>Outside of work I play competitive video games, hike, practice piano, and fence for RIT!</p>

		<hr />
		
		<p>You can find me in the following places around the web:</p>
		<ul id="social-list">
			<li><img class="social-image" src="../icons/envelope-solid.svg" alt="Email"/>Email: <a class="social-text" href="mailto:beckettjenen123@gmail.com">beckett@gmail</a></li>
			<li><img class="social-image" src="../icons/github.svg" alt="GitHub"/><p class="social-text">GitHub: <a href="https://github.com/Dr-N0" target="_blank">@Dr-N0</a></p></li>
			<li><img class="social-image" src="../icons/linkedin.svg" alt="LinkedIn"/><p class="social-text">LinkedIn: <a href="https://www.linkedin.com/in/beckettjenen" target="_blank">Beckett Jenen</a></p></li>
		</ul>

		<h1>Experience</h1>
		<p>If you would prefer to view my resume, you can find that
			<a id="blue-url" href={`https://resume.com`} target="_blank">here</a>
		</p>

		<h3>A brief overview of my work experience as a Software Engineer:</h3>
		<div>
			{#each experience.companies as job}
				<Experience
					experience = {
						{
							companyName: job.companyName,
							companyWebsite: job.companyWebsite,
							jobTitle: job.jobTitle,
							photoSrc: `https://s3.csh.rit.edu/lontronix-website/${job.photoSrc}`
						}
					}
				>
				<p style="display: inline;">
					{job.description}
				</p>
				</Experience>
			{/each}
		</div>

		<h3>Some work I've done on my own:</h3>
		<div>
			{#each projects.programs as proj}
				<Projects
					programs = {
						{
							projectName: proj.projectName,
							projectLink: proj.projectLink,
							projectSkills: proj.projectSkills,
							photoSrc: `https://s3.csh.rit.edu/lontronix-website/${proj.photoSrc}`
						}
					}
				>
				<p style="display: inline;">
					{proj.description}
				</p>
				</Projects>
			{/each}
		</div>
	</div>
</main>

<style>
	.social-image, .social-text {
		vertical-align: middle;
		display: inline-block;
	}
	.social-image {
		width: 1.15em;
		height: 1.15em;
		padding-right: 0.30em;
		filter: invert(100%) sepia(100%) saturate(0%) hue-rotate(139deg) brightness(103%) contrast(101%);
	}
	.social-text {
		margin: 0;
	}
	#social-list li {
		align-items: center;
		vertical-align: middle;
		padding-top: 10px;
	}
	#social-list {
		list-style: none;
		padding-inline-start: 20px;
		margin-block-end: 32px;
	}

	#rit-url {
		text-decoration: underline;
		text-decoration-color: orange;
		text-underline-offset: 2.0px;
		text-decoration-thickness: 0.15em;
		text-decoration-skip-ink: none;
	}
	#csh-url {
		text-decoration: underline;
		text-decoration-color: #B0197E;
		text-underline-offset: 2.0px;
		text-decoration-thickness: 0.15em;
		text-decoration-skip-ink: none;
	}
	#blue-url {
		text-decoration: underline;
		text-decoration-color: #1FA4DB;
		text-underline-offset: 2.0px;
		text-decoration-thickness: 0.15em;
		text-decoration-skip-ink: none;
	}

	@media (prefers-color-scheme: light) {
		.social-image {
			filter: invert(0%) sepia(0%) saturate(56%) hue-rotate(325deg) brightness(107%) contrast(100%);
		}
	}
</style>