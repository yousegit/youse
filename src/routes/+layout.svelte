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

<slot/>

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
		background: #d0cccc no-repeat center center/cover; /* Parallax background */
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

	@keyframes fadeInUp {
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	</style>
