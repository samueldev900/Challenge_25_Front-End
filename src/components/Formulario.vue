<script>

</script>

<template>
    <div class="m-6">
        <h1 class="text-3xl font-extrabold text-cor5">Mortage Calculator</h1>

        <p class="border-cor5 w-16 text-sm text-cor5 border-b my-5">Clear All</p>
        <form action="#">
            <div class="my-4">
                <label class="" for="amount">Mortage Amount</label>
                <div class="rounded-lg border border-gray-300 w-80 h-12  flex bg-white justify-between overflow-hidden">
                    <div class="bg-cor2 w-10 flex items-center justify-center font-bold p-2">
                        €
                    </div>
                    <input type="text" name="amount" class="outline-none w-72 p-4">
                </div>
            </div>
            <div class="my-4">
                <label class="" for="amount">Mortage Term</label>
                <div class="rounded-lg border border-gray-300 w-80 h-12  flex bg-white justify-between overflow-hidden">
                    <input type="text" name="amount" class="outline-none w-72 p-4">
                    <div class="bg-cor2 w-16 flex items-center justify-center font-bold p-4">
                        Years
                    </div>
                </div>
            </div>
            <div class="my-4">
                <label class="" for="amount">Interest Rate</label>
                <div class="rounded-lg border border-gray-300 w-80 h-12  flex bg-white justify-between overflow-hidden">
                    <input type="text" name="amount" class="outline-none w-72 p-4">
                    <div class="bg-cor2 w-16 flex items-center justify-center font-bold p-4">
                        %
                    </div>
                </div>
            </div>
            <div>
                <h3 class="my-2">Mortage Type</h3>
                <div class="rounded-lg border border-gray-300 w-80 h-12  flex items-center bg-white  overflow-hidden p-4 my-2">
                    <input type="radio" name="rapay" id="repay1">
                    <label class="px-4" for="repay1">Rapayment</label>
                </div>
                <div class="rounded-lg border border-gray-300 w-80 h-12  flex items-center bg-white  overflow-hidden p-4 my-2">
                    <input type="radio" name="rapay" id="repay2">
                    <label class="px-4" for="repay2" >Interest Only</label>
                </div>
            </div>
            <a class="" href="#">
                <button class=" w-80 h-12 bg-cor6 rounded-3xl font-bold my-3">
                    Calculate Repayments
                </button>
            </a>
        </form>
    </div>
</template>

<style>

</style>