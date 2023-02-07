<template>
  <div>{{ text }}</div>
  <div>{{ obj.counter }}</div>
  <div>{{ fullName}}</div>
  <div>{{ username}}</div>
  <button ref="btn">Click</button>
</template>

<script setup>
import { ref, defineProps, defineExpose, reactive, watch, computed, toRefs, inject, watchEffect} from "vue";

const props = defineProps ({
        firstName: String,
        lastName: String,
 
});


const text = ref ("Hola vue");
    const obj = reactive({counter: 0});
    // const firstName = ref("Sebastian");
    // const lastName = ref("Navas");
    const { firstName, lastName} = toRefs(props);


   const fullName = computed(() => {
        return `${firstName.value} ${lastName.value}`;
   });
    setInterval(() =>obj.counter++, 500);

    watch(() =>obj.counter, (valor, anterior)  =>{
        console.log(valor, anterior);
    });

    const username = inject("username");

    // const metodos = () => console.log();
   defineExpose({
    fullName,
   });

   const btn = ref(null);

   watch (btn, (valor) => {
        console.log(valor);
   });
// export default {
//     props: 
//   setup(props, {expose}) {

//     return {
//         text,
//         obj,
//         firstName,
//         lastName,
//         fullName,
//         username,
//         btn,
//     }
//   },
// };
</script>
