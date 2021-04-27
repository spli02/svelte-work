<SubTitle title="Nozzle offset" />

<BorderBox boxType="tall">
  <NozzleIllustration slot="left" />
  <NozzleSetOffBtn slot="right" {disabled} />
</BorderBox>

<GeneralControlBtn
  title={`Test offset ${offsetStatus === offsetType.ON ? '…' : ''}`}
  src={`../images/icons-32-x-32-offset-${offsetStatus}.svg`}
  srcAlt={`test_offset_${offsetStatus}`}
  subTitle={offsetSubTitle}
  handleClick={handleOffset}
/>

<script>
  import GeneralControlBtn from '../components/GeneralControlBtn.svelte'
  import SubTitle from '../components/SubTitle.svelte'
  import BorderBox from '../components/BorderBox.svelte'
  import NozzleIllustration from '../components/NozzleIllustration.svelte'
  import NozzleSetOffBtn from '../components/NozzleSetOffBtn.svelte'

  export let disabled

  const offsetType = {
    ON: 'on',
    OFF: 'off',
  }

  let offsetStatus = offsetType.OFF

  const handleOffset = () => {
    offsetStatus = offsetStatus === offsetType.ON ? offsetType.OFF : offsetType.ON
    disabled = !disabled
  }

  $: offsetSubTitle =
    offsetStatus === offsetType.OFF
      ? 'This will trigger printing of a calibration pattern'
      : undefined
</script>
