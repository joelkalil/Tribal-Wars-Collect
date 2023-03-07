<template>
    <!---------------------------------------------------------------------------------------------------->
    <!-- GitHub and LinkedIn-->
    <div class="contact">
      <a href="https://www.linkedin.com/in/joelkalil/">
      <img src="../assets/icons/linkedin.png" alt="Linkedin"></a>

      <a href="https://github.com/joelkalil">
      <img src="../assets/icons/github.png" alt="GitHub"></a>

      <h3> Joel Pontes </h3>
    
    </div>
    <!---------------------------------------------------------------------------------------------------->
    <!-- Title and subtitle -->
    <div class="title">
        <h1> Collect System - Tribal Wars</h1>
        <h3> System to help you to optmize your collect. </h3>

        <h3> Tutorial : </h3>
        <h4> 1. Add the number of troops desired in the equivalent position. </h4>
        <h4> 2. Select how many types of collect you want to use. </h4>
        <h4> 3. Get the result and put it in TW. </h4>
        <h4> Enjoy the collect ! </h4>
    </div>

    <!---------------------------------------------------------------------------------------------------->
    <!-- Section to add the quantity of each troop -->
    <div class="troops">
        <div class="troops-square">
            <img src="../assets/icons/spear.png" alt="Spear">
            <input
                v-model="resources.spear"
                type="number"
            />
        </div>
        <div class="troops-square">
            <img src="../assets/icons/sword.png" alt="Sword">
            <input
                v-model="resources.sword"
                type="number"
            />
        </div>
        <div class="troops-square">
            <img src="../assets/icons/axe.png" alt="Axe">
            <input
                v-model="resources.axe"
                type="number"
            />
        </div>
        <div class="troops-square">
            <img src="../assets/icons/archer.png" alt="Archer">
            <input
                v-model="resources.archer"
                type="number"
            />
        </div>
        <div class="troops-square">
            <img src="../assets/icons/light.png" alt="Light">
            <input
                v-model="resources.light"
                type="number"
            />
        </div>
        <div class="troops-square">
            <img src="../assets/icons/marcher.png" alt="Marcher">
            <input
                v-model="resources.marcher"
                type="number"
            />
        </div>
        <div class="troops-square">
            <img src="../assets/icons/heavy.png" alt="Heavy">
            <input
                v-model="resources.heavy"
                type="number"
            />
        </div>
        <div class="troops-square">
            <img src="../assets/icons/knight.png" alt="Knight">
            <input
                v-model="resources.knight"
                type="number"
            />
        </div>
    </div>

    <!---------------------------------------------------------------------------------------------------->
    <!-- Display where will show the quantity of each material collected. -->
    <div class="resources">
      <div class="resources-square">
        <img src="../assets/icons/resources.png" alt="Capacity">
        <input
            readonly
            v-model="calculateTotalCapacity"
            type="number"
        />
      </div>
      <div class="resources-square">
        <img src="../assets/icons/wood.png" alt="Wood">
        <input
            readonly
            v-model="wood"
            type="number"
        />
      </div>
      <div class="resources-square">
        <img src="../assets/icons/stone.png" alt="Stone">
        <input
            readonly
            v-model="stone"
            type="number"
        />
      </div>
      <div class="resources-square">
        <img src="../assets/icons/iron.png" alt="Iron">
        <input
            readonly
            v-model="iron"
            type="number"
        />
      </div>
    </div>

    <!---------------------------------------------------------------------------------------------------->
    <!---------------------------------------------------------------------------------------------------->
    <!-- Display where will show the quantity of each troop should be add, as well the resources collected
     for them. -->
    <!-- Low Collect -->
    <div class="collect">
      <div class="collect-box">
        <div class="collect-square">
          <input
            type="checkbox"
            value="Low Collect"
            v-model="collect.low"
          ><span> Low Collect </span>
        </div>
        <!---------------------------------------------------------------------------------------------------->
        <!-- Low Collect Resources -->
        <div v-if="capacity_collect.low" class="collect-square">
          <div class="collect-square-resource">
            <img src="../assets/icons/wood.png" alt="Wood">
            <input
                readonly
                v-model="capacity_collect.low"
                type="number"
            />
          </div>

          <div class="collect-square-resource">
            <img src="../assets/icons/stone.png" alt="Stone">
            <input
                readonly
                v-model="capacity_collect.low"
                type="number"
            />
          </div>

          <div class="collect-square-resource">
            <img src="../assets/icons/iron.png" alt="Iron">
            <input
                readonly
                v-model="capacity_collect.low"
                type="number"
            />
          </div>
        </div>
        <!---------------------------------------------------------------------------------------------------->
        <!-- Low Collect Troops -->
        <div v-if="collect.low && capacity_collect.low" class="collect-square">
          <div v-if="troops.low.spear" class="collect-square-troops-unit">
            <img src="../assets/icons/spear.png" alt="Spear">
            <input
                v-model="troops.low.spear"
                type="number"
            />
          </div>
          <div v-if="troops.low.sword" class="collect-square-troops-unit">
              <img src="../assets/icons/sword.png" alt="Sword">
              <input
                  v-model="troops.low.sword"
                  type="number"
              />
          </div>
          <div v-if="troops.low.axe" class="collect-square-troops-unit">
              <img src="../assets/icons/axe.png" alt="Axe">
              <input
                  v-model="troops.low.axe"
                  type="number"
              />
          </div>
          <div v-if="troops.low.archer" class="collect-square-troops-unit">
              <img src="../assets/icons/archer.png" alt="Archer">
              <input
                  v-model="troops.low.archer"
                  type="number"
              />
          </div>
          <div v-if="troops.low.light" class="collect-square-troops-unit">
              <img src="../assets/icons/light.png" alt="Light">
              <input
                  v-model="troops.low.light"
                  type="number"
              />
          </div>
          <div v-if="troops.low.marcher" class="collect-square-troops-unit">
              <img src="../assets/icons/marcher.png" alt="Marcher">
              <input
                  v-model="troops.low.marcher"
                  type="number"
              />
          </div>
          <div v-if="troops.low.heavy" class="collect-square-troops-unit">
              <img src="../assets/icons/heavy.png" alt="Heavy">
              <input
                  v-model="troops.low.heavy"
                  type="number"
              />
          </div>
          <div v-if="troops.low.knight" class="collect-square-troops-unit">
              <img src="../assets/icons/knight.png" alt="Knight">
              <input
                  v-model="troops.low.knight"
                  type="number"
              />
          </div>
        </div>
      </div>
      <!-------------------------------------------------------------------------------------------------->
      <!-------------------------------------------------------------------------------------------------->
      <!-- Medium Collect -->
      <div class="collect-box">
        <div class="collect-square">
          <input
            type="checkbox"
            value="Low Collect"
            v-model="collect.medium"
          ><span> Medium Collect </span>
        </div>
        <!---------------------------------------------------------------------------------------------------->
        <!-- Medium Collect Resources -->
        <div v-if="capacity_collect.medium" class="collect-square">
          <div class="collect-square-resource">
            <img src="../assets/icons/wood.png" alt="Wood">
            <input
                readonly
                v-model="capacity_collect.medium"
                type="number"
            />
          </div>

          <div class="collect-square-resource">
            <img src="../assets/icons/stone.png" alt="Stone">
            <input
                readonly
                v-model="capacity_collect.medium"
                type="number"
            />
          </div>

          <div class="collect-square-resource">
            <img src="../assets/icons/iron.png" alt="Iron">
            <input
                readonly
                v-model="capacity_collect.medium"
                type="number"
            />
          </div>
        </div>
        <!---------------------------------------------------------------------------------------------------->
        <!-- Medium Collect Troops -->
        <div v-if="collect.medium && capacity_collect.medium" class="collect-square">
          <div v-if="troops.medium.spear" class="collect-square-troops-unit">
            <img src="../assets/icons/spear.png" alt="Spear">
            <input
                v-model="troops.medium.spear"
                type="number"
            />
          </div>
          <div v-if="troops.medium.sword" class="collect-square-troops-unit">
              <img src="../assets/icons/sword.png" alt="Sword">
              <input
                  v-model="troops.medium.sword"
                  type="number"
              />
          </div>
          <div v-if="troops.medium.axe" class="collect-square-troops-unit">
              <img src="../assets/icons/axe.png" alt="Axe">
              <input
                  v-model="troops.medium.axe"
                  type="number"
              />
          </div>
          <div v-if="troops.medium.archer" class="collect-square-troops-unit">
              <img src="../assets/icons/archer.png" alt="Archer">
              <input
                  v-model="troops.medium.archer"
                  type="number"
              />
          </div>
          <div v-if="troops.medium.light" class="collect-square-troops-unit">
              <img src="../assets/icons/light.png" alt="Light">
              <input
                  v-model="troops.medium.light"
                  type="number"
              />
          </div>
          <div v-if="troops.medium.marcher" class="collect-square-troops-unit">
              <img src="../assets/icons/marcher.png" alt="Marcher">
              <input
                  v-model="troops.medium.marcher"
                  type="number"
              />
          </div>
          <div v-if="troops.medium.heavy" class="collect-square-troops-unit">
              <img src="../assets/icons/heavy.png" alt="Heavy">
              <input
                  v-model="troops.medium.heavy"
                  type="number"
              />
          </div>
          <div v-if="troops.medium.knight" class="collect-square-troops-unit">
              <img src="../assets/icons/knight.png" alt="Knight">
              <input
                  v-model="troops.medium.knight"
                  type="number"
              />
          </div>
        </div>
      </div>
      <!-------------------------------------------------------------------------------------------------->
      <!-------------------------------------------------------------------------------------------------->
      <!-- High Collect -->
      <div class="collect-box">
        <div class="collect-square">
          <input
            type="checkbox"
            value="High Collect"
            v-model="collect.high"
          ><span> High Collect </span>
        </div>
        <!---------------------------------------------------------------------------------------------------->
        <!-- High Collect Resources -->
        <div v-if="capacity_collect.high" class="collect-square">
          <div class="collect-square-resource">
            <img src="../assets/icons/wood.png" alt="Wood">
            <input
                readonly
                v-model="capacity_collect.high"
                type="number"
            />
          </div>

          <div class="collect-square-resource">
            <img src="../assets/icons/stone.png" alt="Stone">
            <input
                readonly
                v-model="capacity_collect.high"
                type="number"
            />
          </div>

          <div class="collect-square-resource">
            <img src="../assets/icons/iron.png" alt="Iron">
            <input
                readonly
                v-model="capacity_collect.high"
                type="number"
            />
          </div>
        </div>
        <!---------------------------------------------------------------------------------------------------->
        <!-- High Collect Troops -->
        <div v-if="collect.high && capacity_collect.high" class="collect-square">
          <div v-if="troops.high.spear" class="collect-square-troops-unit">
            <img src="../assets/icons/spear.png" alt="Spear">
            <input
                v-model="troops.high.spear"
                type="number"
            />
          </div>
          <div v-if="troops.high.sword" class="collect-square-troops-unit">
              <img src="../assets/icons/sword.png" alt="Sword">
              <input
                  v-model="troops.high.sword"
                  type="number"
              />
          </div>
          <div v-if="troops.high.axe" class="collect-square-troops-unit">
              <img src="../assets/icons/axe.png" alt="Axe">
              <input
                  v-model="troops.high.axe"
                  type="number"
              />
          </div>
          <div v-if="troops.high.archer" class="collect-square-troops-unit">
              <img src="../assets/icons/archer.png" alt="Archer">
              <input
                  v-model="troops.high.archer"
                  type="number"
              />
          </div>
          <div v-if="troops.high.light" class="collect-square-troops-unit">
              <img src="../assets/icons/light.png" alt="Light">
              <input
                  v-model="troops.high.light"
                  type="number"
              />
          </div>
          <div v-if="troops.high.marcher" class="collect-square-troops-unit">
              <img src="../assets/icons/marcher.png" alt="Marcher">
              <input
                  v-model="troops.high.marcher"
                  type="number"
              />
          </div>
          <div v-if="troops.high.heavy" class="collect-square-troops-unit">
              <img src="../assets/icons/heavy.png" alt="Heavy">
              <input
                  v-model="troops.high.heavy"
                  type="number"
              />
          </div>
          <div v-if="troops.high.knight" class="collect-square-troops-unit">
              <img src="../assets/icons/knight.png" alt="Knight">
              <input
                  v-model="troops.high.knight"
                  type="number"
              />
          </div>
        </div>
      </div>        
      <!-------------------------------------------------------------------------------------------------->
      <!-------------------------------------------------------------------------------------------------->
      <!-- Extreme Collect -->
      <div class="collect-box">
        <div class="collect-square">
          <input
            type="checkbox"
            value="Extreme Collect"
            v-model="collect.extreme"
          ><p> Extreme Collect </p>
        </div>
        <!---------------------------------------------------------------------------------------------------->
        <!-- Extreme Collect Resources -->
        <div v-if="capacity_collect.extreme" class="collect-square">
          <div class="collect-square-resource">
            <img src="../assets/icons/wood.png" alt="Wood">
            <input
                readonly
                v-model="capacity_collect.extreme"
                type="number"
            />
          </div>

          <div class="collect-square-resource">
            <img src="../assets/icons/stone.png" alt="Stone">
            <input
                readonly
                v-model="capacity_collect.extreme"
                type="number"
            />
          </div>

          <div class="collect-square-resource">
            <img src="../assets/icons/iron.png" alt="Iron">
            <input
                readonly
                v-model="capacity_collect.extreme"
                type="number"
            />
          </div>
        </div>
        <!---------------------------------------------------------------------------------------------------->
        <!-- Extreme Collect Troops -->
        <div v-if="collect.extreme && capacity_collect.extreme" class="collect-square">
          <div v-if="troops.extreme.spear" class="collect-square-troops-unit">
            <img src="../assets/icons/spear.png" alt="Spear">
            <input
                v-model="troops.extreme.spear"
                type="number"
            />
          </div>
          <div v-if="troops.extreme.sword" class="collect-square-troops-unit">
              <img src="../assets/icons/sword.png" alt="Sword">
              <input
                  v-model="troops.extreme.sword"
                  type="number"
              />
          </div>
          <div v-if="troops.extreme.axe" class="collect-square-troops-unit">
              <img src="../assets/icons/axe.png" alt="Axe">
              <input
                  v-model="troops.extreme.axe"
                  type="number"
              />
          </div>
          <div v-if="troops.extreme.archer" class="collect-square-troops-unit">
              <img src="../assets/icons/archer.png" alt="Archer">
              <input
                  v-model="troops.extreme.archer"
                  type="number"
              />
          </div>
          <div v-if="troops.extreme.light" class="collect-square-troops-unit">
              <img src="../assets/icons/light.png" alt="Light">
              <input
                  v-model="troops.extreme.light"
                  type="number"
              />
          </div>
          <div v-if="troops.extreme.marcher" class="collect-square-troops-unit">
              <img src="../assets/icons/marcher.png" alt="Marcher">
              <input
                  v-model="troops.extreme.marcher"
                  type="number"
              />
          </div>
          <div v-if="troops.extreme.heavy" class="collect-square-troops-unit">
              <img src="../assets/icons/heavy.png" alt="Heavy">
              <input
                  v-model="troops.extreme.heavy"
                  type="number"
              />
          </div>
          <div v-if="troops.extreme.knight" class="collect-square-troops-unit">
              <img src="../assets/icons/knight.png" alt="Knight">
              <input
                  v-model="troops.extreme.knight"
                  type="number"
              />
          </div>
        </div>
      </div>  
  </div>

</template>

<script>

export default {
    data() {
        return{
          resources: {
              spear: 0,
              sword: 0,
              axe: 0,
              archer: 0,
              light: 0,
              marcher: 0,
              heavy: 0,
              knight: 0,
          },
          collect: {
            low: true,
            medium: true,
            high: true,
            extreme: true,  
          },
          collect_factor: {
            low: 15,
            medium: 6,
            high: 3,
            extreme: 2,
          },
          troops:{
            low: {
              spear: 0,
              sword: 0,
              axe: 0,
              archer: 0,
              light: 0,
              marcher: 0,
              heavy: 0,
              knight: 0,
            },
            medium: {
              spear: 0,
              sword: 0,
              axe: 0,
              archer: 0,
              light: 0,
              marcher: 0,
              heavy: 0,
              knight: 0,
            },
            high: {
              spear: 0,
              sword: 0,
              axe: 0,
              archer: 0,
              light: 0,
              marcher: 0,
              heavy: 0,
              knight: 0,
            },
            extreme: {
              spear: 0,
              sword: 0,
              axe: 0,
              archer: 0,
              light: 0,
              marcher: 0,
              heavy: 0,
              knight: 0,
            },
          },
          total_factor: 0,
          capacity: 0,
          capacity_collect: {
            low: 0,
            medium: 0,
            high: 0,
            extreme: 0,
          },
          wood: 0,
          stone: 0,
          iron: 0,
        }
    },
    methods:{
      getCapacityOfTroops(){
        return {
          'spear': 25,
          'sword': 15,
          'axe': 10,
          'archer': 10,
          'light': 80,
          'marcher': 50,
          'heavy': 50,
          'knight': 100,
        }
      },
      updateFactor(){
        var total_factor = 0
        // Calculating total factor based in the collects factors.
        for(var element in this.collect){
          if (this.collect[element] == true) {
            total_factor += this.collect_factor[element]
          }
        }
        this.total_factor = total_factor
      },
      resetingResources(){
        this.capacity_collect.low = 0
        this.capacity_collect.medium = 0
        this.capacity_collect.high = 0
        this.capacity_collect.extreme = 0
      },
      calculateTroops(){
        // Updating the Factor, based in the collect options selected.
        this.updateFactor()
        this.resetingResources()
        // Calculating Low Troops
        if(this.collect.low == true){
          for(var troop in this.troops.low){
            this.troops.low[troop] = Math.round(this.resources[troop]*(this.collect_factor.low/this.total_factor))
          }
        }
        // Calculating Medium Troops
        if(this.collect.medium == true){          
          for(var troop in this.troops.medium){
            this.troops.medium[troop] = Math.round(this.resources[troop]*(this.collect_factor.medium/this.total_factor))
          }
        }
        // Calculating High Troops
        if(this.collect.high == true){          
          for(var troop in this.troops.high){
            this.troops.high[troop] = Math.round(this.resources[troop]*(this.collect_factor.high/this.total_factor))
          }
        }
        // Calculating Extreme Troops
        if(this.collect.extreme == true){          
          for(var troop in this.troops.extreme){
            this.troops.extreme[troop] = Math.round(this.resources[troop]*(this.collect_factor.extreme/this.total_factor))
          }
        }
      },
      calculateResources() {
        var capacity = 0
        const capacityTroops = this.getCapacityOfTroops()
        if(capacityTroops != 0){
          // Calculating the resources collected for each collect
          // Low
          if(this.collect.low == true){
            for(var element in this.resources){
              capacity += this.troops.low[element]*capacityTroops[element]
            }
            this.capacity_collect.low = Math.round(0.1*capacity/3)
          }
          // Medium
          if(this.collect.medium == true){
            capacity = 0
            for(var element in this.resources){
              capacity += this.troops.medium[element]*capacityTroops[element]
            }
            this.capacity_collect.medium = Math.round(0.25*capacity/3)
          }
          // High
          if(this.collect.high == true){
            capacity = 0
            for(var element in this.resources){
              capacity += this.troops.high[element]*capacityTroops[element]
            }
            this.capacity_collect.high = Math.round(0.50*capacity/3)
          }
          // Extreme
          if(this.collect.extreme == true){
            capacity = 0
            for(var element in this.resources){
              capacity += this.troops.extreme[element]*capacityTroops[element]
            }
            this.capacity_collect.extreme = Math.round(0.75*capacity/3)
          }

          // Calculating the total collect of each material
          capacity = this.capacity_collect.low + this.capacity_collect.medium + this.capacity_collect.high + this.capacity_collect.extreme
          this.wood = capacity
          this.stone = capacity
          this.iron = capacity
        }
      }
    },
    computed: {
      calculateTotalCapacity: {
        get(){
          var capacity = 0
          const capacityTroops = this.getCapacityOfTroops()
          for(var element in this.resources){
            capacity += this.resources[element]*capacityTroops[element]
          }
          this.capacity = capacity
          this.calculateTroops()
          this.calculateResources()
          console.log(this.capacity_collect)
          return capacity
        }
    }
  }
}

</script>


<style>
    /* Import Fonts*/
    @import url(//db.onlinewebfonts.com/c/f3258385782c4c96aa24fe8b5d5f9782?family=Old+English+Text+MT);

    body {
      background-attachment: fixed;
      background-color: #d2c09e;
      background-image: url('@/assets/img/bg-image.jpg');
      background-position: top center;
      background-repeat: no-repeat;
      background-size: cover;
      -moz-background-size: cover;
      -webkit-background-size: cover;
    }

    /* Removing Arrows of input */
    input::-webkit-outer-spin-button,
    input::-webkit-inner-spin-button {
        -webkit-appearance: none;
        margin: 0;
    }

    /* Input Style */
    input {
      background: none;
      background-color: none;
      text-align: center;
      text-rendering: auto;
      appearance: auto;
      border: none;
      padding: none;
      height: 2vh;
      overflow: hidden;
    }

    /* Removing focus outline */
    input:focus {
      outline: none;
    }

    .contact {
      font-family: 'Old English Text MT';
      font-size: 125%;
      text-align: center;
      display: flex;
      flex-direction: row;
      align-items: center;
      align-content: center;
      padding: 1vh;
    }

    .contact > a {
      padding: 1vh;
    }

    .contact > a > img {
      width: 3vh;
    }

    .title {
        font-family: 'Old English Text MT';
        font-size: 125%;
        text-align: center;
        margin-bottom: 5vh;
    }

    .troops, .resources, .collect {
        display: flex;
        flex-wrap: wrap;
        flex-direction: row;
        justify-content: center;
        margin-top: 5vh;
        margin-bottom: 10vh;
        margin-left: auto;
        margin-right: auto;
    }

    .troops-square, .resources-square{
        display: flex;
        height: 5vh;
        width: 10vw;
        min-height: 5vh;
        min-width: 10vw;
        padding: 4px 8px;
        margin: 4px;
        -webkit-box-align: center;
        align-items: center;
        background-color: #c1a264 !important;
        border-radius: 0.8rem;
        border: 2px solid #a37923;
        box-shadow: 1vh 1vh 2vh rgba(0,0,0,.5);
    }

    .collect-box {
      display: flex;
      flex-direction: column;
    }

    .collect-square {
        display: flex;
        flex-direction: column;
        height: auto;
        width: auto;
        min-height: 5vh;
        min-width: 10vw;
        padding: 4px 8px;
        margin: 25px;
        align-items: center;
        background-color: #c1a264 !important;
        border-radius: 0.8rem;
        border: 2px solid #a37923;
        box-shadow: 1vh 1vh 2vh rgba(0,0,0,.5);
    }

    .collect-square-resource,  .collect-square-troops-unit {
      display: flex;
      flex-direction: row;
      align-items: center;
      margin: 0.5vh;
    }

</style>