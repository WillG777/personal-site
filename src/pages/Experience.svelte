<script>
  import LayoutGrid, { Cell } from "@smui/layout-grid";
  import ExpItem from "../lib/ExpItem.svelte";
</script>

<main>
  <h1>Experience</h1>
  <LayoutGrid>
    <Cell span={6}>
      <ExpItem img="src/assets/ata-editing-screenshot.jpg">
      <svelte:fragment slot="title">Squaw Peak ATA</svelte:fragment>
      <svelte:fragment slot="desc">I designed a <a href="squawpeakata.com">website</a> for the taekwondo school where I'm an instructor. In addition to designing the layout, I created an editing interface so authorized users (the school owner and I) can change text and images on the site, and add entries to the Instructors page, without editing the code. I used Svelte and Svelte Material UI for the front end and Google Firebase (Authentication and Realtime Database) for the backend.</svelte:fragment>
      </ExpItem>
    </Cell>
    <Cell span={6}>
      <ExpItem img="src/assets/11trees-favorites-page.png">
      <svelte:fragment slot="title">11trees</svelte:fragment>
      <svelte:fragment slot="desc">For my first internship, I contributed to a company that makes web apps in the education field. I first worked on the <a href="https://www.11trees.com/live/annotate-pro/">Annotate PRO</a> web editor, where I designed a page for users to sort their favorite comments using jQuery. I linked it to the production database using PHP and SQL. Next, I worked on the <a href="https://11trees.com/solutions/canopy/">Canopy</a> web app, for which I designed a new front end and comment navigation interface with VueJS. I also used Instructure Canvas APIs to display real-world data on the app.</svelte:fragment>
      </ExpItem>
    </Cell>
  </LayoutGrid>
  <LayoutGrid>
  <Cell span={6}>
    <ExpItem img="src/assets/gitlet-screenshot.jpg">
      <svelte:fragment slot="title">Gitlet</svelte:fragment>
      <svelte:fragment slot="desc">For my Data Structures class, I implemented a version control system in Java. Supported features included adding and committing files, creating branches, merging branches, and pushing/pulling from remote branches. I used the File API to save persistent data, and I stored commits in a tree structure for efficient searching.</svelte:fragment>
    </ExpItem>
  </Cell>
  <Cell span={6}>
    <ExpItem img="src/assets/numc-screenshot.jpg">
      <svelte:fragment slot="title">NumC</svelte:fragment>
      <svelte:fragment slot="desc">For my Computer Architecture class, I wrote a library to implement matrix and vector operations (auch as addition, multiplication, and exponentiation) in C. By using SIMD vectorized instructions, OMP for thread-level parallelism, and repeated squaring, I was able to improve performance to over 50 times as fast as the reference implementation on average.</svelte:fragment>
    </ExpItem>
  </Cell>
  </LayoutGrid>
  
  
</main>