<template>
	<footer class="footer">
		<section class="footer__social">
			<RouterLink :to="{ name: '' }">
				<img src="@/assets/images/logo.svg" alt="Insure logo" />
			</RouterLink>
			<ul class="social__list">
				<li class="social__item">
					<AppLink to="https://www.facebook.com" class="social__link"> 
						<img
							src="@/assets/images/icon-facebook.svg"
							alt="facebook logo"
							class="social__link--img"
						/>
					</AppLink>
				</li>
				<li class="social__item">
					<AppLink to="https://www.twitter.com" class="social__link"> 
						<img
							src="@/assets/images/icon-twitter.svg"
							alt="twitter logo"
							class="social__link--img"
						/>
					</AppLink>
				</li>
				<li class="social__item">
					<AppLink to="https://www.pinterest.com" class="social__link"> 
						<img
							src="@/assets/images/icon-pinterest.svg"
							alt="pinterest logo"
							class="social__link--img"
						/>
					</AppLink>
				</li>
				<li class="social__item">
					<AppLink to="https://www.instagram.com" class="social__link"> 
						<img
							src="@/assets/images/icon-instagram.svg"
							alt="instagram logo"
							class="social__link--img"
						/>
					</AppLink>
				</li>
			</ul>
		</section>
		<section class="footer__nav__bar">
			<ul class="footer__nav__list">
				<li class="footer__nav__item">Our company</li>
				<li class="footer__nav__item">
					<RouterLink :to="{ name: '' }" class="footer__nav__link">How we work</RouterLink>
				</li>
				<li class="footer__nav__item">
					<RouterLink :to="{ name: '' }" class="footer__nav__link">Why Insure?</RouterLink>
				</li>
				<li class="footer__nav__item">
					<RouterLink :to="{ name: '' }" class="footer__nav__link">View plans</RouterLink>
				</li>
				<li class="footer__nav__item">
					<RouterLink :to="{ name: '' }" class="footer__nav__link">Reviews</RouterLink>
				</li>
			</ul>
			<ul class="footer__nav__list">
				<li class="footer__nav__item">Help me</li>
				<li class="footer__nav__item">
					<RouterLink :to="{ name: '' }" class="footer__nav__link">FAQ</RouterLink>
				</li>
				<li class="footer__nav__item">
					<RouterLink :to="{ name: '' }" class="footer__nav__link">Terms of use</RouterLink>
				</li>
				<li class="footer__nav__item">
					<RouterLink :to="{ name: '' }" class="footer__nav__link">Privacy policy</RouterLink>
				</li>
				<li class="footer__nav__item">
					<RouterLink :to="{ name: '' }" class="footer__nav__link">Cookies</RouterLink>
				</li>
			</ul>
			<ul class="footer__nav__list">
				<li class="footer__nav__item">Contact</li>
				<li class="footer__nav__item">
					<RouterLink :to="{ name: '' }" class="footer__nav__link">Sales</RouterLink>
				</li>
				<li class="footer__nav__item">
					<RouterLink :to="{ name: '' }" class="footer__nav__link">Support</RouterLink>
				</li>
				<li class="footer__nav__item">
					<RouterLink :to="{ name: '' }" class="footer__nav__link">Live chat</RouterLink>
				</li>
			</ul>
			<ul class="footer__nav__list">
				<li class="footer__nav__item">Others</li>
				<li class="footer__nav__item">
					<RouterLink :to="{ name: '' }" class="footer__nav__link">Careers</RouterLink>
				</li>
				<li class="footer__nav__item">
					<RouterLink :to="{ name: '' }" class="footer__nav__link">Press</RouterLink>
				</li>
				<li class="footer__nav__item">
					<RouterLink :to="{ name: '' }" class="footer__nav__link">Licenses</RouterLink>
				</li>
			</ul>
		</section>
		<div class="attribution">
			Challenge by
			<AppLink to="https://www.frontendmentor.io?ref=challenge">Frontend Mentor</AppLink>. Coded by <AppLink to="https://www.linkedin.com/in/alfredthompsonovie/">Alfred Thompson Ovie</AppLink>.
		</div>
	</footer>
</template>

<script>
import AppLink from './AppLink.vue';
export default {
	name: "AppFooter",
	components: {
		AppLink,
	}
};
</script>

<style scoped></style>
