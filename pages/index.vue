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
					<img src="~/assets/svg/logotip.svg" alt="Logotip" />
				</div>
				<div class="card-location__product">
					<div v-for="card in cards" :key="card.id">
						<div>
							<p>{{ card.title }}</p>
						</div>
						<img :src="card.image" :alt="card.title" />
						<a href="">Add to cart</a>
					</div>
				</div>
				<div class="card-location__button">
					<a class="card-location__link" href="#">Buy now</a>
				</div>
			</section>
		</article>
	</div>
</template>

<script setup>
const { data: cards } = await useFetch("/data.json");
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


.card-location__text
  position: relative
  background-color: #D35A35
  margin: 24px 0 24px 16px
  left: 5px

.card-location__subtitle
  display: flex
  justify-content: space-between
  align-items: center

.card-location__head
  font-family: 'Archivo Black', sans-serif
  font-size: 40px
  color: #fff
  padding: 13px 16px 16px 13px

.card-location__picture
  position: relative
  margin-top: 20px

.card-location__content
  display: flex
  flex-direction: column
  height: 80%

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
  height: 118px
  width: 481px
  background-color: #fff
  border-radius: 10px
  display: flex
  justify-content: center
  margin: 14px 12px 20px 12px
  cursor: pointer

.card-location__product
  background-color: #fff
  width: 279px
  height: 418px
  margin: 0 auto 8px

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



.card-location__link
  font-family: 'SF Pro Display'
  color: #fff
  font-size: 32px
  display: block
  font-weight: 700
  text-align: center
  padding: 21px 0 21px 0
</style>
