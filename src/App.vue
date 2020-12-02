<template>
  <div id="app" v-cloak>
    <Header />
    <PromoSection />
    <HowTo />
    <Collections />
    <Participants />
  </div>
</template>

<script>
import Header from "./components/Header";
import PromoSection from "./components/PromoSection";
import HowTo from "./components/HowTo";
import Collections from "./components/Collections";
import Participants from "./components/Participants";
import AnalyticsEvents from "@/data/analyticsEvents";
import data from "@/data/data"

export default {
  name: "app",
  components: {
    Header,
    HowTo,
    Collections,
    Participants,
    PromoSection,
  },
};
</script>

<style lang="css">
body {
  background: url("assets/images/patern.jpg");
  background-size: 960px;
  min-width: 320px;
  font-family: "Rubik", system-ui, -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif;
}

button {
  outline: 0;
}

.text-thin {
  font-family: "Rubik";
}

.text-light {
  font-family: "Rubik";
}

.text-regular {
  font-family: "Rubik";
}

.text-bold {
  font-family: "Rubik";
  font-weight: bold;
}

.text-extra-bold {
  font-family: "Rubik";
}

.text-karusel-regular {
  font-family: "Rubik";
}

.text-karusel-small {
  font-family: "Rubik";
}

[v-cloak] {
  @apply hidden;
}

#app {
  @apply overflow-x-hidden;
}

.v-lazy-image {
  filter: blur(0.5rem);
  transition: filter 0.5s;
}
.v-lazy-image-loaded {
  filter: blur(0);
}
</style>
