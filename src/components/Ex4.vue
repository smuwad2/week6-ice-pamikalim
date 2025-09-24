<script>

    export default { 
        data() {
            return {
                // Add code here
                id: "demo1",
                isRed: false,
                blueBoth: true
            }
        },
        methods: { 
   			// Add code here
            changeColor(){
                this.isRed = !this.isRed;
                this.blueBoth = !this.blueBoth
            }
		}
    }
</script>

<template>
    
    <!-- Modify code here -->
    <div class="container">
        <div v-bind:id="id" class="m-2" :class="isRed ? 'redBox' : 'blueBox'">
            <!-- or v-bind:class="{'blueBox': blueBoth, 'redBox': !blueBoth}"-->
            div ID : {{id}} 
        </div>
        
        <button type="button" v-on:click="changeColor":class="isRed ? 'btn btn-danger' : 'btn btn-primary'">Change Color</button>
    </div>

</template>

<style scoped>
    .redBox {
        background-color: red;
    }
    .blueBox {
        background-color: blue;
    }
    #demo1 {
        color: white;
    }
</style>
