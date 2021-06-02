<template>
    <div class="grid md:grid-cols-2 gap-4">
        <div class="shadow-md bg-blue-100 p-10 text-center rounded">
            <h3 class="text-3xl text-blue-900 font-bold mb-4">Cases</h3>
            <div class="text-2xl mb-4">
                <span class="font-bold">New:</span>
                {{number(stats.NewConfirmed)}}
            </div>
            <div class="text-2xl mb-4">
                <span class="font-bold">Total:</span>
                {{number(stats.TotalConfirmed)}}
            </div>
        </div>

         <div class="shadow-md bg-blue-200 p-10 text-center rounded">
            <h3 class="text-3xl text-blue-900 font-bold mb-4">Deaths</h3>
            <div class="text-2xl mb-4">
                <span class="font-bold">New:</span>
                {{number(stats.NewDeaths)}}
            </div>
            <div class="text-2xl mb-4">
                <span class="font-bold">Total:</span>
                {{number(stats.TotalDeaths)}}
            </div>
        </div>
        
    </div>
</template>

<script>
    export default {
        name: 'DataBoxes',
        props: ['stats'],
        methods: {
            number(x) {
                return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
            }
        }
    }
</script>