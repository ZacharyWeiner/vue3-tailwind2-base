<template>
    <div>

    </div>
</template>

<script>
import { reactive, toRefs } from 'vue'
import {Computer} from "bitcoin-computer"

export default {
    async setup () {
        const importFile = async(fileName) => {
            console.log(process.env.BASE_URL + "contracts/" + fileName);
            const response = await fetch(
                process.env.BASE_URL + "contracts/" + fileName
            );
            return response.text();
        }
        const computer = new Computer({
            seed: "crane stove nuclear retreat join era option develop region allow hotel square",
            chain: 'BSV', // BSV or BCH
            network: 'testnet', // testnet or livenet
            path: "m/44'/0'/0'/0" // defaults to "m/44'/0'/0'/0"
        })
        let {wallet} = computer.db;
        console.log("Comp Details", wallet.getPublicKey().toString(), wallet.getAddress().toString())
        console.log(await wallet.getBalance())
         const Counter = await importFile("counter.js")
        //`class Counter {
        // constructor() { this.n = 0 }
        // inc() { this.n += 1 }
        // }`;
        console.log(Counter)
        let counter;
        try{
            counter = await computer.new(Counter, [])
            console.log({counter})
           
        }catch(err){
            console.log("Error before inc()", err);
        }
        try{
        await counter.inc()
        } catch(err){        
            console.log("Error on inc()", counter)
        }

        const state = reactive({
            count: 0,
        })
    
        return {
            ...toRefs(state),
        }
    }
}
</script>

<style lang="scss" scoped>

</style>