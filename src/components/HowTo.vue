<template>
  <div class="py-20">
    <div class="container text-black">
      <h2
        class="text-bold text-3xl md:text-5xl leading-tight mb-10 md:mb-32 text-center"
        id="how-to"
      >
        Как принять <br />
        участие в акции?
      </h2>
      <div class="lg:flex lg:justify-between mb-10 md:mb-32">
        <div
          :key="step.number"
          v-for="step in steps"
          class="text-center mb-10 lg:mb-0 lg:mr-10 relative"
        >
          <div class="step text-karusel-regular" :data-step="step.number" />
          <inline-svg
            :src="step.iconUrl"
            class="w-32 h-32 md:w-48 md:h-48 mb-5 mx-auto"
          />
          <p class="text-bold text-xl">{{ step.title }}</p>
          <span class="text-4xl" v-if="step.notBold">
            {{ step.notBold }}
          </span>
          <span class="text-bold text-4xl" v-if="step.bold">{{ step.bold }}</span>
        </div>
      </div>
      <div class="flex flex-col sm:flex-row justify-center">
        <a
          href="/files/rules.pdf"
          class="btn btn-primary text-bold sm:mr-5 mb-6 sm:mb-0"
          target="_blank"
        >
          Правила акции
        </a>
        <a
          href="/files/booklet.pdf"
          class="btn btn-white text-bold"
          target="_blank"
        >
          Скачать буклет
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HowTo",
  data() {
    return {
      steps: [
        {
          number: "1",
          iconUrl: require("@/assets/images/steps/step-1.svg"),
          title: "Совершайте покупки",
          notBold: "от",
          bold: "400 рублей",
        },
        {
          number: "2",
          iconUrl: require("@/assets/images/steps/step-2.svg"),
          title: "Копи",
          bold: "ФИШКИ",
        },
        {
          number: "3",
          iconUrl: require("@/assets/images/steps/step-3.svg"),
          title: "Получай скидку",
          notBold: "до",
          bold: "71%",
        },
      ],
    };
  },
};
</script>

<style scoped lang="css">
.btn {
  @apply py-3 px-5 border-2 uppercase rounded-full text-white text-sm text-center transition-all duration-150 leading-none;
}

.btn-primary {
  @apply bg-primary-500 border-primary-500;
}

.btn-white {
  @apply bg-transparent border-2 border-grey-500 text-grey-700;
}

.btn-primary:hover {
  @apply bg-primary-300;
}

.btn-white:hover {
  @apply bg-white text-primary-500;
}

.step {
  height: 72px;
  width: 72px;
  @apply absolute top-0;
}

.step::after {
  @apply rounded-lg;
  content: "";
  display: block;
  transform: rotate(45deg);
  width: 100%;
  height: 100%;
  background: white;
  opacity: 0.2;
}

.step::before {
  content: attr(data-step);

  @apply absolute w-full h-full flex items-center justify-center text-white text-5xl;
}

@media (min-width: 768px) {
  .step {
    left: 5rem;
  }
}

@media (min-width: 1024px) {
  .step {
    left: -2rem;
  }
}
</style>
