<!----------Make By YourName---------------->
 <template>
 <div>
     <h2>Test Bluetooth</h2>
<<<<<<< HEAD
     <q-btn color="primary" type="submit" @click="blueToothScan" label="สแกน" />
     <br><br><hr>

    <pre>{{devices}}</pre>
    <q-btn color="primary" type="submit" label="เชื่อมต่อ" />
    <hr>
=======
     <q-btn color="primary" type="submit" label="สแกน" />
     <br><br>
     <pre>{{devices}}</pre>
>>>>>>> 3ce0fa03875efa5abe0e001b01cdd78319e38671
     

   
 </div>

</template>

    <script>
    import { get,sync,call } from "vuex-pathify"; 
<<<<<<< HEAD
import { setTimeout } from 'timers';
=======
>>>>>>> 3ce0fa03875efa5abe0e001b01cdd78319e38671
 

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
<<<<<<< HEAD
            //ble.readRSSI(device_id, success, failure);
=======
            ble.readRSSI(device_id, success, failure);
>>>>>>> 3ce0fa03875efa5abe0e001b01cdd78319e38671
            location.reload();
        }
          );
    },

    getDevice(device){},

    async blueToothScan(){
 
<<<<<<< HEAD
       ble.startScan([], 
        (device)=> {
            this.devices = device.name
            console.log(device.name)
            
            
            //ble.connect();
        },function(err){
            console.log(err);
        }
        );
        setTimeout(ble.stopScan,7000,
        function() { 
            ble.stopScan();
            console.log("Scan complete");  
        },

        function() { console.log("stopScan failed");  }
        );
        //ble.stopScan(this.success, this.failure);
        
  
    },
    async blueToothRead(){
        var rssiSample;
        ble.connect(device_id,
            function(device) {
                rssiSample = setInterval(function() {
                        ble.readRSSI(device_id, function(rssi) {
                                console.log('read RSSI',rssi,'with device', device_id);
                            }, function(err) {
                                console.error('unable to read RSSI',err);
                                clearInterval(rssiSample);
                                })
                    }, 5000);
            },
            function(err) { console.error('error connecting to device')}
            );
    },


=======
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
>>>>>>> 3ce0fa03875efa5abe0e001b01cdd78319e38671


    

    /******* Methods default run ******/
    load:async function(){
     
      await this.blueToothStatus();
<<<<<<< HEAD
     
      
    },
=======
      await this.blueToothScan();
      
      
    },
 
>>>>>>> 3ce0fa03875efa5abe0e001b01cdd78319e38671
},
    }
</script>