<template>
  <div>
    <div class="bg-gray-900 flex justify-center items-center min-h-screen text-white">
      <h1>
        <div class="animate__animated animate__fadeInDownBig">
          <div class="text-5xl animate__animated animate__tada animate__delay-1s">
            iam<span class="inline-block text-red-600 hover:text-red-700 transition ease-in duration-700">c</span>ommee
            <i class="inline-block fas fa-cat animate__animated animate__zoomInRight animate__delay-2s"></i>
          </div>
        </div>
        <div class="text-right animate__animated animate__fadeInRightBig">
          @BUZZWOO CNX
        </div>
      </h1>
    </div>
  </div>
</template>

<script>
  export default {
    async asyncData({
      $content,
      params
    }) {
      const articles = await $content('articles', params.slug)
        .only(['title', 'description'])
        .sortBy('createdAt', 'desc')
        .fetch()
      return {
        articles,
      }
    }
  }
</script>
