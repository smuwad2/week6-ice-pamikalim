<script>
import { isAbsolute } from 'path';

    export default { 
        data() {
            return {
                // Add code here
                id: "demo1",
                isRed: false
            }
        },
        methods: { 
   			// Add code here
            changeColor(){
                this.isRed = !this.isRed;
            }
		}
    }
</script>

<template>
    
    <!-- Modify code here -->
    <div class="container">
        <div v-bind:id="id" class="m-2" :class="isRed ? 'redBox' : 'blueBox'">
            div ID : {{id}} 
        </div>
        
        <button type="button" v-on:click="changeColor":class="isRed ? 'btn btn-danger' : 'btn btn-secondary'">Change Color</button>
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
