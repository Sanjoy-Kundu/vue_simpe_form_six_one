<script setup>
  import {ref, reactive} from "vue";
  const Users = reactive([
  {email: 's@gmail.com', password: '123'},
  {email: 'rohan@gamail.com', password:'123'}
  ]);

  const isLogin = ref(true);

  const loginEmail = ref('');
  const loginPassword = ref('');

  const regiEmail = ref('');
  const regiPas =ref('');
  const regiConPas = ref('');


  function loginSubmit(){
    if(Users[0].email == loginEmail.value && Users[0].password == loginPassword.value){
      alert('Your Login Successfully');
    }else{
      alert('Your Email and Password is wrong');
    }
  }


  function registrationSubmit(){
   if(Users[0].email == regiEmail.value && regiPas.value == regiConPas.value && Users[0].password == regiPas.value){
    alert('Your Registration Successfully');
   }else{
    alert('Your Password and Confirm Password not match');
   }
  }


</script>

<template>
  <!-----Login Form---->

  <section class="gradient-form h-full bg-neutral-200 dark:bg-neutral-700">
  <div class="container h-full p-10" v-if="isLogin">
    <div class="g-6 flex h-full flex-wrap items-center justify-center text-neutral-800 dark:text-neutral-200">
      <div class="w-full">
        <div
          class="block rounded-lg bg-white shadow-lg dark:bg-neutral-800">
          <div class="g-0 lg:flex lg:flex-wrap">
            <!-- Left column container-->
            <div class="px-4 md:px-0 lg:w-6/12">
              <div class="md:mx-6 md:p-12">
                <!--Logo-->
                <div class="text-center">
                  <img class="mx-auto w-48"  src="https://tecdn.b-cdn.net/img/Photos/new-templates/bootstrap-login-form/lotus.webp"  alt="logo" />
                  <h4 class="mb-12 mt-1 pb-1 text-xl font-semibold">
                   Wellcome to my Website
                  </h4>
                  <!-- {{ isLogin }} <br>
                 email=  {{ loginEmail }} <br>
                password =   {{ loginPassword }} <br> -->
                </div>

                <form @submit.prevent="loginSubmit">
                  <p class="mb-4">Please login to your account</p>
                  <!--Username input-->
                  <div class="mb-6">
                     <input type="email" id="" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" v-model="loginEmail"  placeholder="Enter Your Email" >
                  </div> 
                  <div class="mb-6">
                    <input type="password" id="" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" v-model="loginPassword"  placeholder="Enter Your password">
                  </div> 
                  <!--Submit button-->
                  <div class="mb-12 pb-1 pt-1 text-center">
                    <button type="submit" class="mb-3 inline-block w-full rounded px-6 pb-2 pt-2.5 text-xs font-medium uppercase leading-normal text-white shadow-[0_4px_9px_-4px_rgba(0,0,0,0.2)] transition duration-150 ease-in-out hover:shadow-[0_8px_9px_-4px_rgba(0,0,0,0.1),0_4px_18px_0_rgba(0,0,0,0.2)] focus:shadow-[0_8px_9px_-4px_rgba(0,0,0,0.1),0_4px_18px_0_rgba(0,0,0,0.2)] focus:outline-none focus:ring-0 active:shadow-[0_8px_9px_-4px_rgba(0,0,0,0.1),0_4px_18px_0_rgba(0,0,0,0.2)]" @click="loginSubmit()"  data-te-ripple-init data-te-ripple-color="light" style="background: linear-gradient(to right, #ee7724, #d8363a, #dd3675, #b44593); ">
                      Log in
                    </button>

                    <div class="flex items-center justify-between pb-6">
                    <p class="mb-0 mr-2">Don't have an account?</p>
                    <button type="button" @click='isLogin = false' class="inline-block rounded border-2 border-danger bg-red-500 px-6 pb-[6px] pt-2 text-xs font-medium uppercase leading-normal text-danger transition duration-150 ease-in-out hover:border-danger-600 hover:bg-neutral-500 hover:bg-opacity-10 hover:text-danger-600 focus:border-danger-600 focus:text-danger-600 focus:outline-none focus:ring-0 active:border-danger-700 active:text-danger-700 dark:hover:bg-neutral-100 dark:hover:bg-opacity-10" data-te-ripple-init data-te-ripple-color="light"> Register </button>
                  </div>
                  </div>

            
                </form>
              </div>
            </div>

            <!-- Right column container with background and description-->
            <div
              class="flex items-center rounded-b-lg lg:w-6/12 lg:rounded-r-lg lg:rounded-bl-none"
              style="background: linear-gradient(to right, #ee7724, #d8363a, #dd3675, #b44593)">
              <div class="px-4 py-6 text-white md:mx-6 md:p-12">
                <h4 class="mb-6 text-xl font-semibold">
                  We are more than just a company
                </h4>
                <p class="text-sm">
                  Lorem ipsum dolor sit amet, consectetur adipisicing
                  elit, sed do eiusmod tempor incididunt ut labore et
                  dolore magna aliqua. Ut enim ad minim veniam, quis
                  nostrud exercitation ullamco laboris nisi ut aliquip ex
                  ea commodo consequat.
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>




  <div class="container h-full p-10" v-else="isLogin">
    <div
      class="g-6 flex h-full flex-wrap items-center justify-center text-neutral-800 dark:text-neutral-200">
      <div class="w-full">
        <div class="block rounded-lg bg-white shadow-lg dark:bg-neutral-800">
          <div class="g-0 lg:flex lg:flex-wrap">
            <!-- Left column container-->
            <div class="px-4 md:px-0 lg:w-6/12">
              <div class="md:mx-6 md:p-12">
                <!--Logo-->
                <div class="text-center">
                  <img class="mx-auto w-48"  src="https://tecdn.b-cdn.net/img/Photos/new-templates/bootstrap-login-form/lotus.webp"  alt="logo" />
                  <h4 class="mb-12 mt-1 pb-1 text-xl font-semibold">
                   Wellcome to my Website
                  </h4>
                  <h2></h2>
                </div>

                <form>
                  <p class="mb-4">Create a New Account</p>
                  <!--Username input-->

                  <div class="mb-6">
                     <input type="email" id="" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" v-model="regiEmail" placeholder="Enter Your Email" required>
                  </div> 
                  <div class="mb-6">
                     <input type="password" id="" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" v-model="regiPas" placeholder="Enter Your Password" required>
                  </div> 
                  <div class="mb-6">
                     <input type="password" id="" v-model="regiConPas" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="Enter Your Confirm  Password" required>
                  </div> 
                  <!--Submit button-->
                  <div class="mb-12 pb-1 pt-1 text-center">
                    <button class="mb-3 inline-block w-full rounded px-6 pb-2 pt-2.5 text-xs font-medium uppercase leading-normal text-white shadow-[0_4px_9px_-4px_rgba(0,0,0,0.2)] transition duration-150 ease-in-out hover:shadow-[0_8px_9px_-4px_rgba(0,0,0,0.1),0_4px_18px_0_rgba(0,0,0,0.2)] focus:shadow-[0_8px_9px_-4px_rgba(0,0,0,0.1),0_4px_18px_0_rgba(0,0,0,0.2)] focus:outline-none focus:ring-0 active:shadow-[0_8px_9px_-4px_rgba(0,0,0,0.1),0_4px_18px_0_rgba(0,0,0,0.2)]" type="button" @click="registrationSubmit()" data-te-ripple-init data-te-ripple-color="light" style="background: linear-gradient(to right, #ee7724, #d8363a, #dd3675, #b44593); ">
                      Registration
                    </button>

                    <div class="flex items-center justify-between pb-6">
                    <p class="mb-0 mr-2">Already Have an account? Please</p>
                    <button type="button" @click="isLogin= true" class="inline-block rounded border-2 border-danger bg-red-500 px-6 pb-[6px] pt-2 text-xs font-medium uppercase leading-normal text-danger transition duration-150 ease-in-out hover:border-danger-600 hover:bg-neutral-500 hover:bg-opacity-10 hover:text-danger-600 focus:border-danger-600 focus:text-danger-600 focus:outline-none focus:ring-0 active:border-danger-700 active:text-danger-700 dark:hover:bg-neutral-100 dark:hover:bg-opacity-10" data-te-ripple-init data-te-ripple-color="light"> Login</button>
                  </div>
                  </div>

            
                </form>
              </div>
            </div>

            <!-- Right column container with background and description-->
            <div
              class="flex items-center rounded-b-lg lg:w-6/12 lg:rounded-r-lg lg:rounded-bl-none"
              style="background: linear-gradient(to right, #ee7724, #d8363a, #dd3675, #b44593)">
              <div class="px-4 py-6 text-white md:mx-6 md:p-12">
                <h4 class="mb-6 text-xl font-semibold">
                  We are more than just a company
                </h4>
                <p class="text-sm">
                  Lorem ipsum dolor sit amet, consectetur adipisicing
                  elit, sed do eiusmod tempor incididunt ut labore et
                  dolore magna aliqua. Ut enim ad minim veniam, quis
                  nostrud exercitation ullamco laboris nisi ut aliquip ex
                  ea commodo consequat.
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>


</section>
<!----Login form end-->
<br> <br>

</template>

<style scoped>

</style>
