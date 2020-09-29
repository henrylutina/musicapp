<template>
  <div id="app">
    <div class="wrapper py-5">
      <div class="page-header py-5">
          <div class="filter"></div>
            <div class="container">
              <div class="row">
                <div class="col-lg-4 offset-lg-4 col-sm-6 offset-sm-3">
                  <div class="card card-register border rounded">
                    <header class="display 4 py-4 rounded border">
                      <h3>Erica</h3>
                    </header>
                    <main>
                      <section class="player">
                        <h4 class="song-title">{{ current.title }} - <span>{{ current.artist }}</span></h4>
                        <div class="controls">
                          <button class="prev btn btn-outline-light" @click="prev"><i class="fa fa-fast-backward fa-2x"></i></button>
                          <button class="play btn btn-outline-light" v-if="!isPlaying" @click="play"><i class="fa fa-play-circle fa-2x"></i></button>
                          <button class="pause btn btn-outline-light" v-else @click="pause"><i class="fa fa-pause-circle fa-2x"></i></button>
                          <button class="next btn btn-outline-light" @click="next"><i class="fa fa-fast-forward fa-2x"></i></button>
                        </div>
                      </section>
                      <section class="playlist">
                        <h3>music playlist</h3>
                        <button class="my-2 rounded btn btn-outline-light" v-for="song in songs" :key="song.src" @click="play(song)" :class="(song.src == current.src) ? 'song playing' : 'song'">
                          {{ song.title }} - {{ song.artist }}
                        </button>
                      </section>
                    </main>
                  </div>
                </div>
              </div>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      current: {},
      index: 0,
      isPlaying: false,
      songs: [
        {
          title: 'Free mind',
          artist: 'Tems',
          src: require('@/assets/music/Free_Mind(128k).mp3')
        },
        {
          title: 'Jerusalema',
          artist: 'Master KG',
          src: require('@/assets/music/Master_KG_-_Jerusalema__[Feat._Nomcebo]_(Official_Music_Video)(128k).mp3')
        },
        {
          title: 'Diamonds',
          artist: 'Sam Smith',
          src: require('@/assets/music/Sam_Smith_-_Diamonds(128k).mp3')
        },
        {
          title: 'Erica',
          artist: 'Slimcase',
          src: require('@/assets/music/Slimcase_-_Erica_(Official_Video)(128k).mp3')
        }
      ],
      player: new Audio()
    }
  },
  methods: {
    play (song) {
      if (typeof song.src != "undefined") {
        this.current = song;

        this.player.src = this.current.src;
      }

      this.player.play();
      this.player.addEventListener('ended', function () {
        this.index++;
        if (this.index > this.songs.length - 1) {
          this.index = 0;
        }

        this.current = this.songs[this.index];
        this.play(this.current);
      }.bind(this));
      this.isPlaying = true;
    },
    pause () {
      this.player.pause();
      this.isPlaying = false;
    },
    next () {
      this.index++;
      if (this.index > this.songs.length - 1) {
        this.index = 0;
      }

      this.current = this.songs[this.index];
      this.play(this.current);
    },
    prev () {
      this.index--;
      if (this.index < 0) {
        this.index = this.songs.length - 1;
      }

      this.current = this.songs[this.index];
      this.play(this.current);
    }
  },
  created () {
    this.current = this.songs[this.index];
    this.player.src = this.current.src;
  }
}
</script>

<style>
.wrapper{
  background-image: url('~@/assets/img/login-image.jpg');
}
header {
	display: flex;
	justify-content: center;
	align-items: center;
	padding: 15px;
	background: linear-gradient(to bottom right,  #001a33, #ff66ff);
	color: #FFF;
}
main {
  width: 100%;
  max-width: 768px;
  margin: 0 auto;
  padding: 25px;
  background: linear-gradient(to bottom right,  #001a33, #ff66ff);
  }

.song-title {
  color: white;
  font-size: 15px;
  font-weight: 700;
  text-transform: uppercase;
  text-align: center;
}
.song-title span {
  font-weight: 400;
  font-style: italic;
}

.controls {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 30px 15px;
}

.play, .pause {
  font-size: 20px;
  font-weight: 700;
  padding: 8px 16px;
  margin: 0px 15px;
  border-radius: 8px;
}

.next, .prev {
  font-size: 16px;
  font-weight: 700;
  padding: 5px 8px;
  margin: 0px 15px;
  border-radius: 6px;
}

.playlist {
  padding: 0px 30px;
}
.playlist h3 {
  color: white;
  font-size: 28px;
  font-weight: 400;
  margin-bottom: 30px;
  text-align: center;
}
.playlist .song {
  display: block;
  width: 100%;
  padding: 15px;
  font-size: 20px;
  font-weight: 700;
  cursor: pointer;
}
.playlist .song:hover {
  color: #FF5858;
}

.playlist .song.playing {
  color: #FFF;
  background: linear-gradient(to bottom right,  #001a33, #ff66ff);
}
</style>