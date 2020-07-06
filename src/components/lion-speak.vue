<template>
  <div class="flex flex-col w-64 bg-gray-200 shadow-xl">
    <h3>Lion Speaks Component</h3>
    <div>
      <h5>Lions Says:</h5>
      <div>
        <textarea
          :value="lionText"
          @input="event => $emit('update:lionText', event.target.value)"
          class="border shadow p-1 mt-5 mb-5"
        ></textarea>
        <!-- <button class="bg-blue-300 text-white p-4 mb-4 rounded">Speaks For Himself</button> -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["lionText"]
  // model: {
  //   prop: "lionText",
  //   value: "input"
  // }
};
</script>

<style scoped></style>
