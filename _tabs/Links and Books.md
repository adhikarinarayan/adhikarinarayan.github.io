---
icon: fa-solid fa-bookmark
order: 2
---

<style>
  /* Hide the "Brain Food" heading */
  .dynamic-title {
    display: none;
  }

  .brain-food-container {
    display: flex;
    gap: 2rem;
    margin: 2rem 0;
  }

  .brain-food-container .column-left,
  .brain-food-container .column-right {
    flex: 1;
  }

  .brain-food-container h2 {
    margin-top: 0;
  }

  .brain-food-container ul {
    list-style-type: disc;
    padding-left: 1.5rem;
  }

  @media (max-width: 768px) {
    .brain-food-container {
      flex-direction: column;
    }
  }
</style>

<div class="brain-food-container">
  <div class="column-left">
    <h2>Useful Links</h2>
    <ul>
      <li><a href="https://github.com/dair-ai/ML-Papers-of-the-Week" target="_blank">ML Papers of the Week</a></li>
      <li><a href="https://plato.stanford.edu/index.html" target="_blank">Stanford Encyclopedia of Philosophy</a></li>
      <li><a href="https://www.scottaaronson.com/democritus" target="_blank">QC since Democritus</a></li>
      <li><a href="https://paulgraham.com/articles.html" target="_blank">PG Essays</a></li>
      <li><a href="https://gwern.net/doc/science/1986-hamming" target="_blank">You and Your Research (Hamming's Essay)</a></li>
      <li><a href="https://colah.github.io/" target="_blank">Colah's Blog</a></li>
      <li><a href="https://huyenchip.com/blog/" target="_blank">Chip Huyen's Blog</a></li>
    </ul>
  </div>

  <div class="column-right">
    <h2>Books I Enjoyed</h2>
    <ul>
      <li>Klara and the Sun by Kazuo Ishiguro</li>
      <li>Project Hail Mary by Andy Weir</li>
      <li>Why Machines Learn by Anil Ananthaswamy</li>
      <li>The MANIAC by Benjamín Labatut</li>
      <li>The Brothers Karamazov by Fyodor Dostoevsky</li>
      <li>Three Body Problem Trilogy by Liu Cixin</li>
      <li>The Last Question by Isaac Asimov</li>
      <li>Stories of Your Life by Ted Chiang</li>
      <li>Dark Matter by Blake Crouch</li>
      <li>Crime and Punishment by Fyodor Dostoevsky</li>
      <li>Norwegian Wood by Haruki Murakami</li>
    </ul>

    <h2>TBA</h2>
    <ul>
      <li>Artist -</li>
    </ul>
  </div>
</div>
