<template>
	<header class="header grid" :class="{ fixed: isMenuOpen }">
		<nav class="nav__bar">
			<section class="branding">
				<AppLink :to="{ name: 'home' }">
					<img src="@/assets/images/logo.svg" alt="Insure homepage" />
				</AppLink>
			</section>
			<!-- mobile -->
			<section class="overlay grid" v-if="isMenuOpen">
				<ul class="nav__list">
					<li class="nav__item">
						<AppLink :to="{ name: 'about' }" class="nav__link">
							How we work
						</AppLink>
					</li>
					<li class="nav__item">
						<AppLink :to="{ name: '' }" class="nav__link"> Blog </AppLink>
					</li>
					<li class="nav__item">
						<AppLink :to="{ name: '' }" class="nav__link"> Account </AppLink>
					</li>
					<li class="nav__item">
						<AppLink :to="{ name: '' }" class="nav__link cta">
							View plans
						</AppLink>
					</li>
				</ul>
			</section>
			<!-- desktop -->
			<ul class="nav__list" v-if="!isMobile">
				<li class="nav__item">
					<AppLink :to="{ name: 'about' }" class="nav__link">
						How we work
					</AppLink>
				</li>
				<li class="nav__item">
					<AppLink :to="{ name: '' }" class="nav__link"> Blog </AppLink>
				</li>
				<li class="nav__item">
					<AppLink :to="{ name: '' }" class="nav__link"> Account </AppLink>
				</li>
				<li class="nav__item">
					<AppLink :to="{ name: '' }" class="nav__link cta">
						View plans
					</AppLink>
				</li>
			</ul>
			<div class="hamburger" v-if="isMobile">
				<Transition name="fade" appear mode="out-in">
					<button
						type="button"
						class="btn--menu"
						@click.prevent="isMenuOpen = !isMenuOpen"
						v-if="!isMenuOpen"
					>
						<img src="@/assets/images/icon-hamburger.svg" alt="open nav menu" />
					</button>

					<button
						type="button"
						class="btn--menu"
						@click.prevent="isMenuOpen = !isMenuOpen"
						v-else
					>
						<img src="@/assets/images/icon-close.svg" alt="close nav menu" />
					</button>
				</Transition>
			</div>
		</nav>
	</header>
</template>

<script>
import { ref, onMounted } from "vue";
import AppLink from "./AppLink.vue";
export default {
	name: "AppNavigation",
	components: {
		AppLink,
	},
	setup() {
		const isMenuOpen = ref(null);
		const windowWidth = ref(null);
		const isMobile = ref(null);

		const checkScreen = () => {
			windowWidth.value = window.innerWidth;
			if (windowWidth.value < 800) {
				isMenuOpen.value = false;
				isMobile.value = true;
				return;
			}
			isMenuOpen.value = false;
			isMobile.value = false;
		};
		onMounted(() => {
			checkScreen();
			window.addEventListener("resize", checkScreen);
		});

		return {
			isMenuOpen,
			isMobile,
		};
	},
};
</script>

<style scoped>
.fade-enter-from,
.fade-leave-to {
	opacity: 0;
}
.fade-enter-active,
.fade-leave-active {
	transition: all 0.3s linear;
}
header.fixed {
	position: fixed;
	width: 100%;
	left: 0;
	right: 0;
	background-color: white;
	z-index: 99;
}
.nav__bar {
	grid-column: 2;
	grid-row: 1;
	display: flex;
	justify-content: space-between;
	align-items: center;
	position: relative;
	height: 6em;
}

.overlay {
	position: fixed;
	top: 6em;
	left: 0;
	right: 0;
	height: calc(100vh - 6em);
	background-color: var(--DarkViolet);
	background-image: url(@/assets/images/bg-pattern-mobile-nav.svg);
	background-repeat: no-repeat;
	background-position: bottom;
	background-size: contain;
	z-index: 99;
	/* clip-path: polygon(0 0, 100% 0, 100% 0, 0 0); */
}
.nav__list {
	grid-column: 2;
	grid-row: 1;
	padding-top: 1.5em;
	z-index: 4;
	/* clip-path: polygon(0 0, 100% 0, 100% 0, 0 0); */
}
.nav__item + .nav__item {
	margin-top: 1em;
}
.nav__link {
	font-weight: var(--fw-md);
	padding: 1em;
	display: block;
	text-align: center;
	transition: all 0.3s linear;
}

.hamburger {
	width: 32px;
	height: 35px;
	position: relative;
}
.btn--menu {
	position: absolute;
}
@media (min-width: 800px) {
	.nav__list {
		/* clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%); */
		display: flex;
		align-items: center;
		gap: 1em;
		padding-top: 0em;
	}
	.nav__item + .nav__item {
		margin-top: 0em;
	}
	.nav__link {
		color: var(--GrayishBlue);
		font-weight: var(--fw-md);
		padding: 0.5em;
		display: block;
		text-align: center;
		text-transform: uppercase;
		letter-spacing: 1px;
		font-size: 0.9rem;
	}
	.nav__link.cta {
		border: 2px solid var(--DarkViolet);
		color: var(--DarkViolet);
		padding: 0.5em 1.5em;
	}
	.nav__link:hover {
		color: var(--DarkViolet);
	}
	.nav__link.cta::before {
		content: "";
		position: absolute;
		top: 0;
		left: -101%;
		width: 100%;
		height: 100%;
		transition: all 0.3s linear;
		background-color: var(--DarkViolet);
		z-index: -1;
	}
	.nav__link.cta:hover::before {
		left: 0%;
	}
	.nav__link.cta:hover {
		color: var(--VeryLightGray);
	}
}
</style>
