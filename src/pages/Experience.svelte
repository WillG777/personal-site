<script>
  import LayoutGrid, { Cell } from "@smui/layout-grid";
  import ExpItem from "../lib/ExpItem.svelte";
</script>

<main>
  <h1>Experience</h1>
  <h2>Internships</h2>
  <LayoutGrid>
    <Cell span={6}>
      <ExpItem img="pic-with-duo.jpg">
      <svelte:fragment slot="title">Duolingo</svelte:fragment>
      <svelte:fragment slot="desc">I worked as a software engineering intern on <a href="https://duolingo.com">Duolingo</a>'s Cloud Operations team. My project consisted of two internal tools. The first was a Slack bot that used GPT-4 and pulled data from Slack and Zoom to automatically generate incident reports. The second was a React app to suggest and schedule employees for review sessions. I used Python for the backend of both tools and deployed them as AWS Lambda functions using Terraform.</svelte:fragment>
      </ExpItem>
    </Cell>
    <Cell span={6}>
      <ExpItem img="11trees-favorites-page.png">
      <svelte:fragment slot="title">11trees</svelte:fragment>
      <svelte:fragment slot="desc">For my first internship, I contributed to a company that makes web apps in the education field. I first worked on the <a href="https://www.11trees.com/live/annotate-pro/">Annotate PRO</a> web editor, where I designed a page for users to sort their favorite comments using jQuery. I linked it to the production database using PHP and SQL. Next, I worked on the <a href="https://11trees.com/solutions/canopy/">Canopy</a> web app, for which I designed a new front end and comment navigation interface with VueJS. I also used Instructure Canvas APIs to display real-world data on the app.</svelte:fragment>
      </ExpItem>
    </Cell>
  </LayoutGrid>

  <h2>Other Projects</h2>
  <LayoutGrid>
    <Cell span={6}>
      <ExpItem>
      <svelte:fragment slot="title">Squaw Peak ATA</svelte:fragment>
      <svelte:fragment slot="desc">I designed a <a href="https://squawpeakata.com">website</a> for the taekwondo school where I worked as an instructor. In addition to designing the layout, I created an editing interface so authorized users (the school owner and I) can change text and images on the site, and add entries to the Instructors page, without editing the code. I used Svelte and Svelte Material UI for the front end and Google Firebase (Authentication and Realtime Database) for the backend.</svelte:fragment>
      </ExpItem>
    </Cell>
    <Cell span={6}>
      <ExpItem>
        <svelte:fragment slot="title">PINTOS</svelte:fragment>
        <svelte:fragment slot="desc">For my Operating Systems class, I worked with a group of 4 to develop features for a simple Unix-like operating system using C. For the first phase of the project, we implemented the ability to run basic user programs, including argument passing and basic syscalls. Next, we implemented multithreading, including a strict priority scheduler and user thread syscalls. Finally, we implemented a basic file system including a buffer cache, inode array for extensible files, and a directory system.</svelte:fragment>
      </ExpItem>
    </Cell>
  </LayoutGrid>
  <LayoutGrid>
    <Cell span={6}>
      <ExpItem img="">
        <svelte:fragment slot="title">ChocoPy Compiler</svelte:fragment>
        <svelte:fragment slot="desc">For my Programming Languages class, I worked with a partner to create a compiler for the <a href="https://chocopy.org/">ChocoPy</a> language, a simple subset of Python. For the first part of the project, we implemented a lexer and parser using JFlex and CUP, which took a program as input and produced an AST. From there, we implemented semantic analysis in Java using a recursive descent of the AST, which ensures that programs are well-typed and have valid variable declarations. Finally, we implemented code generation, using another recursive descent to produce RISC-V assembly code.</svelte:fragment>
      </ExpItem>
    </Cell>
    <Cell span={6}>
      <ExpItem>
        <svelte:fragment slot="title">Secure File System</svelte:fragment>
        <svelte:fragment slot="desc">For my Computer Security class, I worked with a partner to implement a client API for a cryptographically secure file system using Go. Features we supported include making user accounts, storing and appending to files, and sharing files with other users. We used a variety of methods to ensure confidentiality and integrity including symmetric encryption for files, RSA encryption for file invitations, and MACs to provide integrity. We designed an array structure to allow for constant-time appends to files and wrote over 1,000 lines of test cases.</svelte:fragment>
      </ExpItem>
    </Cell>
  </LayoutGrid>
  <LayoutGrid>
  <Cell span={6}>
    <ExpItem>
      <svelte:fragment slot="title">Gitlet</svelte:fragment>
      <svelte:fragment slot="desc">For my Data Structures class, I implemented a version control system in Java. Supported features included adding and committing files, creating branches, merging branches, and pushing/pulling from remote branches. I used the File API to save persistent data, and I stored commits in a tree structure for efficient searching.</svelte:fragment>
    </ExpItem>
  </Cell>
  <Cell span={6}>
    <ExpItem>
      <svelte:fragment slot="title">NumC</svelte:fragment>
      <svelte:fragment slot="desc">For my Computer Architecture class, I wrote a library to implement matrix and vector operations (auch as addition, multiplication, and exponentiation) in C. By using SIMD vectorized instructions, OMP for thread-level parallelism, and repeated squaring, I was able to improve performance to over 50 times as fast as the reference implementation on average.</svelte:fragment>
    </ExpItem>
  </Cell>
  </LayoutGrid>
  
  
</main>