<template>
  <Layout>
    <v-row no-gutters>
      <v-col cols="12" class="ma-0">
        <v-parallax dark src="/uploads/030.jpg" height="480">
        <template>
          <v-row
            align="center"
            justify="center"
          >
            <v-col class="text-center mt-12" cols="12" md="10" lg="6">
              <h4 class="title text-uppercase mb-3">Welcome to smoklahoma, we love providing amazing wedding catering  and barbeque inspired menus for events.</h4>
              <h1 class="title text-uppercase ">Specialists in smoke, fire &amp; beautiful food!</h1>
            </v-col>
          </v-row>
        </template>
        </v-parallax>
      </v-col>
    </v-row>
    <v-row no-gutters>
      <v-col v-for="n in 4" :key="`home-four${n}`" cols="12" sm="3" md="3" lg="3">
          <g-image :src="`/uploads/00${n}.jpg`" style="height: auto; width: 100%;" width="500" height="500" fit="contain"/>
      </v-col>
    </v-row>
    <v-row class="ma-3 flex-row-reverse" style="max-width: 1000px; margin: 0 auto !important;">
      <v-col cols="2" class="text-uppercase">
        <h1 class="overline">Contact Mark:</h1>
        <p class="title">
          01234567890
        </p>       
        <h1 class="overline">Location:</h1>
        <p class="title">Middlesbrough</p>
      </v-col>
      <v-col cols="10">
        <!-- Learn how to use images here: https://gridsome.org/docs/images -->
        <h1 class="display-2 font-weight-bold text-uppercase">Catering for private parties, corporate events, public events and festivals!</h1>
        <div v-html="$static.post.content"></div>
        <p>
          smoklahoma is all about serving quality produce all cooked live on site using flavoured lump wood/charcoal giving that authentic barbecue taste we all crave for.
we can cater for any number and will work to your needs giving guests an unforgettable experience.
Any questions please ask and we look forward to hearing from you.
In the meantime take a look at reviews/Facebook page (smoklahomapitbbq) to get an idea of what we're about or even better pop along to one of our many street food events and say hello and have a feed. 
        </p>
        <p>
          We provide catering at any event including private parties, corporate events and public events and festivals.
        </p>
        <p>
          
The Best!

Smoklahoma were the perfect choice for us for our wedding! Food was delicious. Service was excellent and portion sizes were great. Everyone loved it! Thank you so much!
Reviewed by: Kayleigh D

        </p>
        <p>
          
Outstanding Service- Colewood Summer BBQ

The food was much better than our expectations, service was brilliant. Would recommend Smoklahoma for any event.
Reviewed by: Joyce M

        </p>

        <p>
Mouth-watering food and cool set up.

We invited Mark and his team from Smoaklahoma Pitt BBQ to do our wedding evening meal and can't thank them enough for their fantastic work. Our guests are still talking about it. The set up fit perfectly into our barn and countryside wedding theme and my husband and I thoroughly enjoyed the food. Talking to our guests, it's obvious just how impressed everybody was with the food and amazing Smoklahoma team. We'd book again in a flash and would recommend them highly. Thanks a lot! Phil and Steph
Reviewed by: Stephanie L
</p>
        <p>
          
The Best!

Smoklahoma were the perfect choice for us for our wedding! Food was delicious. Service was excellent and portion sizes were great. Everyone loved it! Thank you so much!
Reviewed by: Kayleigh D

        </p>
        <p>
          
Outstanding Service- Colewood Summer BBQ

The food was much better than our expectations, service was brilliant. Would recommend Smoklahoma for any event.
Reviewed by: Joyce M

        </p>

        <p>
Mouth-watering food and cool set up.

We invited Mark and his team from Smoaklahoma Pitt BBQ to do our wedding evening meal and can't thank them enough for their fantastic work. Our guests are still talking about it. The set up fit perfectly into our barn and countryside wedding theme and my husband and I thoroughly enjoyed the food. Talking to our guests, it's obvious just how impressed everybody was with the food and amazing Smoklahoma team. We'd book again in a flash and would recommend them highly. Thanks a lot! Phil and Steph
Reviewed by: Stephanie L
Mouth-watering food and cool set up.
</p>

        <p class="home-links">
          <a href="https://gridsome.org/docs/" target="_blank" rel="noopener">Gridsome Docs</a>
          <a href="https://github.com/gridsome/gridsome" target="_blank" rel="noopener">GitHub</a>
        </p>
      </v-col>
    </v-row>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: "Hello, world!"
  }
};
</script>

<static-query>
query {
  post(path: "/posts/my-first-post/") {
    title
    excerpt
    date
    content
  }
}
</static-query>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
