<SubTitle
  title={subtitle}
  src={`../images/icons-24-x-24-nozzle-temperature-${nozzleTempStatus}.svg`}
  srcAlt="temperature"
  isProgressRequired={tempCoolStatus === tempStatus.ON || tempHeatStatus === tempStatus.ON}
  {tempCoolStatus}
  {tempHeatStatus}
/>

<BorderBox boxType="short">
  <TempControlBtn
    title="Cool down"
    slot="left"
    src={`../images/icons-32-x-32-cool-${tempCoolStatus}.svg`}
    srcAlt={`cool_down_${tempCoolStatus}`}
    type={tempControlType.COOL}
    isStatusOn={tempCoolStatus === tempStatus.ON}
    {handleTemp}
    {tempControlType}
    {disabled}
  />
  <TempControlBtn
    title="Heat up"
    slot="right"
    src={`../images/icons-32-x-32-heat-${tempHeatStatus}.svg`}
    srcAlt={`heat_up_${tempHeatStatus}`}
    type={tempControlType.HOT}
    isStatusOn={tempHeatStatus === tempStatus.ON}
    {handleTemp}
    {tempControlType}
    {disabled}
  />
</BorderBox>

<GeneralControlBtn
  title="Change nozzle"
  src={`../images/icons-32-x-32-nozzle-exchange-${nozzleChangeStatus}.svg`}
  srcAlt={`nozzle_change_${nozzleChangeStatus}`}
  subTitle={`Printed hours: ${currentPrintedHours} / ${maxPrintedHours}`}
  handleClick={handleChangeNozzle}
  isSubTitleHighlighted={!disabled && currentPrintedHours >= maxPrintedHours}
  {disabled}
/>

<GeneralControlBtn
  title="Unlock both doors"
  src="../images/icons-32-x-32-unlock.svg"
  srcAlt="unlock_doors"
/>

<script>
  import TempControlBtn from '../components/TempControlBtn.svelte'
  import GeneralControlBtn from '../components/GeneralControlBtn.svelte'
  import SubTitle from '../components/SubTitle.svelte'
  import BorderBox from '../components/BorderBox.svelte'

  export let disabled

  // nozzle-temperature
  const nozzleTempType = {
    NORMAL: 'normal',
    COLD: 'cold',
    HOT: 'hot',
  }

  $: nozzleTempStatus =
    tempCoolStatus === tempStatus.ON
      ? nozzleTempType.COLD
      : tempHeatStatus === tempStatus.ON
      ? nozzleTempType.HOT
      : nozzleTempType.NORMAL

  $: subtitle =
    tempCoolStatus === tempStatus.ON
      ? 'Cooling down the nozzle …'
      : tempHeatStatus === tempStatus.ON
      ? 'Heating up the nozzle …'
      : 'Nozzle temperature: 0 °C'

  // temp-control
  const tempControlType = {
    HOT: 'hot',
    COOL: 'cool',
  }

  const tempStatus = {
    ON: 'on',
    OFF: 'off',
    DISABLED: 'disabled',
  }

  $: tempCoolStatus = disabled ? tempStatus.DISABLED : tempStatus.OFF
  $: tempHeatStatus = disabled ? tempStatus.DISABLED : tempStatus.OFF

  const handleTemp = type => {
    if (type === tempControlType.HOT) {
      tempHeatStatus = tempHeatStatus === tempStatus.ON ? tempStatus.OFF : tempStatus.ON
      tempCoolStatus = tempStatus.OFF
    } else {
      tempCoolStatus = tempCoolStatus === tempStatus.ON ? tempStatus.OFF : tempStatus.ON
      tempHeatStatus = tempStatus.OFF
    }
  }

  // nozzle-exchange
  const nozzleChangeType = {
    NORMAL: 'normal',
    RESET: 'reset',
    DISABLED: 'disabled',
  }
  const maxPrintedHours = 500
  $: nozzleChangeStatus = disabled ? nozzleChangeType.DISABLED : nozzleChangeType.NORMAL

  const handleChangeNozzle = () => {
    nozzleChangeStatus = nozzleChangeType.RESET
  }

  $: currentPrintedHours = nozzleChangeStatus === nozzleChangeType.RESET ? '0' : '755'
</script>
