<script>
import Result from './Result.vue';

    export default {
  data() {
    return {
        isCheckedRepaymente: false,
        isCheckedInterestOny: false,
        selectedOption: '',
        amount: 0,
        envio: false,
        mAmount: 0,
        mTerm: 0,
        InterestRate: 0,
        MortgageType: '',
        resultMes: 0,
        resultFinal: 0
    };
  },
  methods: {
    checkAmount() {
      if (this.amount > 50) {
        this.amount = 50;
      }
    },
    calcularRepayment(){
        let P = 0;  
        let A = this.mAmount;  
        let r = (this.InterestRate / 100) / 12;  
        let n = parseInt(this.mTerm * 12);  
        P = (A * r * Math.pow(1 + r, n)) / (Math.pow(1 + r, n) - 1);
        let valorFinal = P * n;
        this.resultMes = parseFloat(P); 
        this.resultFinal = parseFloat(valorFinal);  
    },
    calcularInterestOnly() {
        let P = 0;  
        let A = parseFloat(this.mAmount) || 0;  
        let r = this.InterestRate / 100;  
        let n = this.mTerm * 12;  
        P = A * (r / 12);
        let valorFinal = (P * n) + A;
        this.resultMes = parseFloat(P) || 0;  
        this.resultFinal = parseFloat(valorFinal) || 0; 
    },
    updateRadioState() {
      this.isCheckedRepaymente = this.selectedOption === 'repay1';
      this.isCheckedInterestOny = this.selectedOption === 'repay2';
    },
    calcular(){
        if(this.isCheckedRepaymente){
            console.log('chegou aqui')
            this.calcularRepayment();
        }
        else if(this.isCheckedInterestOny){
            console.log('chegou aqui2')
            this.calcularInterestOnly()
        }
        this.envio = !this.envio;  
    }
}

};
</script>

<template>
    <div class="m-6">
        <h1 class="text-3xl font-extrabold text-cor5">Mortage Calculator</h1>

        <p class="border-cor5 w-16 text-sm text-cor5 border-b my-2 mb-6">Clear All</p>
        <form action="#">
            <div class="my-4">
                <label class="" for="amount">Mortage Amount</label>
                <div class="rounded-lg border border-gray-300 w-80 h-12  flex bg-white justify-between overflow-hidden">
                    <div class="bg-cor1 w-10 flex items-center justify-center font-bold p-2">
                        £
                    </div>
                    <input v-model="mAmount" type="text" id="amount" name="amount" class="outline-none w-72 p-4">
                </div>
            </div>
            <div class="my-4 ">
                <label class="p-2" for="amount">Mortage Term</label>
                <div class="rounded-lg border border-gray-300 w-80 h-12  flex bg-white justify-between overflow-hidden">
                    <input v-model="mTerm" type="number" class="outline-none w-72 p-4" max="50">
                    <div class="bg-cor1 w-16 flex items-center justify-center font-bold p-4">
                        Years
                    </div>
                </div>
            </div>
            <div class="my-4">
                <label class="" for="amount">Interest Rate</label>
                <div class="rounded-lg border border-gray-300 w-80 h-12  flex bg-white justify-between overflow-hidden">
                    <input v-model="InterestRate" type="number" name="amount" class="outline-none w-72 p-4">
                    <div class="bg-cor1 w-16 flex items-center justify-center font-bold p-4">
                        %
                    </div>
                </div>
            </div>
            <div>
                <h3 class="my-2">Mortgage Type</h3>
                <!-- Repayment Radio -->
                <div @click="selectedOption = 'repay1'; updateRadioState()" :class="['rounded-lg border w-80 h-12 flex items-center bg-white overflow-hidden p-4 my-2', selectedOption === 'repay1' ? 'border-cor6 bg-cor10' : 'border-gray-300']">
                    <input type="radio" name="repay" id="repay1" value="repay1" v-model="selectedOption" @change="updateRadioState" class="cursor-pointer">
                    <label class="px-4 cursor-pointer" for="repay1">Repayment</label>
                </div>

                <!-- Interest Only Radio -->
                <div @click="selectedOption = 'repay2'; updateRadioState()" :class="['rounded-lg border w-80 h-12 flex items-center bg-white overflow-hidden p-4 my-2', selectedOption === 'repay2' ? 'border-cor6 bg-cor10' : 'border-gray-300']">
                    <input type="radio" name="repay" id="repay2" value="repay2" v-model="selectedOption" @change="updateRadioState" class="cursor-pointer">
                    <label class="px-4 cursor-pointer" for="repay2">Interest Only</label>
                </div>
            </div>
            
            <div class="
                flex
                items-center
                justify-center
                w-80 h-12 
                bg-cor6 
                rounded-3xl 
                font-bold 
                my-3
                mt-6"
                @click="calcular()">
                    <img src="../assets/images/icon-calculator.svg" alt=""> Calculate Repayments
            </div>
        </form>
        <!--=============== WAIT RESULT =============== -->
        <div v-if="!envio" class="bg-cor5 p-5">
            <div class="flex flex-col justify-center items-center">
                <img src="../assets/images/illustration-empty.svg" alt="">
                <h1 class="text-cor1 text-2xl font-extrabold my-5">Results shown here</h1>
                <p class="text-cor3 font-semibold text-center">
                    Complete the form and click "calculate <br> repayments to see what your monthly <br> repayments would be"
                </p>
            </div>
        </div>

        <!-- Result=============== -->
        <div v-else class="bg-cor5 p-5">
            <h1 class="text-cor1 text-2xl font-extrabold my-5">Your Results</h1>
            <p class="text-cor3 font-semibold">Your results are shown below based on the information you provided. To adjust the results, edit the form and click "calculate repayments" again</p>
            <!-- Result================== -->
            <div class="bg-cor9 border-t-4 mt-7 p-2 border-cor6 rounded-md py-5 px-4">
            <h1 class="text-cor1">Your monthly repayments</h1 >
            <p class="text-4xl font-bold border-b border-cor4 py-4 text-cor6">£{{ resultMes.toFixed(2) }}</p>

            <div class="my-5">
                <p class="text-cor3">Total you'll repay over the term</p>
                <p class="text-2xl font-bold  text-cor1 my-2">£{{ resultFinal.toFixed(2) }}</p>
            </div>
        </div>
    </div>
    </div>
</template>

<style>

</style>