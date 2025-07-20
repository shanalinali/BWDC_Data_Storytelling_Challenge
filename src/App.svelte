<script>
  // Sections with Scroller component involved (typically graphs)
  import LeftAlignedExample from "./sections/LeftAlignedExample.svelte";
  import RightAlignedEarningsGraph from "./sections/RightAlignedEarningsGraph.svelte";
  import RightAlignedNoGraph from "./sections/RightAlignedNoGraph.svelte";
  import LeftAlignedEnrollmentGraph from "./sections/LeftAlignedEnrollmentGraph.svelte";
  import LeftAlignedHouseholdGraph from "./sections/LeftAlignedHouseholdGraph.svelte";
  import RightAlignedPercentHolding from "./sections/RightAlignedPercentHolding.svelte";
  // Sections for transitioning the story
  import TitleSection from "./sections/TitleSection.svelte";
  import FirstTransition from "./sections/FirstTransition.svelte";
  import SecondTransition from "./sections/SecondTransition.svelte";
  import ThirdTransition from "./sections/ThirdTransition.svelte";
  import FourthTransition from "./sections/FourthTransition.svelte";
  import FinalTransition from "./sections/FinalTransition.svelte";
  import AcknowledgementsSection from "./sections/AcknowledgementsSection.svelte";
  // KWK examples from Scrollytelling template
  import InteresectionObserverBasicExample from "./sections/InteresectionObserverBasicExample.svelte";
  import IntersectionObserverAlertExample from "./sections/IntersectionObserverAlertExample.svelte";
  import DisappearingDuckExample from "./sections/DisappearingDuckExample.svelte";
  import IntersectionObserverSectionCard from "./sections/IntersectionObserverSectionCard.svelte";
  import IntersectionObserverListExample from "./sections/IntersectionObserverListExample.svelte";
</script>

<main>
  <TitleSection />
  <RightAlignedNoGraph />
  <LeftAlignedEnrollmentGraph />
  <FirstTransition />
  <RightAlignedEarningsGraph />
  <SecondTransition />
  <LeftAlignedHouseholdGraph />
  <ThirdTransition />
  <FourthTransition />
  <RightAlignedPercentHolding />
  <FinalTransition />
  <AcknowledgementsSection />

  <IntersectionObserverSectionCard />
  <InteresectionObserverBasicExample />
  <IntersectionObserverAlertExample />
  <DisappearingDuckExample />
  <IntersectionObserverListExample />
</main>
