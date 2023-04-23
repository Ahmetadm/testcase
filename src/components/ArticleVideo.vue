<script>
export default {

  props: {
    src: { type: String, required: true },
    loop: { type: Boolean, required: false, default: false },
    width: { type: Number, required: false, default: 500 },
    height: { type: Number, required: false, default: 281 },
    autoplay: { type: Boolean, required: false, default: false },
    muted: { type: Boolean, required: false, default: false },
    poster: { type: String, required: false },
    preload: { type: String, required: false, default: 'auto' }
  },
  data() {
    return {
      playing: false,
      duration: 0,
      percentagePlayed: 0,
      videoMuted: false,
      controls: false,
      videoSrc: this.$props.src
    }
  },

  methods: {
    setPlaying(state) {
      this.playing = state
    },
    goFullScreen() {
      if (this.$refs.player.webkitEnterFullScreen) {
        return this.$refs.player.webkitEnterFullScreen()
      }
      return this.$refs.player.requestFullscreen()
    },
    play() {
      this.$refs.player.play()
      this.setPlaying(true)
      this.controls = true
      this.goFullScreen()
    }
  }
}
</script>
<template>
  <div>
    <video
      allowFullScreen
      webkitallowfullscreen
      mozallowfullscreen
      :muted="muted"
      :autoplay="autoplay"
      :controls="controls"
      :loop="loop"
      :width="width"
      :height="height"
      :poster="poster"
      :preload="preload"
      :playsinline="true"
      ref="player"
    >
      <source :src="$props.src" type="video/mp4" />
      Your browser does not support the video tag.
    </video>

    <button v-if="!playing" class="button" @click="play">
      <div class="button__circle">
        <i class="fas fa-play"></i>
      </div>
    </button>
  </div>
</template>

<style scoped>
video {
  width: 100%;
  position: relative;
}
.button {
  background-color: transparent;
  border: none;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  cursor: pointer;
}
.button__circle {
  background-color: white;
  display: inline-block;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  position: relative;
  text-align: center;
}
.button__circle::after {
  content: '';
  width: 80px;
  height: 80px;
  border-radius: 50%;
  position: absolute;
  top: 50%;
  left: 50%;
  border: 2px solid white;
  transform: translate(-50%, -50%);
}
.button__circle .fas {
  line-height: 60px;
  color: gray;
  font-size: 25px;
}
</style>
