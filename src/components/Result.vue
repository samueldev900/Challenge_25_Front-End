<script>
 export default {
  data() {
    return {
      selectedOption: '',
      amount: 0 
    };
  },
  methods: {
    checkAmount() {
      if (this.amount > 50) {
        this.amount = 50;
      }
    }
  }
};
</script>

<template>
    <div class="bg-cor5 p-5">
        <h1 class="text-cor1 text-2xl font-extrabold my-5">Your Results</h1>
        <p class="text-cor3 font-semibold">Your results are shown below based on the information you provided. To adjust the results, edit the form and click "calculate repayments" again</p>

        
        <div class="bg-cor9 border-t-4 mt-7 p-2 border-cor6 rounded-md py-5 px-4">
          <h1 class="text-cor1">Your monthly repayments</h1 >
          <p class="text-4xl font-bold border-b border-cor4 py-4 text-cor6">£1,797.74</p>

          <div class="my-5">
            <p class="text-cor3">Total you'll repay over the term</p>
            <p class="text-2xl font-bold  text-cor1 my-2">£539,322.94</p>
          </div>
        </div>
    </div>
</template>

<style>

:root {
  --cor1: hsl(202, 86%, 94%);
  --cor2: hsl(203, 41%, 72%);
  --cor3: hsl(200, 26%, 54%);
  --cor4: hsl(200, 24%, 40%);
  --cor5: hsl(202, 55%, 16%);
  --lime: hsl(61, 70%, 52%);
  --red: hsl(4, 69%, 50%);
  --custom-green: #133040;
  --custom-green: #0e2431;
}

#resultado{
    width: 100%;
    background-color: var(--cor5);

}

</style>