<template>
    <div class="song-display">
      <h2>Playing Song</h2>
      <div v-if="selectedSong" class="playing-song-info">
        <img :src="selectedSong.image_url" alt="Album Art" class="album-art" />
        <p class="song-title">{{ selectedSong.title }}</p>
        <p class="song-artist">{{ selectedSong.artist }}</p>
      </div>
      <div v-else>
        <p class="no-song-selected">No song selected. Please pick a song.</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      selectedSong: Object,
    },
  };
  </script>
  
  <style scoped>
  .song-display {
    text-align: center;
  }
  
  .playing-song-info {
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    background-color: #f7f7f7;
  }
  
  .album-art {
    max-width: 150px;
    max-height: 150px;
  }
  
  .song-title {
    font-weight: bold;
  }
  
  .song-artist {
    color: #555;
  }
  
  .no-song-selected {
    font-style: italic;
    color: #888;
  }
  </style>
  