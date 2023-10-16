<template>
  <div>
    <div class="song-list">
      <div v-for="song in songs" :key="song.song_id" @click="selectSong(song)">
        <img :src="song.image_url" alt="Album Art" />
        <p>{{ song.title }}</p>
        <p>{{ song.artist }}</p>
      </div>
    </div>
    <div class="playing-song">
      <SongDisplay :selectedSong="selectedSong" />
    </div>
  </div>
</template>

<script>
import SongDisplay from "./components/SongDisplay.vue";

export default {
  data() {
    return {
      songs: [
        {
          title: "Song 1",
          artist: "Artist 1",
          song_id: 1,
          image_url: "image_url_1.jpg",
        },
        {
          title: "Song 2",
          artist: "Artist 2",
          song_id: 2,
          image_url: "image_url_2.jpg",
        },
        // Add more songs here
      ],
      selectedSong: null,
    };
  },
  methods: {
    selectSong(song) {
      this.selectedSong = song;
    },
  },
  components: {
    SongDisplay,
  },
};
</script>
<style scoped>
.song-list {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}

.song-item {
  text-align: center;
  cursor: pointer;
  padding: 10px;
  margin: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #f7f7f7;
  transition: background-color 0.3s;
}

.song-item:hover {
  background-color: #e2e2e2;
}

.album-art {
  max-width: 100px;
  max-height: 100px;
}

.song-title {
  font-weight: bold;
}

.song-artist {
  color: #555;
}
</style>