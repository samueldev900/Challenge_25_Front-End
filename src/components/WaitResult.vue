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
        <div class="flex flex-col justify-center items-center">
            <img src="../assets/images/illustration-empty.svg" alt="">
            <h1 class="text-cor1 text-2xl font-extrabold my-5">Results shown here</h1>
            <p class="text-cor3 font-semibold text-center">
                Complete the form and click "calculate <br> repayments to see what your monthly <br> repayments would be"
            </p>
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