<svelte:head>
  <title>Biology class eDee 1</title>
</svelte:head>

<div>
  <ApplicationBar />
  <Header />

  <MainSection>
    <SubSection>
      <NozzleTempContainer {disabled} />
    </SubSection>

    <SubSection>
      <NozzleOffsetContainer bind:disabled />
    </SubSection>
  </MainSection>
</div>

<script>
  import ApplicationBar from '~/components/ApplicationBar.svelte'
  import Header from '~/components/Header.svelte'
  import NozzleTempContainer from '~/containers/NozzleTempContainer.svelte'
  import NozzleOffsetContainer from '~/containers/NozzleOffsetContainer.svelte'
  import SubSection from '~/components/SubSection.svelte'
  import MainSection from '~/components/MainSection.svelte'

  let disabled = false
</script>

<style type="text/scss">
  @import 'main.scss';

  :global(#sapper) {
    width: 800px;
    height: 480px;
  }

  :global(body) {
    margin: 0;
    padding: 0;
    user-select: none;
    overflow: hidden;
    background-color: var(--white);
    font-family: Roboto;
    font-size: var(--font-size-default);
  }
</style>
