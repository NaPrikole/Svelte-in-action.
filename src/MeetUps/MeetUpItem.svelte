<script>
    import Button from '../UI/Button.svelte';

    export let title;
    export let subtitle;
    export let imageUrl;
    export let description;
    export let address;
    export let email;
</script>

<style>
  article {
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    border-radius: 5px;
    background: white;
    margin: 1rem;
    box-shadow:
    0 1px 4px rgba(0, 0, 0, .3),
    -23px 0 20px -23px rgba(0, 0, 0, .8),
    23px 0 20px -23px rgba(0, 0, 0, .8),
    0 0 40px rgba(0, 0, 0, .1) inset;
  }

  header,
  .content,
  footer {
    padding: 1rem;
  }

  /* article {
    transition: transform .5s ease-in-out;
  }

  article:hover {
    -webkit-transform: rotateY(180deg);
    transform: rotateY(180deg);
  } */

  .content {
    height: 60px;
  }

  .image {
    width: 100%;
    height: 14rem;
    overflow: hidden;
  }

  .image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: 1s;
    display: block;
  }

  .image img:hover {
    transform: scale(1.1);
   }

  h1 {
    font-size: 1.25rem;
    margin: 0.5rem 0;
    font-family: "Roboto Slab", sans-serif;
  }

  h1.is-favorite {
    background: #01a129;
    color: white;
    padding: 0 0.5rem;
    border-radius: 5px;
  }

  h2 {
    font-size: 1rem;
    color: #808080;
    margin: 0.5rem 0;
  }

  p {
    font-size: 1.25rem;
    margin: 0;
  }

  div {
    text-align: right;
  }
 
</style>

<article>
  <header>
    <h1>{title}</h1>
    <h2>{subtitle}</h2>
    <p>{address}</p>
  </header>
  <div class="image">
    <img src="{imageUrl}" alt="{title}" />
  </div>
  <div class="content">
    <p>{description}</p>
  </div>
  <footer>
    <div class="row">
      <div class="col-xs-4">
        <Button mode="meetup-item" type="button" caption="Show Details" />
      </div>
      <div class="col-xs-4">
        <Button mode="meetup-item" type="button" caption="Favourite" />
      </div>
      <div class="col-xs-4">
        <Button mode="meetup-mail-item" href="mailto:{email}" caption="Contact" />
      </div>
    </div>
  </footer>
</article>
