<!----------Make By YourName---------------->
 <template>
 <div>
     <h2>Test Bluetooth</h2>
     <q-btn color="primary" type="submit" label="สแกน" />
     <br><br>
     <pre>{{devices}}</pre>
     

   
 </div>

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
    devices:[],
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

    async blueToothStatus(){
        ble.isEnabled(
        function() {
           alert('Bluetooth Open!');
        },
        function() {
            ble.showBluetoothSettings();
            ble.readRSSI(device_id, success, failure);
            location.reload();
        }
          );
    },

    getDevice(device){},

    async blueToothScan(){
 
        ble.startScan([], 
        function(device) {
            this.devices = device
            console.log(device)
           //console.log(JSON.stringify(device));
           
        }, );

        setTimeout(ble.stopScan,5000,
        function() { 
            
            console.log("Scan complete");
            
        },

        function() { console.log("stopScan failed");  }
        ); 

    //    ble.startScan([], this.success, this.failure );
 
    },

   /* success(device){ 
        this.devices = device
        console.log(device)
        
    },
    failure(device){
        setTimeout(function() {
            this.devices = device
            ble.stopScan(   
            function() { console.log("Scan complete"); },
            function() { console.log("stopScan failed"); }
            );
        }, 5000);
    },*/


    

    /******* Methods default run ******/
    load:async function(){
     
      await this.blueToothStatus();
      await this.blueToothScan();
      
      
    },
 
},
    }
</script>