<template>
	<header class="header grid">
		<nav class="nav__bar">
			<div class="branding">
				<a href="#">
					<img src="@/assets/images/logo.svg" alt="Insure logo" />
				</a>
			</div>
			<ul class="nav__list">
				<li class="nav__item"><a href="#" class="nav__link">How we work</a></li>
				<li class="nav__item"><a href="#" class="nav__link">Blog</a></li>
				<li class="nav__item"><a href="#" class="nav__link">Account</a></li>
				<li class="nav__item">
					<a href="#" class="nav__link cta">View plans</a>
				</li>
			</ul>
			<div class="hamburger">
				<button class="btn--menu openMenu">
					<img src="@/assets/images/icon-hamburger.svg" alt="open nav menu" />
				</button>
				<button class="btn--menu closeMenu">
					<img src="@/assets/images/icon-close.svg" alt="close nav menu" />
				</button>
			</div>
			<div class="overlay"></div>
		</nav>
	</header>
</template>

<script>
export default {
	name: "AppNavigation",
};
</script>

<style scoped>

.nav__bar {
	grid-column: 2;
	grid-row: 1;
	display: flex;
	justify-content: space-between;
	align-items: center;
	position: relative;
	height: 6em;
}
.nav__list {
	position: absolute;
	top: 6em;
	left: 0;
	right: 0;
	padding-top: 1em;
	clip-path: polygon(0 0, 100% 0, 100% 0, 0 0);
	z-index: 4;
	@media (min-width: 768px) {
	}
}
.nav__item + .nav__item {
	margin-top: 1em;
}

.nav__link {
	font-weight: var(--fw-md);
	padding: 1em;
	display: block;
	text-align: center;
	transition: all .3s linear;
}
.nav__link:hover {
	color: var(--DarkViolet);
}
.nav__link.cta:hover {
	background-color: var(--DarkViolet);
	color: var(--VeryLightGray);
}
.overlay {
	position: fixed;
	top: 6em;
	left: 0;
	right: 0;
	height: calc(100vh - 6em);
	background-color: var(--DarkViolet);
	background-image: url(../images/bg-pattern-mobile-nav.svg);
	background-repeat: no-repeat;
	background-position: bottom;
	background-size: contain;
	z-index: 2;
	clip-path: polygon(0 0, 100% 0, 100% 0, 0 0);
}
.hamburger {
	width: 32px;
	height: 35px;
	position: relative;
}
.btn--menu {
	position: absolute;
}
</style>
