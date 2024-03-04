<script setup>
const route = useRoute();
const {cars} = useCars()
const {toTitleCase} = useUtilities();


useHead({
  title: toTitleCase(route.params.name),
});

const car = computed(() => {
  return cars.find((c) => {
    return c.id === parseInt(route.params.id)
  });
});

definePageMeta({
  layout: "custom",
});

// function toTitleCase(str) {
//   return str.replace(
//     /\w\S*/g,
//     function(txt) {
//       return txt.charAt(0).toUpperCase() + txt.substr(1).toLowerCase();
//     }
//   );
// }
</script>


<template>
   <div v-if="car">

   {{route.params.id}}
       
   <SearchBar />
    <CarDetailHero :car="car" />
   <CarDetailAttributes :features="car.features" />
   <CarDetailDescription :descriptioon="car.description"/>
   <CardetailContact />
 
  <!-- CAR DESCRISPTION -->
  
  <!-- CAR DESCRISPTION -->
  <!-- CAR CONTACT -->
  
  <!-- CAR CONTACT -->
</div>
  

</template>