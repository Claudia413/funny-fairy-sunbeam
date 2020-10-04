<template>
  <Layout>
    <section class="news">
      <div class="container ">
          <h2 class="emphasize green">News</h2>
          <article v-for="article in news" :key="article.id" class="news-article">
              <h4>{{article.title}}</h4>
              <p class="subtitle">{{article.publishingDate}}</p>
              <p>{{article.content}}</p>
          </article>
      </div>
    </section>

  </Layout>
</template>

<script>


export default {
  metaInfo: {
    title: 'News'
  },
  data() {
    return {
        news: [{
            id: 1,
            title: "Covid-19 Alert level 1",
            content: "We are now at Covid-19 alert level 1, which means we are able to see you face to face. Please email or call us for an appointment. If you are feeling unwell, please do not come into the clinic.",
            publishingDate: "22-09-2020"
        },
        {
            id: 2,
            title: "Covid-19 update",
            content: "Since we can not see you in person we can arrange a telephone or video consultation with you.  Please email the clinic for an appointment.",
            publishingDate: "27-03-2020"
        },
        {
            id: 3,
            title: "Happy New Year",
            content: "Happy New Year to all our current clients and welcome to the new ones. Please call our receptionists Jacky or Tracy for an appointment. Merry Christmas. Hope all our clients past and present have a nice Christmas. We are staying open over the Christmas period, only closing on the statutory days, so we are ready to look after you over this period. Please ring Jacky to book an appointment with Blair, Ross, Tania or Hayley.",
            publishingDate: "09-12-2019"
        },]

     }
  },
  components: {

  },
  methods: {

  }
}
</script>

<style lang="scss">
.news-article {
    margin-bottom: 40px;
    h4 {
         font-size: 18px;
        line-height: 26px;
        margin-bottom: 4px;
    }
}

</style>
