<template>
  <div class="pt-10 pb-32">
    <div class="container" id="collections">
      <h2 class="text-bold text-3xl md:text-5xl leading-tight mb-32 text-center">
        Коллекция товаров Blaupunkt
      </h2>
      <div class="collections">
        <Collection
          :key="collection.id"
          v-for="(collection, index) in collections"
          :positionLeft="index % 2 == 0"
          :collection="collection"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Collection from "@/components/Collection.vue";
import CollectionsData from "@/data/collectionsData.js";

export default {
  name: "Collections",
  components: {
    Collection,
  },
  data() {
    return {
      collections: CollectionsData,
    };
  },
};
</script>

<style scoped lang="css">
</style>
