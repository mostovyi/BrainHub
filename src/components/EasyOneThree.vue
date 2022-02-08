<template>
  <div>
    <div>
      <button @click="getNewNumbersArray( repeats )">Result is: {{ answer }}</button>
    </div>
    <div>
      <div v-for="(element, i) in array" :key=" 'A'+ i">{{ element }} </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "EasyOneThree",
  data: function () {
    return {
      array: [],
      answer: 0
    }
  },
  // Input parameters
  props: {
    repeats : Number
  },
  // Digits generation function
  methods: {
    getNewNumbersArray : function (repeats) {
      console.log("EasyOneThree")
      let help = [];
      let helpAnswer = 0;
      let currentValue = 0;
      for(let i = 0; i < repeats; i++){

        switch (helpAnswer) {

          case 0: {
            currentValue = this.getRandomIntInclusive(1, 3);
            help.push(currentValue);
            helpAnswer += currentValue;
            break;
          }
          case 1: {
            let list1 = [1, 2, 3, -1];
            currentValue = this.getRandomIntInclusive(0, 3);
            currentValue = list1[currentValue];
            help.push(currentValue);
            helpAnswer += currentValue;
            break;
          }
          case 2: {
            let list2 = [-2, -1, 1, 2];
            currentValue = this.getRandomIntInclusive(0, 3);
            currentValue = list2[currentValue];
            help.push(currentValue);
            helpAnswer += currentValue;
            break;
          }
          case 3: {
            let list3 = [-3, -2, -1, 1];
            currentValue = this.getRandomIntInclusive(0, 3);
            currentValue = list3[currentValue];
            help.push(currentValue);
            helpAnswer += currentValue;
            break;
          }
          case 4: {
            let list4 = [-3, -2, -1];
            currentValue = this.getRandomIntInclusive(0, 2);
            currentValue = list4[currentValue];
            help.push(currentValue);
            helpAnswer += currentValue;
            break;
          }
        }
      }
      this.array = help;
      this.answer = helpAnswer;
    },
    // Generates random values
    getRandomIntInclusive : function (min, max) {
    min = Math.ceil(min);
    max = Math.floor(max);
    return Math.floor(Math.random() * (max - min + 1)) + min; //Максимум и минимум включаются
    }
  }
}
</script>

<style scoped>

</style>