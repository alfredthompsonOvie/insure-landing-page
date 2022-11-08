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

<style scoped></style>
