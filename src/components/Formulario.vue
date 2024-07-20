<script>
    export default {
    data() {
        return {
        selectedOption: '' // Inicialmente nenhum rádio está selecionado
        };
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
                    <input type="text" name="amount" class="outline-none w-72 p-4">
                </div>
            </div>
            <div class="my-4 ">
                <label class="p-2" for="amount">Mortage Term</label>
                <div class="rounded-lg border border-gray-300 w-80 h-12  flex bg-white justify-between overflow-hidden">
                    <input type="text" name="amount" class="outline-none w-72 p-4">
                    <div class="bg-cor1 w-16 flex items-center justify-center font-bold p-4">
                        Years
                    </div>
                </div>
            </div>
            <div class="my-4">
                <label class="" for="amount">Interest Rate</label>
                <div class="rounded-lg border border-gray-300 w-80 h-12  flex bg-white justify-between overflow-hidden">
                    <input type="text" name="amount" class="outline-none w-72 p-4">
                    <div class="bg-cor1 w-16 flex items-center justify-center font-bold p-4">
                        %
                    </div>
                </div>
            </div>
            <div>
                <h3 class="my-2">Mortgage Type</h3>
                <div :class="['rounded-lg border w-80 h-12 flex items-center bg-white overflow-hidden p-4 my-2', selectedOption === 'repay1' ? 'border-cor6 bg-cor10' : 'border-gray-300']">
                <input type="radio" name="rapay" id="repay1" value="repay1" v-model="selectedOption">
                <label class="px-4" for="repay1">Repayment</label>
                </div>
                <div :class="['rounded-lg border w-80 h-12 flex items-center bg-white overflow-hidden p-4 my-2', selectedOption === 'repay2' ? 'border-cor6 bg-cor10' : 'border-gray-300']">
                <input type="radio" name="rapay" id="repay2" value="repay2" v-model="selectedOption">
                <label class="px-4" for="repay2">Interest Only</label>
                </div>
            </div>
            <a class="" href="#">
                <button class="
                flex
                items-center
                justify-center
                w-80 h-12 
                bg-cor6 
                rounded-3xl 
                font-bold 
                my-3
                mt-6">
                    <img src="../assets/images/icon-calculator.svg" alt=""> Calculate Repayments
                </button>
            </a>
        </form>
    </div>
</template>

<style>

</style>