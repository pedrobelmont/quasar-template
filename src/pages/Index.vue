<template>
  <q-page class="q-ma-xl">
    <div class="text-grey-13">home -> category 1 ->  product page </div>
      <div class="q-col-gutter-xs row items-start">
        <!-- foto -->
        <div class="col-6">
          <div>      
            <q-img src="https://cdn.quasar.dev/img/parallax2.jpg " 
              :ratio="1" id="imagen" class="q-mb-sm">
                <q-icon class="absolute all-pointer-events" size="32px" name="favorite_border" color="white" style="top: 8px; left: 8px">
                  <q-tooltip>
                    favorito
                  </q-tooltip>
                </q-icon>
              </q-img>
            </div>
            <div class="row q-col-gutter-sm">
              <div class="col-4"> <q-img src="https://cdn.quasar.dev/img/parallax2.jpg "></q-img> </div>
              <div class="col-4"> <q-img src="https://cdn.quasar.dev/img/parallax2.jpg "></q-img> </div>
              <div class="col-4"> <q-img src="https://cdn.quasar.dev/img/parallax2.jpg "></q-img> </div>
            </div>
          </div>
        <!-- informção lado da foto -->
        <div class="col-6 text-bold text-h2">
          product page 
            <div class="text-h5  q-ma-sm"> 
              <q-rating
                v-model="ratingModel"
                size="xl"
                :max="5"
                color="primary"/>
            <div><a href="#reviews">read reviews</a></div>
          </div>
            <div class="text-h5 text-grey-13 q-ma-sm"> Nossa loja tem uma seção exclusiva de roupas com tamanhos grandes, com tendências sempre em alta e preços super em baixa. Aproveite.</div>
            <div class="row text-h3 q-ml-sm">
             <div> <s style="font-size:50%;position: relative; top: -7px; ">600</s></div> <div style="color: rgb(29,29,201); font-size:50%;"> |50% OFF</div>  $300
            </div>
          <div class="row q-ma-sm"> 
            <div style="max-width: 300px" class="col-5"> <q-select rounded outlined v-model="model" :options="options" label="size" /></div>
              <div class="text-h6 text-grey-3 col-5 q-mx-sm">
                <div style=" background-color: rgb(120,120,120); padding: 10px; border-radius: 25px; " v-if="model=='GG'"> 1 ropa no estoque</div>
                <div style=" background-color: rgb(120,120,120); padding: 10px; border-radius: 25px; " v-if="model=='P'"> sem ropa no estoque</div>
                <div style=" background-color: rgb(120,120,120); padding: 10px; border-radius: 25px; " v-if="model=='PP'"> 6 ropas no estoque</div>
                <div style=" background-color: rgb(120,120,120); padding: 10px; border-radius: 25px; " v-if="model=='M'"> 20 ropas no estoque</div>
                <div style=" background-color: rgb(120,120,120); padding: 10px; border-radius: 25px; " v-if="model=='G'"> 4 ropas no estoque</div>
            </div> <div class="q-pa-md">
              <div class="text-h5 "> choose color </div>
              <div><q-btn round color="red"></q-btn><q-btn class="q-ml-sm" round color="blue"></q-btn><q-btn class="q-ml-sm" round color="yellow"></q-btn><q-btn class="q-ml-sm" round color="green"></q-btn></div>
              <div><q-btn @click="add" size=lg class="text-accent" color="grey-7">add cart </q-btn></div>
              <div class="row">
                <div style="max-width: 126px"><q-tabs><q-tab name="tab1"><q-img style="height: 50px; max-width: 50px" src="~assets/paypal.png"></q-img></q-tab></q-tabs></div>
                <div style="max-width: 126px"><q-tabs><q-tab name="tab1"><q-img style="height: 50px; max-width: 50px" src="~assets/mastercard.png"></q-img></q-tab></q-tabs></div>
                <div style="max-width: 126px"><q-tabs><q-tab name="tab1"><q-img style="height: 50px; max-width: 50px" src="~assets/symbols.png"></q-img></q-tab></q-tabs></div>
                <div style="max-width: 126px"><q-tabs><q-tab name="tab1"><q-img style="height: 50px; max-width: 50px" src="~assets/amex.png"></q-img></q-tab></q-tabs></div>
              </div>
            </div>
          </div>
        </div>
      </div>
          <div>  
            <div class="q-pa-md">
          <q-tabs
            v-model="tab"
            dense
            class="text-grey"
            active-color="primary"
            indicator-color="primary"
            align="justify"
            narrow-indicator>
          <q-tab name="ds1" label="discrição1"></q-tab>
          <q-tab name="ds2" label="decrição2"></q-tab>
          <q-tab name="ds3" label="decrição3"></q-tab>
          <q-tab name="ds4" label="decrição4"></q-tab>
          <q-tab name="ds5" label="decrição5"></q-tab>
          </q-tabs>
          <q-separator></q-separator>
          <q-tab-panels v-model="tab" animated>
            <q-tab-panel name="ds1">
            <div class="text-h6">decrição1</div>
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
            </q-tab-panel>
            <q-tab-panel name="ds2">
            <div class="text-h6">decrição2</div>
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
            </q-tab-panel>
            <q-tab-panel name="ds3">
            <div class="text-h6">decrição3</div>
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
            </q-tab-panel>
              <q-tab-panel name="ds4">
            <div class="text-h6">decrição4</div>
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
            </q-tab-panel>
            <q-tab-panel name="ds5">
            <div class="text-h6">decrição5</div>
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
            </q-tab-panel>  
          </q-tab-panels>
        </div>
          <div class="q-mt-xl"> 
          <div id="reviews" class="text-h4 flex flex-center"> coston reviews </div>
          <div class="row q-col-gutter-sm">
            <div class="col-4">
              <q-card bordered class=" my-card">
                <q-item>
                <q-item-section avatar>
                  <q-avatar>
                    <img src="https://cdn.quasar.dev/img/avatar2.jpg">
                   </q-avatar>
                  </q-item-section>
                  <q-card-section>
                  <div><q-rating
                    v-model="ratingModel2"
                    size="xl"
                    :max="5"
                    color="primary"/></div>
                  </q-card-section>
                </q-item>
                <q-separator/>
                <q-card-section>
                  péssimo vim compra ropa e aparece uma ponte
                </q-card-section>
              </q-card>
            </div>
              <div class="col-4">
              <q-card bordered class=" my-card">
                <q-item>
                <q-item-section avatar>
                  <q-avatar>
                    <img src="https://cdn.quasar.dev/img/avatar2.jpg">
                   </q-avatar>
                  </q-item-section>
                  <q-card-section>
                  <div><q-rating
                    v-model="ratingModel2"
                    size="xl"
                    :max="5"
                    color="primary"/></div>
                  </q-card-section>
                </q-item>
                <q-separator/>
                <q-card-section>
                  péssimo vim compra ropa e aparece uma ponte
                </q-card-section>
              </q-card>
            </div>
            <div class="col-4">
              <q-card bordered class=" my-card">
                <q-item>
                <q-item-section avatar>
                  <q-avatar>
                    <img src="https://cdn.quasar.dev/img/avatar2.jpg">
                   </q-avatar>
                  </q-item-section>
                  <q-card-section>
                  <div><q-rating
                    v-model="ratingModel3"
                    size="xl"
                    :max="5"
                    color="primary"/></div>
                  </q-card-section>
                </q-item>
                <q-separator/>
                <q-card-section>
                  amei a ponte
                </q-card-section>
              </q-card>
            </div>
          </div>
            <div class="text-h3 flex flex-center q-ma-xl "> You may also like</div>
            <div class="row q-col-gutter-sm">
              <div class="col-3"><q-img src="https://cdn.quasar.dev/img/parallax2.jpg "></q-img></div>
              <div class="col-3"><q-img src="https://cdn.quasar.dev/img/parallax2.jpg "></q-img></div>
              <div class="col-3"><q-img src="https://cdn.quasar.dev/img/parallax2.jpg "></q-img></div>
              <div class="col-3 text-grey-13"><q-img src="https://cdn.quasar.dev/img/parallax2.jpg ">
              <div class="row q-col-gutter-sm q-ma-sm" id="borda">
                <div class="col-6"> 
                  <q-icon class="absolute all-pointer-events" size="32px" name="favorite_border" color="white" style="top: 8px; left: 8px">
                    </q-icon>
                    </div>
                    <div class="col-6" id="posição">
                      500
                    </div>
                  </div>
                </q-img>
              </div>
            </div>
            <div class="q-ma-xl">
              <div class="text-h3 flex flex-center"> get inspired community </div>
              <div class="row q-mt-xl q-col-gutter-sm">
              <div class="col-2"><q-img src="https://cdn.quasar.dev/img/parallax2.jpg "></q-img></div>
              <div class="col-2"><q-img src="https://cdn.quasar.dev/img/parallax2.jpg "></q-img></div>
              <div class="col-2"><q-img src="https://cdn.quasar.dev/img/parallax2.jpg "></q-img></div>
              <div class="col-2"><q-img src="https://cdn.quasar.dev/img/parallax2.jpg "></q-img></div>
              <div class="col-2"><q-img src="https://cdn.quasar.dev/img/parallax2.jpg "></q-img></div>
              <div class="col-2"><q-img src="https://cdn.quasar.dev/img/parallax2.jpg "></q-img></div>
              </div>
            </div>
            <div>
              <div class="text-h3 flex flex-center q-ma-xl"> subscribe to our </div>
              <div class="row" id="posição2">
                <div class="col-6">
                  <q-input filled/>
                  </div>
                  <div class="col-6">
                   <q-btn label="Subscribe"/>
                </div>
              </div>
            </div>
        </div>
          <div class="bg-grey-13 q-mt-xl" id="profundidade">
            <div class="row">
              <div class="col-3" id="imagen2">
                <div class=""><q-img src="~assets/fugete.png" style="height: 75px; max-width: 75px"/></div>
              </div>
                <div class="col-3" id="imagen3">
                    follow us 
                  <div class="row">
                    <div class="col-4"><q-img src="~assets/facebook.png" style="height: 35px; max-width: 35px"/></div>
                    <div class="col-4"><q-img src="~assets/instagram.png" style="height: 35px; max-width: 35px"/></div>
                    <div class="col-4"><q-img src="~assets/twitter.png" style="height: 35px; max-width: 35px"/></div>
                  </div>
                </div>
                <div class="col-3" id="imagen3">
                    <div class="text-h5">menu</div>
                    <div>homepage</div>
                    <div>category 1</div>
                    <div>category 2</div>
                    <div>about us</div>
                  </div>
                 <div class="col-3" id="imagen3">
                  <div class="text-h5">contact</div>
                  <div>email</div>
                  <div>call us</div>
                  <div>chat online</div>

                 </div>
                 <div class="col-3" id="imagen3">
                   <div>oioi</div>
                 </div>
                 
            </div>
          </div>
      </div>
     
  </q-page>
</template>

<script>
import { ref } from 'vue'

export default {
  

setup () {  
    
    return {
      tab: ref(''),
      selected: ref([]),
      ratingModel: ref(),
      ratingModel2:2,
      ratingModel3:5,
      model: ref(''),
      options: ['PP', 'P', 'M', 'G', 'GG'],
      contagem:0
    }
  },
  methods: {
    add(){
      this.contagem++
      console.log(this.contagem)
    }
  },
}
</script>

<style>
  #imagen{
   /* transition: transform .2s;*/
  }
  #imagen:hover {
    /*transform: scale(1.27,1.27,1,27);*/ 
  }
  #borda{
    border-radius: 25px;
  }
  #posição{
    position: relative;
    top: -10px;
  }
  #posição2{
    margin-left:37%;
  }
  #profundidade{
    height: 20em;
  }
  #imagen2{
    position: relative;
    top: 50px;
    right:-8%;
  }
  #imagen3{
    position: relative;
    top: 50px;
    right:8%;
  }
  #imagen4{
     position: relative;
    top: -34px;
    right:-110%;
  }
</style>