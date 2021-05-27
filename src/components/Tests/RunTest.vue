<template>
    <div>

    </div>
</template>

<script>
import Run from 'run-sdk'
import { onMounted } from '@vue/runtime-core'
class Counter extends Run.Jig {
    init() {
        this.value = 0
    }

    inc() {
        this.value += 1
    }
}
export default {
    async setup () {
         let run = new Run({trust: "*", 
                      purse: "<Replace Me>", 
                      owner: "<Replace Me>",
                      network: "test"})
        run.activate()
        console.log("Run Activated")
    const syncJigs = async (_run) => {
      console.log("Syncing...")
      await _run.inventory.sync()
      console.log("Inventory Sync Complete:", _run.inventory.jigs)
    }
    const createCounter = async (_run) => {
        _run.activate()
         const counter = new Counter()
        // Incremement a couple of times
        counter.inc()
        counter.inc() 
        await counter.sync()
    }
    onMounted(async () => {
       await createCounter(run)
       await syncJigs(run)
    })
    

      // Load a second instance of the same counter using the previous counter's 'location'
      //const counter2 = await run.load(counter.location)

      // Check that these counters are actually the same
    //console.log('counters the same:', counter.value === counter2.value)
   
    return{run}
    }
}
</script>

<style lang="scss" scoped>

</style>