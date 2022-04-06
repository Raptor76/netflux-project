<template>
  <div>
    <Header />
    <div class="home">
      <Film :myfilm="actionFilm" :genre="Genre[0]" id="action" />
      <Film :myfilm="horrorFilm" :genre="Genre[1]" id="horror" />
      <Film :myfilm="animationFilm" :genre="Genre[2]" id="animation" />
      <Film :myfilm="romanceFilm" :genre="Genre[3]" id="romance" />
      <Film :myfilm="fantasticFilm" :genre="Genre[4]" id="fantastic" />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Film from "@/components/Film.vue";
import Header from "./components/Header.vue";

export default {
  name: "HomeView",
  components: {
    Film,
    Header,
  },
  data() {
    return {
      actionFilm: [],
      horrorFilm: [],
      animationFilm: [],
      romanceFilm: [],
      fantasticFilm: [],
      Genre: [],
    };
  },
  methods: {
    async getActionFilms() {
      try {
        let apiGenre =
          "https://api.themoviedb.org/3/genre/movie/list?api_key=71989cd46363c5e44455bea46d00f587&language=fr-FR";
        let responseGenre = await fetch(apiGenre);
        let dataGenre = await responseGenre.json();
        this.Genre.push(dataGenre.genres[0].name);

        let apiFilm =
          "https://api.themoviedb.org/3/discover/movie?api_key=71989cd46363c5e44455bea46d00f587&with_genres=28&language=fr-FR";
        let responseFilm = await fetch(apiFilm);
        let dataFilm = await responseFilm.json();

        for (let i = 0; i < dataFilm.results.length; i++) {
          let title = dataFilm.results[i].title;
          let id = dataFilm.results[i].id;

          let poster =
            "https://image.tmdb.org/t/p/w500" + dataFilm.results[i].poster_path;
          let miniature =
            "https://image.tmdb.org/t/p/w500" +
            dataFilm.results[i].backdrop_path;
          let note = dataFilm.results[i].vote_average;

          this.actionFilm.push({
            id: id,
            title: title,
            poster: poster,
            miniature: miniature,
            note: note,
          });
        }
      } catch (error) {
        console.log(error);
      }
    },

    async getHorrorFilm() {
      try {
        let apiGenre =
          "https://api.themoviedb.org/3/genre/movie/list?api_key=71989cd46363c5e44455bea46d00f587&language=fr-FR";
        let responseGenre = await fetch(apiGenre);
        let dataGenre = await responseGenre.json();
        this.Genre.push(dataGenre.genres[10].name);

        let apiFilm =
          "https://api.themoviedb.org/3/discover/movie?api_key=71989cd46363c5e44455bea46d00f587&with_genres=27&language=fr-FR";

        let responseFilm = await fetch(apiFilm);
        let dataFilm = await responseFilm.json();

        for (let i = 0; i < dataFilm.results.length; i++) {
          let title = dataFilm.results[i].title;
          let id = dataFilm.results[i].id;

          let poster =
            "https://image.tmdb.org/t/p/w500" + dataFilm.results[i].poster_path;
          let miniature =
            "https://image.tmdb.org/t/p/w500" +
            dataFilm.results[i].backdrop_path;
          let note = dataFilm.results[i].vote_average;

          this.horrorFilm.push({
            id: id,
            title: title,
            poster: poster,
            miniature: miniature,
            note: note,
          });
        }
      } catch (error) {
        console.log(error);
      }
    },
    async getAnimationFilm() {
      try {
        let apiGenre =
          "https://api.themoviedb.org/3/genre/movie/list?api_key=71989cd46363c5e44455bea46d00f587&language=fr-FR";
        let responseGenre = await fetch(apiGenre);
        let dataGenre = await responseGenre.json();
        this.Genre.push(dataGenre.genres[2].name);

        let apiFilm =
          "https://api.themoviedb.org/3/discover/movie?api_key=71989cd46363c5e44455bea46d00f587&with_genres=16&language=fr-FR";

        let responseFilm = await fetch(apiFilm);
        let dataFilm = await responseFilm.json();

        for (let i = 0; i < dataFilm.results.length; i++) {
          let title = dataFilm.results[i].title;
          let id = dataFilm.results[i].id;

          let poster =
            "https://image.tmdb.org/t/p/w500" + dataFilm.results[i].poster_path;
          let miniature =
            "https://image.tmdb.org/t/p/w500" +
            dataFilm.results[i].backdrop_path;
          let note = dataFilm.results[i].vote_average;

          this.animationFilm.push({
            id: id,
            title: title,
            poster: poster,
            miniature: miniature,
            note: note,
          });
        }
      } catch (error) {
        console.log(error);
      }
    },
    async getRomanceFilm() {
      try {
        let apiGenre =
          "https://api.themoviedb.org/3/genre/movie/list?api_key=71989cd46363c5e44455bea46d00f587&language=fr-FR";
        let responseGenre = await fetch(apiGenre);
        let dataGenre = await responseGenre.json();
        this.Genre.push(dataGenre.genres[13].name);

        let apiFilm =
          "https://api.themoviedb.org/3/discover/movie?api_key=71989cd46363c5e44455bea46d00f587&with_genres=10749&language=fr-FR";
        let responseFilm = await fetch(apiFilm);
        let dataFilm = await responseFilm.json();

        for (let i = 0; i < dataFilm.results.length; i++) {
          let title = dataFilm.results[i].title;
          let id = dataFilm.results[i].id;

          let poster =
            "https://image.tmdb.org/t/p/w500" + dataFilm.results[i].poster_path;
          let miniature =
            "https://image.tmdb.org/t/p/w500" +
            dataFilm.results[i].backdrop_path;
          let note = dataFilm.results[i].vote_average;

          this.romanceFilm.push({
            id: id,
            title: title,
            poster: poster,
            miniature: miniature,
            note: note,
          });
        }
      } catch (error) {
        console.log(error);
      }
    },
    async getFantasticFilm() {
      try {
        let apiGenre =
          "https://api.themoviedb.org/3/genre/movie/list?api_key=71989cd46363c5e44455bea46d00f587&language=fr-FR";
        let responseGenre = await fetch(apiGenre);
        let dataGenre = await responseGenre.json();
        this.Genre.push(dataGenre.genres[8].name);

        let apiFilm =
          "https://api.themoviedb.org/3/discover/movie?api_key=71989cd46363c5e44455bea46d00f587&with_genres=14&language=fr-FR";
        let responseFilm = await fetch(apiFilm);
        let dataFilm = await responseFilm.json();

        for (let i = 0; i < dataFilm.results.length; i++) {
          let title = dataFilm.results[i].title;
          let id = dataFilm.results[i].id;

          let poster =
            "https://image.tmdb.org/t/p/w500" + dataFilm.results[i].poster_path;
          let miniature =
            "https://image.tmdb.org/t/p/w500" +
            dataFilm.results[i].backdrop_path;
          let note = dataFilm.results[i].vote_average;

          this.fantasticFilm.push({
            id: id,
            title: title,
            poster: poster,
            miniature: miniature,
            note: note,
          });

          console.log(this.fantasticFilm);
        }
      } catch (error) {
        console.log(error);
      }
    },
  },
  mounted() {
    this.getActionFilms();
    this.getHorrorFilm();
    this.getAnimationFilm();
    this.getRomanceFilm();
    this.getFantasticFilm();
  },
};
</script>


<style>
body {
  overflow-x: hidden;
  background: rgba(0, 0, 0, 0.7);
}
</style> 
