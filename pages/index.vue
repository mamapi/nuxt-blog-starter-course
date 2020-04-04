<template>
  <div>
    <div class="section">
      <main class="container">
        <div class="columns is-multiline">
          <div
            v-for="article in articles"
            :key="article.id"
            class="column is-3"
          >
            <Card :article="article" />
          </div>
        </div>
      </main>
    </div>
  </div>
</template>

<script>
import Card from '~/components/homepage/Card'

export default {
  name: 'HomePage',

  components: {
    Card
  },

  data: () => ({
    articles: []
  }),

  created() {
    const req = require.context('~/articles', false, /\.(md)$/)

    req.keys().forEach((filePath) => {
      const key = filePath.replace('./', '').replace('.md', '')
      const { attributes } = require(`~/articles/${key}.md`)

      this.articles.push({
        id: key,
        slug: key,
        imgURL: attributes.imgURL,
        uploadAt: attributes.uploadAt,
        author: attributes.author,
        title: attributes.title,
        desc: attributes.desc
      })
    })
  }
}
</script>
