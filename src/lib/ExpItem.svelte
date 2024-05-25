<script>
  import LayoutGrid, { Cell } from "@smui/layout-grid";
  import Card, { Media, Content } from "@smui/card";
  export let img = '';
</script>

<div class="card-container">
  <Card variant="outlined">
    <div style="padding: 1rem;">
      <h2 class="mdc-typography--headline6" style="margin: 0;">
        <slot name="title"></slot>       
      </h2>
    </div>
    {#if img}
      <Media class="card-media-16x9" style="background-image: url({img})" aspectRatio="16x9" />
    {/if}
    <Content class="mdc-typography--body2">
      <slot name="desc"></slot>
    </Content>
  </Card>
</div>
