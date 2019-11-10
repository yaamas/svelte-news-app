<script>
  import Head from "./Head.svelte";
  import Body from "./Body.svelte";

  // const fetch = require('node-fetch');

  let toLang = "",
    fromLang = "en";
  let country = "in",
    category = "health";

  let newsapi = `https://newsapi.org/v2/top-headlines?country=${country}&category=${category}&apiKey=a188caa95ebe45a1898d065d94db2b57`;

  let articles = (async () => {
    const resp = await fetch(newsapi);
    if (!resp.ok) throw new Error("bad result");
    let payload = await resp.json();
    return payload["articles"];
  })();
</script>

<Head bind:toLang bind:country />
<div class="articles">
  {#await articles}
    <p>loading ...</p>
  {:then data}
    {#each data as article}
      <Body
        title={article.title}
        source={article.source.name}
        src={article.urlToImage}
        url={article.url}
        description={article.description} />
    {/each}
  {/await}
</div>
