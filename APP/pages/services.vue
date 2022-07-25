<template>
  <div >
    <navbars />
    <Carousel>
      <CarouselSlide v-for="post in posts" :key="post.key"
        ><img
          :src="require('~/assets/carouselPosts/post_'+post.key+'.JPG')"
          alt="img"
          class="carouselPost"
      />
      <p v-html="post.text" class="carouselText"></p></CarouselSlide>
    </Carousel>
      <h1 class="titreServices">Services</h1>
      
      <!-- <Services /> -->
    
  </div>
</template>

<script>
export default{
  data: function () {
    return {
      posts: [
        {
          key: 1,
          text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam dolorum debitis doloremque maiores architecto ut perferendis error incidunt neque, magni eligendi sint a, mollitia esse rem eveniet beatae laborum fugiat."
        },
        {
          key: 2,
          text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam dolorum debitis doloremque maiores architecto ut perferendis error incidunt neque, magni eligendi sint a, mollitia esse rem eveniet beatae laborum fugiat."
        },
        {
          key: 3,
          text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam dolorum debitis doloremque maiores architecto ut perferendis error incidunt neque, magni eligendi sint a, mollitia esse rem eveniet beatae laborum fugiat."
        },
      ]
    }
  }
}

</script>
<style></style>