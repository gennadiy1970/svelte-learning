<script>
  export let src;
  export let alt;
  export let text;
</script>

<style>
  .image {
    width: 100%;
    object-fit: contain;
  }
</style>

<figure>
  <img class="image" {src} {alt} />
  <figcapton>
  <h4>{text}</h4>
  </figcapton>
</figure>
