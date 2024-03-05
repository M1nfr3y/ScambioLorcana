<script>
  import Card from "../Card.svelte";

  let cards = [
    { title: "Titolo 1", description: "Descrizione 1", imageUrl: "image1.jpg" },
    { title: "Titolo 2", description: "Descrizione 2", imageUrl: "image2.jpg" },
    { title: "Titolo 3", description: "Descrizione 3", imageUrl: "image3.jpg" },
    { title: "Titolo 4", description: "Descrizione 4", imageUrl: "image4.jpg" },
    { title: "Titolo 5", description: "Descrizione 5", imageUrl: "image5.jpg" },
    { title: "Titolo 6", description: "Descrizione 6", imageUrl: "image6.jpg" },
    { title: "Titolo 7", description: "Descrizione 7", imageUrl: "image7.jpg" },
    { title: "Titolo 8", description: "Descrizione 8", imageUrl: "image8.jpg" },
    { title: "Titolo 9", description: "Descrizione 9", imageUrl: "image9.jpg" },
    { title: "Titolo 10", description: "Descrizione 10", imageUrl: "image10.jpg" },
    { title: "Titolo 11", description: "Descrizione 11", imageUrl: "image11.jpg" },
    { title: "Titolo 12", description: "Descrizione 12", imageUrl: "image12.jpg" },
  ];

  let groupCards = [];
  while (cards.length > 0) {
    groupCards.push(cards.splice(0, 4));
  }
</script>
<diV>
  <h2>Scambi</h2>
</diV>
<div
  id="carouselExampleDark"
  class="carousel carousel-dark slide"
  data-bs-ride="carousel"
>
  <div class="carousel-indicators">
    <button
      type="button"
      data-bs-target="#carouselExampleDark"
      data-bs-slide-to="0"
      class="active"
      aria-label="Slide 1"
    ></button>
    <button
      type="button"
      data-bs-target="#carouselExampleDark"
      data-bs-slide-to="1"
      aria-label="Slide 2"
      class=""
      aria-current="true"
    ></button>
    <button
      type="button"
      data-bs-target="#carouselExampleDark"
      data-bs-slide-to="2"
      aria-label="Slide 3"
      class=""
    ></button>
  </div>
  <div class="carousel-inner">
    {#each groupCards as group, groupIndex}
      <div
        class="carousel-item {groupIndex === 0 ? 'active' : ''}"
        data-bs-interval="10000"
      >
        <div class="card-deck">
          {#each group as card, cardIndex}
            <div class="card">
              <!-- <img src="/heart-fill.svg" class="card-img-top" alt="..."> -->
              <div class="card-body">
                <h5 class="card-title">{card.title}</h5>
                <p class="card-text">{card.description}</p>
              </div>
            </div>
          {/each}
        </div>
      </div>
    {/each}
    <!-- <Card {title}></Card> -->
  </div>
  <button
    class="carousel-control-prev"
    type="button"
    data-bs-target="#carouselExampleDark"
    data-bs-slide="prev"
    style="left: -5%"
  >
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button
    class="carousel-control-next"
    type="button"
    data-bs-target="#carouselExampleDark"
    data-bs-slide="next"
    style="right: -5%;"
  >
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>

<style>
  .carousel {
    overflow: hidden;
  }

  .card-deck {
    display: flex;
    justify-content: space-around;
  }

  .card {
    margin-top: 1%;
    width: 335px;
    height: 200px;
    text-align: center;
    background-color: #d2b786d1;
    border-color: #403174d1;
    border-width: 3px;
  }

  .carousel-dark {
    height: 255px;
    margin-top: 2%;
  }
</style>
