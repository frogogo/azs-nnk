<template>
  <div class="flex items-center">
    <div class="codes mr-6">
      <span class="codes__count">+{{ codes }}</span>
      <span class="codes__label">{{codesPlural(codes)}}</span>
    </div>
    <div class="price__wrapper">
      <span class="price__label text-primary-500">Акционная цена:</span>
      <div class="price text-primary-500 font-bold">
        <span class="price__amount">
          {{ discountedPrice.toLocaleString("ru-RU") }}
        </span>
        <small class="price__currency">₽</small>
      </div>
    </div>
    <span class="divider mx-4 md:mx-5" />
    <div class="price__wrapper">
      <span class="price__label text-grey-700">Обычная цена:</span>
      <div class="price text-grey-700 font-light">
        <span class="price__amount">
          {{ price.toLocaleString("ru-RU") }}
        </span>
        <small class="price__currency">₽</small>
      </div>
    </div>
  </div>
</template>

<script>
const pluralRules = new Intl.PluralRules('ru-RU');

export default {
  props: {
    price: Number,
    discountedPrice: Number,
    codes: Number,
    frogogoDiscount: Number,
  },
  methods: {
    codesPlural(code) {
      const translates = {
        one: 'фишка',
        few: 'фишки',
        many: 'фишек'
      }

      return translates[pluralRules.select(code)]
    }
  }
};
</script>

<style scoped>
.frogogo__label {
  @apply font-bold uppercase;

  font-size: 10px;
}

.divider {
  @apply bg-grey-500 rounded;
  width: 2px;
  height: 36px;
}

.codes {
  @apply flex flex-col items-center bg-primary-500 p-1;

  border-radius: 10px;
  width: 80px;
  height: 60px;
  flex-shrink: 0;
}

.codes__count {
  @apply text-white;

  font-weight: 500;
  font-size: 30px;
  line-height: 38px;
}

.codes__label {
  @apply tracking-widest mb-1 text-white font-bold;

  line-height: 18px;
  font-size: 14px;
}

.price__wrapper {
  display: flex;
  flex-direction: column;
  align-content: space-between;
  height: 60px;
}

.price {
  font-size: 28px;
  line-height: 28px;

  display: flex;
  align-items: baseline;
}

.price__amount {
  font-size: 46px;
  line-height: 46px;
}

.price__currency {
  @apply ml-1;
  font-size: 0.5em;
}

.price__label {
  @apply font-bold uppercase;
  font-size: 8px;
}

.price--xl {
  @apply text-primary-500;
  font-size: 45px;
  line-height: 45px;

  margin-top: -4px;
}

.price--xl .price__amount {
  font-size: 48px;
  font-weight: bold;
}

.price--xl .price__penny {
  font-size: 1em;
  line-height: 1em;
}

.discounted-price {
  line-height: 1em;
  font-size: 1em;
}

.frogogo {
  font-family: "Rubik";
  font-size: 7px;
}

@media (min-width: 640px) {
  .frogogo {
    font-size: 14px;
  }

  .frogogo__label {
    @apply pb-1;
    font-size: 16px;
  }

  .price {
    font-size: 36px;
    line-height: 36px;
  }

  .price--xl {
    font-size: 80px;
    line-height: 80px;
  }

  .divider {
    width: 2px;
    height: 60px;
  }

  .price__label {
    @apply pb-1 text-xs;
  }

  .codes__count {
    font-size: 38px;
    line-height: 38px;
  }

  .codes__label {
    line-height: 18px;
    font-size: 14px;
  }
}
</style>