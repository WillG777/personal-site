<script>
  import { Link, Router, Route, navigate as svNavigate, link } from "svelte-navigator";
	import TopAppBar, { Row, Section, AutoAdjust } from "@smui/top-app-bar";
	import Button, { Label } from "@smui/button";
  import IconButton from "@smui/icon-button";
	import LayoutGrid, { Cell } from '@smui/layout-grid';
  import Paper, { Content } from "@smui/paper";
  import Home from "./pages/Home.svelte";
  import Experience from "./pages/Experience.svelte";
  import Teaching from "./pages/Teaching.svelte";
  import Education from "./pages/Education.svelte";
  import Drawer, { Content as DrawerContent, Header, Title as DrawerTitle, Scrim, AppContent } from "@smui/drawer";
  import List, { Item } from "@smui/list";
  import { onMount } from "svelte";

  

  let topAppBar;
  let darkMode = true;
  $: toggleIcon = darkMode ? 'light_mode' : 'dark_mode';
  let currentPage = window.location.pathname;
  let drawerOpen = false;
  let innerWidth = 1000;

  function navigate(page) {
    currentPage = page;
    svNavigate(page);
  }
  function drawerNav(page) {
    drawerOpen = false;
    navigate(page);
  }
  onMount(() => {
		if (window.location.search.startsWith('?page=')) {
			navigate('/' + window.location.search.substring(6))
		}
	})
</script>

<svelte:head>
  <link rel="stylesheet" href="smui{darkMode ? '-dark' : ''}.css">
</svelte:head>
<svelte:window bind:innerWidth={innerWidth}></svelte:window>


<Router>
  <Drawer variant="modal" bind:open={drawerOpen}>
		<Header>
			<DrawerTitle>Will Giorza</DrawerTitle>
		</Header>
		<DrawerContent>
			<List>
				<Item on:click={() => drawerNav('/')}>Home</Item>
				<Item on:click={() => drawerNav('/experience')}>Experience</Item>
				<Item on:click={() => drawerNav('/education')}>Education</Item>
				<Item on:click={() => drawerNav('/teaching')}>Teaching</Item>
			</List>
		</DrawerContent>
	</Drawer>
  <Scrim />
  <AppContent>
    <TopAppBar bind:this={topAppBar} variant="fixed">
      <Row>
        <Section>
              <img on:click={() => navigate('/')} src="wg-logo.png" alt="WG" width="50" style="cursor: pointer">
              <h2 on:click={() => navigate('/')} style="padding: 0px 10px; cursor: pointer">Will Giorza</h2>
        </Section>
        <Section>
          {#if innerWidth < 700}
					  <IconButton class="material-icons" on:click={() => drawerOpen=true}>menu</IconButton>
          {:else}
            <a href="/" use:link={navigate}><Button ripple={false}><Label><span class:activeLink={currentPage==='/'}>Home</span></Label></Button></a>
            <a href="experience" use:link={navigate}><Button ripple={false}><Label><span class:activeLink={currentPage==='/experience'}>Experience</span></Label></Button></a>
            <a href="education" use:link={navigate}><Button ripple={false}><Label><span class:activeLink={currentPage==='/education'}>Education</span></Label></Button></a>
            <a href="teaching" use:link={navigate}><Button ripple={false}><Label><span class:activeLink={currentPage==='/teaching'}>Teaching</span></Label></Button></a>
          {/if}
        </Section>
        <Section align="end">
          <IconButton class="material-icons" on:click={() => darkMode = !darkMode}>{toggleIcon}</IconButton>
        </Section>
      </Row>
    </TopAppBar>
    <AutoAdjust {topAppBar}>
      <div id="routeContainer">
        <LayoutGrid>
          <Cell span={1} />
          <Cell span={10}>
            <Paper>
              <Content>
                <Route path="/" component={Home} />
                <Route path="experience" component={Experience} />
                <Route path="education" component={Education} />
                <Route path="teaching" component={Teaching} />
              </Content>
            </Paper>
          </Cell>
          <Cell span={1} />
        </LayoutGrid>
      </div>
      <footer>
        <LayoutGrid>
          <Cell spanDevices={{ desktop: 6, tablet: 4, phone: 2 }}>
            <p>&copy; 2022 Will Giorza</p>
          </Cell>
          <Cell spanDevices={{ desktop: 6, tablet: 4, phone: 2 }}>
            <p>Made with <a href="https://svelte.dev">Svelte</a> and <a href="https://sveltematerialui.com">SMUI</a></p>
          </Cell>
        </LayoutGrid>
      </footer>
    </AutoAdjust>
  </AppContent>
</Router>


<style>
  #routeContainer {
    padding: 8px;
    min-height: 75vh;
  }
  .activeLink {
    font-weight: bold;
  }
  footer p {
    text-align: center;
    font-size: 0.9rem;
  }
</style>
