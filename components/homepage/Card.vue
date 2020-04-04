<template>
  <article class="card">
    <div class="card-image">
      <figure class="image is-4by3">
        <img
          :src="
            article.imgURL || 'https://nuxtjs.org/logos/nuxt-icon-white.png'
          "
          :alt="`Zdjęcie ${article.name}`"
        />
      </figure>
    </div>
    <div class="card-content">
      <div class="media">
        <div class="media-content">
          <nuxt-link
            class="title is-4 is-block"
            :to="`posty/${article.slug}`"
            >{{ article.title }}</nuxt-link
          >
          <p v-if="article.author" class="subtitle is-6">
            @{{ article.author }}
          </p>
        </div>
      </div>

      <div class="content">
        {{ article.desc }}
        <br />
        <time :datetime="article.uploadAt">{{ article.uploadAt }}</time>
      </div>
    </div>
  </article>
</template>
<script>
export default {
  props: {
    article: {
      type: Object,
      required: true
    }
  }
}
</script>
