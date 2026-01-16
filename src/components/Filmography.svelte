<script>
  import { films } from "../data/films.js";

  const categories = ["Film", "Documentary", "Series"];

  const filmsByCategory = (category) =>
    films.filter((item) => item.category === category);
</script>

<section class="section section-filmography">
  <div class="container section-inner">

    {#each categories as category}
      {#if filmsByCategory(category).length}
        <div class="film-category">
          <div class="film-category-header">
            <h3>{category}</h3>
          </div>

          <div class="film-grid">
            {#each filmsByCategory(category) as film}
              <a
                class="film-card"
                href={film.imdbUrl}
                target="_blank"
                rel="noopener noreferrer"
              >
                <div class="film-poster-wrap">
                  <img src={film.poster} alt={film.title} class="film-poster" />
                </div>
                <div class="film-meta">
                  <h4 class="film-title">{film.title}</h4>
                  <p class="film-info">
                    <span>{film.year}</span>
                    <span>· {film.genre}</span>
                  </p>
                  <p class="film-role">{film.role}</p>
                </div>
              </a>
            {/each}
          </div>
        </div>
      {/if}
    {/each}
  </div>
</section>