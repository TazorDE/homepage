<script>
	import Navbar from "./components/Navbar.svelte";
	import Footer from "./components/Footer.svelte";
	import Header from "./components/Header.svelte";
	import About from "./components/About.svelte";
	import Projects from "./components/Projects.svelte";
	import Contact from "./components/Contact.svelte";

	/**
	 * -------------------- Navigation Bar --------------------
	 */
	let brand = "Malte Teichert";
	let nav_items = [
		["Home", "#"],
		["About", "#about"],
		["Experience", "#experience"],
		["Contact", "#contact"],
	];
	let github = "https://github.com/TazorDE";

	/**
	 * -------------------- Header Section --------------------
	 */
	let header_title_1 = "Hi,";
	let header_title_2 = "I'm Malte.";
	let header_title_3 = "Computer Scientist / Web Developer";

	/**
	 * -------------------- About Section --------------------
	 */
	let bio_title = "About Me";
	let skills_title = "My Skills";
	let skills = {
		Languages: [
			["JavaScript", "fab fa-js-square", 88],
			["TypeScript", "fas fa-code", 88],
			["HTML/CSS/SASS", "fab fa-html5", 90],
			["Node.js", "fab fa-node-js", 86],
			["Python", "fab fa-python", 70],
			["LaTeX", "fas fa-code", 68],
			["Java", "fab fa-java", 55],
		],
		Technology: [
			["Express", "fas fa-code", 95],
			["Websocket", "fas fa-code", 80],
			["REST", "fas fa-code", 90],
			["Server Side Rendering", "fas fa-code", 85],
			["Git/GitHub", "fab fa-git-square", 90],
			["Docker/Podman", "fab fa-docker", 85],
			["Terraform", "fas fa-code", 50],
		],
	};
	let bio =
		"I am a computer-scientist based in Germany. The main focus of my work is to create and maintain web applications. I am currently working for IBM on the Code Engine UI team. I am also working on my own projects, mainly the VTEC League Results System.";

	/**
	 * -------------------- Project Section --------------------
	 */
	let projects_title = "Work Experience / Projects";
	let projects = [
		[
			"B.Sc. Computer Science (2019-2022)",
			"Dual study at IBM and the Baden-Wuerttemberg Cooperative State University (DHBW) Stuttgart.",
			"https://www.dhbw-stuttgart.de/",
		],
		[
			"IBM Germany GmbH - Dual Study Program (2019-2022)",
			"Dual study program, main focus on cloud native development for IBM Watson Studio and IBM Code Engine.",
			"https://www.ibm.com/de-de",
		],
		[
			"VTEC League Results System (2021-present)",
			"A web application for league result display and management. The application is built with Node.js, Express and server-side rendering.",
			"https://vtec.malteteichert.de/",
		],
		[
			"GitHub - Other Projects",
			"A collection of other projects I've worked on. Mainly projects for my bachelor's degree.",
			"https://github.com/TazorDE",
		],
		[
			"More Information",
			"If you wish for more information on my projects and my work experience (CV), feel free to contact me directly.",
			"#contact",
		],
	];
	/**
	 * -------------------- Contact Section --------------------
	 */
	let contact_title = "Contact Me";
	let social = [
		["Email", "fas fa-envelope", "mailto:contact@malteteichert.de"],
		["Github", "fab fa-github", github],
		[
			"LinkedIn",
			"fab fa-linkedin",
			"https://www.linkedin.com/in/nils-malte-teichert/",
		],
	];

	/**
	 * -------------------- Theme Toggle --------------------
	 */
	let state = "dark"; // Change this to "light" to use light theme.

	let text_color = "dark";
	let bg_color = "light";

	if (state === "dark") {
		text_color = "light";
		bg_color = "dark";
	}
</script>

<main class="bg-{bg_color} text-{text_color} min-vh-100">
	<div class="bg-pattern">
		<Navbar Id="navbar" {brand} {nav_items} {github} {state} />
		<Header
			Id="#"
			{header_title_1}
			{header_title_2}
			{header_title_3}
			{state}
		/>
		<About Id="about" {bio_title} {bio} {skills_title} {skills} {state} />
		<Projects Id="experience" {projects_title} {projects} {state} />
		<Contact Id="contact" {contact_title} {social} {state} />
		<Footer Id="footer" {brand} {state} />
	</div>
</main>

<style>
</style>
