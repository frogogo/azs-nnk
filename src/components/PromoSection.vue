<template>
  <section class="section">
    <div class="container flex flex-col-reverse sm:items-center md:flex-row">
      <div class="description flex-1 md:mr-20 w-1/2">
        <h1 class="mb-4 text-white font-bold text-2xl lg:text-4xl leading-none">
          <span class="title">КОЛЛЕКЦИЯ НОЖЕЙ</span>
        </h1>
        <div class="flex mt-8 mb-6">
          <img
            :src="require('@/assets/images/logo-blaupunkt.svg')"
          />
          <img
            class="h-16 ml-6"
            :src="require('@/assets/images/mark-blaupunkt.png')"
          />
        </div>
     
        <div class="text-white text-base font-light">
          <p class="mb-4">
          Компания Blaupunkt* была основана в 1923 году в Берлине. В настоящее время продукция данного бренда представлена широким ассортиментом высококачественных товаров для дома.
          </p>
          <p class="mb-8">
          Ножи выполнены из нержавеющей стали марки  X30Cr13. Изделия обладают отличными антикоррозийными свойствами, износостойкостью и высокой прочностью. Режущая кромка лезвия хорошо подается заточке и длительное время удерживает остроту. Бесшовное соединение клинка с рукоятью придает ножам  эстетичный внешний вид. Благодаря удобной ручке нож  хорошо ложится  в руку и не выскальзывает в процессе работы.
          </p>
          <p>* Блаупункт</p>
        </div>
      </div>
    </div>
    <a
      href="#how-to"
      v-smooth-scroll="{ duration: 300, offset: -100 }"
      class="flex flex-1 items-center mb-6"
    >
      <img
        :src="require('@/assets/images/icon-down.svg')"
        class="hidden md:block mx-auto"
        alt="Вниз"
      />
    </a>
  </section>
</template>

<style scoped>
.section {
  @apply flex flex-col pt-8;

  background-image: url("~@/assets/images/header.jpg");
  background-size: cover;
  margin-top: 100px;
  min-height: calc(100vh - 100px);
}

.description {
  max-width: 460px;
}

.title {
  @apply text-white text-6xl font-normal font-bold leading-tight;
}

.subtitle {
  @apply text-white text-xl;
}
</style>