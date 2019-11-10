<script>
  export let title;
  export let source;
  export let src;
  export let url;
  export let description;

  if (description == null) description = "No description available";
</script>

<style>
  * {
    box-sizing: border-box;
  }

  .card {
    /* Add shadows to create the "card" effect */
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    transition: 0.3s;
    width: 40%;
    border-radius: 0.5em;
    max-width: 400px;
    margin: auto;
  }

  .card h3 {
    padding-left: 16px;
    padding-top: 14px;
    padding-right: 16px;
  }

  .card p {
    padding-left: 16px;
    padding-top: 0px;
    padding-right: 16px;
  }

  .card img {
    height: 100%;
    width: 100%;
    object-fit: contain;
  }

  /* On mouse-over, add a deeper shadow */
  .card:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
  }

  .container p {
    padding: 5px 16px;
  }

  .container p:last-child {
    padding-top: 5px;
    border-top: 1px solid lightgray;
    text-align: center;
    font-size: 16px;
    color: #414fb6;
  }

  .container a:hover {
    background: rgb(227, 229, 236);

    padding: 3px 3px;
  }

  .container a:link,
  a:visited {
    padding: 14px 25px;
    border-radius: 0.5em;
    text-decoration: none;
    display: inline-block;
  }
</style>

<div>
  <div class="card">
    <h3>{title}</h3>
    <p>{source}</p>
    <img {src} alt="" />
    <div class="container">
      <p>{description.length > 80 ? description.slice(0, 75) : description}...</p>
      <p>
        <a href={url} target="_blank">
          More
          <i class="fa fa-eye" />
        </a>
      </p>
    </div>

  </div>
</div>
