<template color="#6B799E">
  <div class="home">
   <v-container>
   <v-layout >
     <v-flex xs12 sm6 offset-sm3>
       <v-card height="590" >
        <v-row justify="center">
          
          </v-row> 

          <h4 class="text-center display-2 font-weight-light grey--text my-5" >{{currentTitle}}</h4>
          
          <div class="d-flex justify-end mr-1">
          <v-btn
          :disabled="step === 1"
          text
          v-show="showsignup"
          @click="prev"
          class="font-weight-light"

            >
                SIGN IN?
            </v-btn>
            
            <v-btn
          :disabled="step === 3"
          v-show="showsignin"
          text
          @click="next"
          class="font-weight-light"
        >
        
               SIGN UP?
        </v-btn> 
          </div>
            
            
            
        <v-divider></v-divider>

          


          
          
          <v-window v-model="step" vertical> 
            
              <v-window-item :value="1">
        
                <v-row justify="center" class="my-5" >
            <div class="mr-9">
              <v-btn class="mx-2" fab  large color="black" outlined>
           <v-icon>fab fa-facebook-f</v-icon>
          </v-btn></div>

          <div class="mr-9">
            <v-btn class="mx-2" fab  large color="black" outlined>
              <v-icon>fab fa-facebook-f</v-icon>
              </v-btn>
          </div>
          

         <div class="">
            <v-btn class="mx-2" fab  large color="black" outlined>
           <v-icon>fab fa-facebook-f</v-icon>
          </v-btn>
         </div>
          
          </v-row>
          <div class="mt-10">
            <hr><h5 class=" mt-n5 display-1" style="background:white; width:45px; margin:auto">OR</h5>
          </div>
          
          <v-card-text>
            <v-form>
              <v-text-field label="Username or Email" prepend-icon="fas fa-user-tie"></v-text-field>
              <v-text-field
              :append-icon="show1 ? 'mdi-eye': 'mdi-eye-off'"
              :type="show1 ? 'text' : 'password'"
              @click:append="show1 = !show1"
              prepend-icon="fas fa-lock"
              label="Password"
              >

              </v-text-field>


              <v-row justify="center" class="mt-5"><v-btn depressed rounded><v-icon left>fas fa-sign-in-alt</v-icon>  <span>SIGN in</span> </v-btn></v-row>
           
            </v-form>
          </v-card-text>
        
          
          

      </v-window-item>

      <v-window-item :value="2">
      
        <v-form>
          <v-card-text>
            <v-text-field label="Name" prepend-icon="fas fa-font"></v-text-field>
            <v-text-field label="User Name" prepend-icon="fas fa-user-tie"></v-text-field>
            <v-text-field label="Email" prepend-icon="fas fa-envelope"></v-text-field>
            <v-text-field
              :append-icon="show1 ? 'mdi-eye': 'mdi-eye-off'"
              :type="show1 ? 'text' : 'password'"
              @click:append="show1 = !show1"
              prepend-icon="fas fa-lock"
              label="Password"
              >

              </v-text-field>
            
            <v-text-field label="Phone" prepend-icon="fas fa-mobile"></v-text-field>

            <v-row justify="center" class="mt-5"><v-btn depressed rounded><v-icon left>fas fa-sign-in-alt</v-icon>  <span>SIGN UP</span> </v-btn></v-row>
           
          <div class="text-center font-weight-bold grey--text my-3"><span>By clicking the sign up button, you agree with our Terms and Conditions.</span></div>
          
          </v-card-text>
        </v-form>


      </v-window-item> 
    </v-window>


        
        </v-card>
        

         

    


  
  
    
      
     </v-flex>
   </v-layout>

</v-container>
  </div>
</template>

<script>


export default {
  name: 'Home',
  data(){
    return{
      step:1,
      showsignin:false,
      showsignup:false,
      show1:false
      
    }
  },
  computed: {
      currentTitle () {
        switch (this.step) {
          case 1:{this.showsignin = true;
                  this.showsignup = false;
            return 'Login'}
          case 2: {this.showsignup = true;
                   this.showsignin =false;
            return 'Create Account'}
          
        }
      },
      btnTitle(){
        switch (this.step){
          case 1: return 'SIGN IN'
          case 2: return 'SIGN UP'
        }

      }
    },
  methods: {
      next () {
        this.step =2;
      },
      prev () {
        this.step=1;
      },
    },
}
</script>
