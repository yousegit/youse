<script>
	import { page } from '$app/stores';
</script>

<header>
	<nav>
		<ul>
			<li aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/">About Me</a>
			</li>
			<li aria-current={$page.url.pathname.startsWith('/projects') ? 'page' : undefined}>
				<a href="/projects">Projects</a>
			</li>
		</ul>
	</nav>
</header>

<main>
	{#if $page.url.pathname === '/'}
	<section id="about-me">
		<div class="about-container">
			<div class="left-section">
				<div class="image-container">
					<img src="/betterpic.JPG" alt="Yousef" class="profile-image" loading="lazy" />
				</div>
				<h1>Hi, I'm Yousef</h1>
				<h2>Highschool Student</h2>
			</div>
			<div class="about-content">
				<p>
					Hello! My name is Yousef, and I have always been deeply interested in technology. Over the years, I have completed several internships and taken advanced classes such as AP Computer Science Principles and AP Computer Science A. These experiences have not only deepened my passion for technology but also equipped me with valuable skills. As I look towards the future, I plan to study computer science at university to further my knowledge and contribute to this exciting field.
				</p>
				<p>
					Beyond my academic pursuits, I'm a high school senior. I'm a member of both the varsity swim and cross country teams at my school, and I have a passion for skiing. Living in Zurich, Switzerland, I enjoy hanging out with friends, playing sports, and exploring my interests. Whether it's diving into a new hobby or just having fun, I'm always eager to make the most of my time and experiences.
				</p>
				<div class="contact-me">
					<h2>Contact Me</h2>
					<a href="https://www.linkedin.com/in/yousef-al-saleh-998564272/" target="_blank">
						<img src="/linkedin.png" alt="LinkedIn" class="linkedin-logo" loading="lazy" />
					</a>
					<a href="mailto:yousef@yousefully.com" target="_blank">
						<img src="/email.png" alt="Email" class="email-logo" loading="lazy" />
					</a>
				</div>
			</div>
		</div>
	</section>

	<section id="skills">
		<div class="skills-container">
			<h2>Skills</h2>
			<ul>
				<li>JavaScript</li>
				<li>Python</li>
				<li>Java</li>
				<li>HTML & CSS</li>
				<li>Adobe Premiere Pro</li>
				<li>Critical thinking</li>
				<li>Teamwork</li>
				<li>Problem-solving</li>
			</ul>
		</div>
	</section>

	<section id="interests">
		<div class="interests-container">
			<h2>Interests</h2>
			<p>I have a passion for skiing, swimming, and cross country running. In my free time, I enjoy exploring new technologies, coding personal projects, and spending time with friends. Living in Zurich, I also love to take advantage of the beautiful outdoor opportunities available in Switzerland. Additionally, I am very interested in fashion and streetwear, often keeping up with the latest trends and styles.</p>
		</div>
	</section>

	<section id="timeline">
		<div class="timeline-container">
			<h2>My Journey</h2>
			<ul>
				<li>
					<span>2022</span>
					<p>Took first computer science class (AP Computer Science Principles)</p>
				</li>
				<li>
					<span>2023</span>
					<p>Completed AP Computer Science A</p>
					<p>Started interning at Hebbian</p>
				</li>
				<li>
					<span>2024</span>
					<p>Started interning at Thomson Reuters</p>
					<p>Started interning at Liip AG</p>
				</li>
				<li>
					<span>2025</span>
					<p>Expected to graduate in the summer</p>
				</li>
			</ul>
		</div>
	</section>
	{/if}

	{#if $page.url.pathname.startsWith('/projects')}
	<section id="projects">
		<div class="projects-container">
			<h1>Coming soon...</h1>
		</div>
	</section>
	{/if}
</main>

<style>
	/* Set the overall background color */
	body {
		font-family: sans-serif;
		margin: 0;
		background-color: #E0DFE0; /* Overall background color */
		min-height: 100vh;
		scroll-behavior: smooth; /* Smooth scrolling */
	}

	header {
		display: flex;
		justify-content: center;
		align-items: center;
		background: url('colores.png') no-repeat center center/cover; /* Parallax background */
		padding: 0;
		box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
		position: sticky;
		width: 100%;
		top: 0;
		z-index: 1000;
	}

	nav {
		display: flex;
		justify-content: center;
		align-items: center;
		width: auto;
		background-color: rgba(224, 223, 224, 0.8); /* Semi-transparent nav background */
		padding: 1em 0;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
		backdrop-filter: blur(5px); /* Background blur */
	}

	ul {
		display: flex;
		justify-content: center;
		align-items: center;
		list-style: none;
		margin: 0;
		padding: 0;
	}

	li {
		position: relative;
		margin: 0 2em;
	}

	li[aria-current='page']::before {
		--size: 6px;
		content: '';
		width: 0;
		height: 0;
		position: absolute;
		top: 0;
		left: calc(50% - var(--size));
		border: var(--size) solid transparent;
		border-top: var(--size) solid var(--color-theme-1);
	}

	nav a {
		display: flex;
		align-items: center;
		padding: 0 1rem;
		color: var(--color-text);
		font-weight: 600;
		font-size: 1rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.3s ease, transform 0.3s ease;
	}

	nav a:hover {
		color: var(--color-theme-1);
		transform: scale(1.1) translateY(-3px); /* Scale and move up on hover */
		text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.2); /* Add text shadow on hover */
	}

	/* About Me section styling */
	#about-me {
		display: flex;
		justify-content: center;
		align-items: center;
		padding: 2em 1em;
		margin-top: 4em; /* Adjust according to the header height */
		background-color: #E0DFE0; /* Change About Me section background color */
	}

	.about-container {
		display: flex;
		align-items: flex-start;
		max-width: 1500px;
		width: 100%;
		margin-left: 0em; /* Move the content to the left */
		opacity: 0;
		transform: translateY(20px);
		animation: fadeInUp 1s forwards;
	}

	@keyframes fadeInUp {
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	.left-section {
		display: flex;
		flex-direction: column;
		align-items: center;
		margin-right: 2em;
		transform: translateY(-40px); /* Move the image 40px up */
	}

	.image-container {
		width: 500px; /* Adjust the size as needed */
		height: 500px;
		overflow: hidden;
		border-radius: 40px;
		margin-bottom: 0.5em; /* Reduce the margin to bring text closer */
		box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
		transition: transform 0.3s ease, box-shadow 0.3s ease; /* Smooth transition */
	}

	.image-container:hover {
		transform: scale(1.05); /* Slight zoom on hover */
		box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2); /* Enhanced shadow on hover */
	}

	.profile-image {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.left-section h1 {
		font-size: 3em; /* Make the text larger */
		margin: 0.2em 0; /* Reduce margin to bring closer to image */
		text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.2); /* Add text shadow */
	}

	.left-section h2 {
		font-size: 1.5em; /* Smaller text */
		color: gray;
		margin: 0;
		text-shadow: 1px 1px 4px rgba(0, 0, 0, 0.2); /* Add text shadow */
	}

	.about-content {
		flex: 1;
		padding-left: 2em; /* Move the text a bit to the right */
	}

	.about-content p {
		font-size: 1.2em;
		line-height: 1.6;
		margin-top: 1em;
		text-shadow: 1px 1px 4px rgba(0, 0, 0, 0.1); /* Add text shadow */
	}

	.contact-me {
		margin-top: 6em; /* Move the Contact Me section lower */
		text-align: center;
	}

	.contact-me h2 {
		font-size: 2em;
		margin-bottom: 0.5em;
	}

	.linkedin-logo,
	.email-logo {
		width: 64px; /* Make the logos bigger */
		height: 64px;
		transition: transform 0.3s ease, filter 0.3s ease; /* Smooth transition */
		margin: 0 1em; /* Add space between the logos */
	}

	.linkedin-logo:hover,
	.email-logo:hover {
		transform: rotate(360deg) scale(1.2); /* Rotate and scale up on hover */
		filter: brightness(1.2); /* Brighten on hover */
	}

	/* Skills section styling */
	#skills {
		padding: 2em 1em;
		background-color: #f7f7f7;
		text-align: center;
	}

	.skills-container {
		max-width: 1000px;
		margin: 0 auto;
	}

	.skills-container h2 {
		font-size: 2.5em;
		margin-bottom: 1em;
	}

	.skills-container ul {
		list-style: none;
		padding: 0;
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
	}

	.skills-container li {
		background-color: #e0e0e0;
		margin: 0.5em;
		padding: 0.5em 1em;
		border-radius: 5px;
	}

	/* Interests section styling */
	#interests {
		padding: 2em 1em;
		background-color: #e0e0e0;
		text-align: center;
	}

	.interests-container {
		max-width: 1000px;
		margin: 0 auto;
	}

	.interests-container h2 {
		font-size: 2.5em;
		margin-bottom: 1em;
	}

	/* Timeline section styling */
	#timeline {
		padding: 2em 1em;
		background-color: #f7f7f7;
		text-align: center;
	}

	.timeline-container {
		max-width: 1000px;
		margin: 0 auto;
	}

	.timeline-container h2 {
		font-size: 2.5em;
		margin-bottom: 1em;
	}

	.timeline-container ul {
		list-style: none;
		padding: 0;
	}

	.timeline-container li {
		background-color: #e0e0e0;
		margin: 1em;
		padding: 1em;
		border-radius: 5px;
		flex: 1;
		max-width: 250px;
	}

	.timeline-container span {
		font-weight: bold;
		display: block;
		margin-bottom: 0.5em;
	}

	/* Projects section styling */
	#projects {
		display: flex;
		justify-content: center;
		align-items: center;
		padding: 2em 1em;
		background-color: #E0DFE0; /* Match the background color */
		min-height: 50vh; /* Ensure the section has some height */
	}

	.projects-container {
		text-align: center;
	}

	.projects-container h1 {
		font-size: 2.5em;
		color: gray;
		text-shadow: 1px 1px 4px rgba(0, 0, 0, 0.1); /* Add text shadow */
	}

	/* Section divider */
	.divider {
		width: 100%;
		height: 100px;
		background: url('divider.svg') no-repeat center center/contain;
		animation: slideIn 1s ease-out;
	}

	@keyframes slideIn {
		from {
			transform: translateX(-100%);
			opacity: 0;
		}
		to {
			transform: translateX(0);
			opacity: 1;
		}
	}
</style>
