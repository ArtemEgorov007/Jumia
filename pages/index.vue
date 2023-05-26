<template>
	<div class="card-container">
		<article class="card-location">
			<div class="card-location__subtitle">
				<div class="card-location__text">
				<h1 class="card-location__head text">FREE DELIVERY</h1>
				</div>
				<img src="~/assets/svg/cube.svg" alt="" />
			</div>
			<section class="card-location__content">
				<div class="card-location__contact">
					<!-- Здесь размещаете строку для звонка, логотип и кнопку -->
				</div>
				<div class="card-location__logotip">
					<!-- Здесь размещаете строку для звонка, логотип и кнопку -->
				</div>
				<div class="card-location__product">
					<!-- Здесь размещаете содержимое карточки товара -->
				</div>
			</section>
		</article>
	</div>
</template>

<script>
export default {
	setup() {
		return {};
	}
};
</script>

<style lang="sass" scoped>
@import '~/assets/css/style.css'
@import url('https://fonts.googleapis.com/css2?family=Archivo+Black&display=swap')

.card-location
  width: 506px
  height: 900px
  background-color: #F19E38

.card-container
  max-width: 500px
  margin: 0 auto


.card-location__text
  background-color: #D35A35
  height: 70px
  width: 384px
  margin: 23px 0 0 18px

.card-location__subtitle
  display: flex
  justify-content: space-between
  align-items: center

.card-location__head
  font-family: 'Archivo Black', sans-serif
  font-size: 40px
  color: #fff
  padding: 13px 0 0 13px

.card-location__content
  display: flex
  flex-direction: column
  justify-content: space-between
  height: 100%

.card-location__contact
  /* Стили для строки звонка, логотипа и кнопки */

.card-location__product
  /* Стили для содержимого карточки товара */
</style>
