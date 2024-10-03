<template>
  <div style="padding: 0px">
    <v-zoomer-gallery
      ref="gallery"
      :list="urlImageList"
      :zooming-elastic="false"
      v-model="selIndex"
    ></v-zoomer-gallery>
    <div style="box-sizing: border-box; height: 32px; padding: 4px">
      <button :disabled="selIndex === 0" @click="selIndex -= 1">&lt;-</button>
      <span>{{ selIndex + 1 }} / {{ urlImageList.length }}</span>
      <button
        :disabled="selIndex === urlImageList.length - 1"
        @click="selIndex += 1"
      >
        -&gt;
      </button>
      <button @click="$refs.gallery.reset()">reset</button>
      <button @click="$refs.gallery.zoomIn()">+</button>
      <button @click="$refs.gallery.zoomOut()">-</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selIndex: 0,
      urlImageList: [
        { type: 'video', url: 'http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/ForBiggerBlazes.mp4'},
        { type: 'audio', url: 'http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/ForBiggerBlazes.mp4'},
       { type: 'image', url:  'https://unpkg.com/vue-zoomer@0.3.9/dist/demo/landscape-2.ba8bc5c7.jpg'},
        { type: 'image', url: 'https://unpkg.com/vue-zoomer@0.3.9/dist/demo/landscape-3.f5787143.jpg'},
        { type: 'image', url: 'https://unpkg.com/vue-zoomer@0.3.9/dist/demo/landscape-4.7217d472.jpg'},
        { type: 'image', url: 'https://unpkg.com/vue-zoomer@0.3.9/dist/demo/landscape-5.f1faccaa.jpg'},
      ],
    }
  },
}
</script>
