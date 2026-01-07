<script>
	let open = false;
	function toggle() {
		open = !open;
	}
</script>

<nav class="nav">
	<div class="logo">Ali Store</div>

	<button class="burger" on:click={toggle} aria-label="toggle menu">
		<div></div><div></div><div></div>
	</button>

	<ul class="menu desktop">
		<li><a href="/">Home</a></li>
		<li><a href="/about">About</a></li>
		<li><a href="/services">Services</a></li>
		<li><a href="/contact">Contact</a></li>
	</ul>

	<ul class="menu mobile {open ? 'show' : ''}">
		<li><a href="/">Home</a></li>
		<li><a href="/about">About</a></li>
		<li><a href="/services">Services</a></li>
		<li><a href="/contact">Contact</a></li>
	</ul>
</nav>

<style>
	.nav {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 1rem 1.5rem;
		background: #1c1e22;
		color: #fff;
		position: relative;
	}

	.logo {
		font-size: 1.3rem;
		font-weight: bold;
	}

	/* desktop menu */
	.menu.desktop {
		display: flex;
		gap: 1.5rem;
	}
	.menu.desktop a {
		color: white;
		text-decoration: none;
		font-weight: 500;
	}

	/* hamburger */
	.burger {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		width: 22px;
		height: 18px;
		background: none;
		border: none;
		cursor: pointer;
	}
	.burger div {
		height: 3px;
		width: 100%;
		background: white;
		border-radius: 3px;
	}

	/* mobile menu */
	.menu.mobile {
		display: flex;
		flex-direction: column;
		position: absolute;
		top: 100%;
		left: 0;
		width: 100%;
		background: #222;
		padding: 1rem;
		gap: 1rem;
		transform: translateY(-10px);
		opacity: 0;
		pointer-events: none;
		transition: all .25s ease;
	}
	.menu.mobile.show {
		transform: translateY(0);
		opacity: 1;
		pointer-events: auto;
	}
	.menu.mobile a {
		color: white;
		text-decoration: none;
	}

	/* responsive */
	@media (min-width: 768px) {
		.burger { display: none; }
		.menu.mobile { display: none; }
	}
	@media (max-width: 767px) {
		.menu.desktop { display: none; }
	}
</style>
