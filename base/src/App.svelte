<script>
  import { onMount } from "svelte";

  import Title from "./components/Title.svelte";
  import Wrapper from "./components/Wrapper.svelte";
  import Cards from "./components/Cards.svelte";
  import Card from "./components/Card.svelte";
  import Image from "./components/Image.svelte";

  import db from "./api/db.js";
  import { name } from "./api/data.json";

  const { data, images } = db;
  let serverData = {data: { name: ''}};
  const githabUrl = 'https://raw.githubusercontent.com/gennadiy1970/json-data/master/db.json';

  onMount(async function() {
    const response = await fetch(githabUrl);
    serverData = await response.json();
    await console.log(serverData.data.name);
  });
</script>

<Wrapper>
  <Title name={data.name} />
  <Title {name} />
  <Title name=" +"/>
  <Title name={'props ' + serverData.data.name} />
  <Card>
    <Title name="Slots" />
  </Card>
  <Title name="List" />
  <Cards>
    {#each images as image, i (image.src)}
      <Card>
        <Image {...image} />
      </Card>
    {/each}

  </Cards>
</Wrapper>
