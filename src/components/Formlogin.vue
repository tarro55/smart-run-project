 <!----------Make By YourName---------------->
 <template>
    <q-layout>
        <q-flex>
            <q-input outlined v-model="email" label="อีเมลล์" />
        </q-flex>
        <q-flex>
            <q-input outlined v-model="password" label="รหัสผ่าน" />
        </q-flex>
    </q-layout>
</template>

    <script>
    import { get,sync,call } from "vuex-pathify"; 
export default {
    name: 'Root',
    /*-------------------------Load Component---------------------------------------*/
    components: {

    },
  /*-------------------------Set Component---------------------------------------*/
props:{

},
    /*-------------------------DataVarible---------------------------------------*/
    data() {
    return {

        };
    }, 
    /*-------------------------Run Methods when Start this Page------------------------------------------*/
     async mounted() {
    /**** Call loading methods*/
            this.load(); 
    },
    /*-------------------------Run Methods when Start Routed------------------------------------------*/
     async beforeRouteEnter(to, from, next) { 
        next()
    },
    /*-------------------------Vuex Methods and Couputed Methods------------------------------------------*/
    computed:{

},
    /*-------------------------Methods------------------------------------------*/
methods:{
    /******* Methods default run ******/
    load:async function(){
}
},
    }
</script>