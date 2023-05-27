<template>
	<div class="card-container">
		<article class="card-location">
			<div class="card-location__subtitle">
				<div class="card-location__text">
					<h1 class="card-location__head text">FREE DELIVERY</h1>
				</div>
				<div class="card-location__size picture">
					<img class="card-location__picture" src="~/assets/svg/cube.svg" alt="" />
				</div>
			</div>
			<div class="card-location__contact">
				<p class="card-location__information">Call to order</p>
				<a class="card-location__number" href="#">0700 600 0000</a>
			</div>
			<section class="card-location__content">
				<div class="card-location__logotip">
					<img class="card-location__brend" src="~/assets/svg/logotip.svg" alt="Logotip" />
				</div>
				<div class="card-location__button">
					<a class="card-location__link" href="#">Buy now</a>
				</div>
				<div class="swiper-container">
					<div class="swiper-wrapper">
						<div v-for="card in cards" :key="card.id" class="swiper-slide card-location__product">
							<div class="card-locatino__presentation">
								<img class="card-locatino__imaging" :src="card.image" :alt="card.title" />
								<div class="card-locatino__information">
									<p class="card-locatino__names">{{ card.title }}</p>
								</div>
								<a class="card-location__bay" href="">Добавить в корзину</a>
							</div>
						</div>
					</div>
				</div>
			</section>
		</article>
	</div>
</template>

<script setup>
import Swiper from "swiper";
import "swiper/swiper-bundle.css";

const { data: cards } = await useFetch(`https://fakestoreapi.com/products`);

onMounted(() => {
	new Swiper(".swiper-container", {
		slidesPerView: 1,
		spaceBetween: 150,
		navigation: {
			nextEl: ".swiper-button-next",
			prevEl: ".swiper-button-prev"
		}
	});
});
</script>

<style lang="sass" scoped>
@import '~/assets/css/style.css'
@import url('https://fonts.googleapis.com/css2?family=Archivo+Black&display=swap')
@import url('https://fonts.cdnfonts.com/css/sf-pro-display')

.card-location
  width: 506px
  height: 900px
  background-color: #F19E38

.card-container
  max-width: 506px
  margin: 0 auto
  background-color: #000

.swiper-container 
  width: 286px
  margin: 0 auto

.card-location__text
  position: relative
  background-color: #D35A35
  width: 384px
  height: 70px
  left: 3%

.card-location__subtitle
  display: flex
  justify-content: space-between
  align-items: center

.card-location__head
  font-family: 'Archivo Black', sans-serif
  font-size: 40px
  color: #fff
  padding: 13px 0px 0 8px

.card-location__size
  position: relative
  top: 9%

.card-location__picture
  position: relative
  width: 112px
  height: 128px

.card-location__contact
  position: relative
  background-color: #B6DDEF
  bottom: 1%

.card-location__information
  font-family: 'SF Pro Display'
  font-size: 18px
  font-weight: 700
  text-align: center
  padding: 12px 0 12px 0

.card-location__number
  font-family: 'SF Pro Display'
  font-size: 32px
  display: block
  font-weight: 700
  text-align: center
  padding: 0 0 20px 0

.card-location__logotip
  width: 481px
  height: 118px
  background-color: #fff
  display: flex
  align-items: center
  justify-content: center
  border-radius: 24px
  margin: 14px 12px 20px 12px
  cursor: pointer

.card-location__brend
  width: 283px
  height: 52px

.card-location__product
  background-color: #fff
  width: 279px
  height: 418px
  margin: 0 auto 8px

.card-locatino__imaging
  width: 250px
  height: 25

.card-location__link
  width: 481px
  height: 79px
  background-color: #DC5832
  margin: 0 12px 0 13px
  border-radius: 10px
  &__::hover
   color: #5A5A5A
   background-color: #FF6347
   box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3)

.card-location__button
  margin-top: 7px

.card-location__link
  font-family: 'SF Pro Display'
  color: #fff
  font-size: 32px
  display: block
  font-weight: 700
  text-align: center
  padding: 21px 0 21px 0

.card-location__contant
 display: flex

.card-locatino__presentation
  padding: 6px 12px 6px 12px

</style>
