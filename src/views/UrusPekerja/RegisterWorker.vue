<script setup>
    import SidebarManager from '../../components/SidebarManager.vue';
</script>

<template>
    <div class="bg-[#f0f0f0] min-h-screen w-full flex pb-[3%]">
        <SidebarManager/>

        <div v-if="loading" class="fixed inset-0 flex items-center bg-black bg-opacity-50 justify-center z-50">
            <div class="loader">
          </div>
        </div>
        <div v-else class="ml-[22%] mt-[2.7%] w-[75%]">
            <div>
                <h1 class="text-xl font-semibold ]">Daftar Pekerja</h1>
                                <!-- <h1 class="text-2xl font-semibold">Ubahsuai Maklumat Pekerja</h1>  -->
                <h2 class="text-md text-gray-500"><span><RouterLink to="/main">Halaman Utama</RouterLink></span> - <span><RouterLink to="/urus-pekerja">Pengurusan Pekerja</RouterLink></span> - <span class="text-sky-400">Pendaftaran Pekerja</span></h2>
            </div>
            
            <div class="flex justify-between mt-[2%]">
                <div  class="bg-white w-[95%] h-[78%] shadow-2xl rounded-xl pt-[3%] pb-[5%]">
                    <h3 class="text-center text-lg mb-[3%]">Sila masukkan maklumat pekerja di ruang yang disediakan.</h3>

                    <form class="w-[80%] m-auto" @submit.prevent="submitForm">
                        <div class="relative z-0 w-full mb-6 group">
                            <input type="text" name="floating_nama" v-model="namapenuh" id="floating_nama" class="block py-2.5 px-0 w-full text-md text-black bg-transparent border-0 border-b-2 border-black appearance-none dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" "  />
                            <label for="floating_nama" class="peer-focus:font-medium absolute text-md text-black duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">Nama Penuh</label>
                            <label class="text-red-600 font-medium text-xs" for="errorNama" id="errorNama">{{ errors.namapenuh }}</label>

                          </div>
                        <div class="relative z-0 w-full mb-6 group">
                            <input type="text" name="floating_kp" id="floating_kp" v-model="nokp" class="block py-2.5 px-0 w-full text-md text-black bg-transparent border-0 border-b-2 border-black appearance-none dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" "  />
                            <label for="floating_kp" class="peer-focus:font-medium absolute text-md text-black duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">Nombor Kad Pengenalan</label>
                            <label class="text-red-600 font-medium text-xs" for="errorkad" id="errorkad">{{ errors.nokp }}</label>
                            <label class="text-red-600 font-medium text-xs" for="errorkad3" id="errorkad3">{{ errors.errorKP }}</label>
                          </div>
                        <div class="flex justify-between">
                            <div class="relative z-0 w-[45%] mb-6 group">
                            <input type="text" name="floating_phone" id="floating_phone"  v-model="telefon" class="block py-2.5 px-0 w-full text-md text-black bg-transparent border-0 border-b-2 border-black appearance-none dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" "  />
                            <label for="floating_phone" class="peer-focus:font-medium absolute text-md text-black duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">Nombor Telefon</label>
                            <label class="text-red-600 font-medium text-xs" for="errorphone" id="errorphone">{{ errors.telefon }}</label>
                            <label class="text-red-600 font-medium text-xs" for="errorphone3" id="errorphone3">{{ errors.errorTel }}</label>

                          </div>
                        <div class="relative z-0 w-[45%] mb-6 group">
                            <input type="text" name="floating_email" id="floating_email"  v-model="emel" class="block py-2.5 px-0 w-full text-md text-black bg-transparent border-0 border-b-2 border-black appearance-none dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" "  />
                            <label for="floating_email" class="peer-focus:font-medium absolute text-md text-black duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">E-Mel</label>
                            <label class="text-red-600 font-medium text-xs" for="erroremail" id="erroremail">{{ errors.emel }}</label>
                            <label class="text-red-600 font-medium text-xs" for="erroremel" id="erroremel">{{ errors.errorEmel }}</label>
                          </div>
                        </div>
                        <div class="relative z-0 w-full mb-6 group">
                            <input type="text" name="floating_address" id="floating_address"  v-model="alamat" class="block py-2.5 px-0 w-full text-md text-black bg-transparent border-0 border-b-2 border-black appearance-none dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" "  />
                            <label for="floating_address" class="peer-focus:font-medium absolute text-md text-black duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">Alamat</label>
                            <label class="text-red-600 font-medium text-xs" for="errorAddress" id="errorAddress">{{ errors.alamat }}</label>
                          </div>
                        <div class="flex justify-between">
                            <div class="relative z-0 w-[45%] mb-6 group">
                            <input type="text" name="floating_id" id="floating_id"  v-model="idpekerja" class="block py-2.5 px-0 w-full text-md text-black bg-transparent border-0 border-b-2 border-black appearance-none dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" "  />
                            <label for="floating_id" class="peer-focus:font-medium absolute text-md text-black duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">ID Pekerja</label>
                            <label class="text-red-600 font-medium text-xs" for="errorID" id="errorID">{{ errors.idpekerja }}</label>
                            <label class="text-red-600 font-medium text-xs" for="errorid" id="errorid">{{ errors.errorID }}</label>
                          </div>
                        <div class="relative z-0 w-[45%] mb-6 group">
                          <input type="number" name="floating_gaji" id="floating_gaji"  v-model="gaji" class="block py-2.5 px-0 w-full text-md text-black bg-transparent border-0 border-b-2 border-black appearance-none dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" "  />
                            <label for="floating_gaji" class="peer-focus:font-medium absolute text-md text-black duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">Gaji Pekerja</label>
                            <label class="text-red-600 font-medium text-xs" for="errorgaji" id="errorgaji">{{ errors.gaji }}</label>
                            
                          </div>
                        </div>
                        <div class="flex justify-between">
                          <div class="relative z-0 w-[45%] mb-6 group">
                            <input
                              type="password"
                              name="floating_password"
                              v-model="password"
                              id="floating_password"
                              class="block py-2.5 px-0 w-full text-md text-black bg-transparent border-0 border-b-2 border-black appearance-none dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer"
                              placeholder=" "
                            />
                            <label
                              for="floating_password"
                              class="peer-focus:font-medium absolute text-md text-black duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6"
                            >
                              Kata Laluan
                            </label>
                            <label class="text-red-600 font-medium text-xs" for="errorps" id="errorps">{{ errors.password }}</label>
                            <i :class="['fa-solid', 'fa-eye', 'text-lg', {'text-blue-500': showPassword, 'text-gray-500': !showPassword}, 'cursor-pointer', 'absolute', 'top-3', 'right-2', 'scale-105']" @click="togglePasswordVisibility()"></i>
                          </div>
                        <div class="relative z-0 w-[45%] mt-3 group">
                          <div class="flex flex-col">
                            <div>
                              <label for="peranan" class="mr-[5%]">Peranan:</label>
                                <select id="peranan" v-model="peranan" class=" appearance-none bg-gray-200 border border-gray-200 text-gray-700 py-[6PX] px-4 pr-8 rounded leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
                                  <option disabled>-- Sila Pilih Peranan --</option>
                                  <option value="Pekerja">Pekerja</option>
                                  <option value="Pengurus">Pengurus</option>
                                </select>
                            </div>
                            <div>
                              <label class="text-red-600 font-medium text-xs" for="errorrole" id="errorrole">{{ errors.peranan }}</label>
                            </div>
                          </div>
                          </div>
                        </div>

                        <label for="items" class="pt-3 pr-3">Muatnaik Gambar Pekerja:</label>
                            <lr-file-uploader-regular
                              css-src="https://esm.sh/@uploadcare/blocks@0.22.9/web/file-uploader-regular.min.css"
                              ctx-name="my-uploader"
                              class="my-config "
                            >
                            </lr-file-uploader-regular>

                        <div class="flex justify-between">
                            <RouterLink to="/urus-pekerja" class="w-[47%] mt-[2.8%]"><button class="text-white w-full text-md bg-gradient-to-r from-red-400 to-red-300 h-12 px-12 rounded-full shadow-xl hover:scale-105 duration-200">Batal</button></RouterLink>
                            <button type="submit" class="text-white w-[47%] bg-gradient-to-r from-sky-400 to-indigo-300 h-12 px-12 rounded-full shadow-xl mt-[2.80%] hover:scale-105 duration-200">Daftar</button>
                        </div>
                    </form>
                </div>
            </div>
        </div>
        <ToastMessage ref="toast"/>  
    </div>
</template>

<style>
.my-config {
  --cfg-pubkey: "3b7e00a614646d15bf1a";
  --cfg-img-only: 1;
  --cfg-multiple: 1;
  --cfg-max-local-file-size-bytes: 10485760;
  --cfg-use-cloud-image-editor: 1;
  --cfg-source-list: "local, camera, gdrive";
  --darkmode: 0;
  --h-accent: 223;
  --s-accent: 100%;
  --l-accent: 61%;
}
</style>

<script>
import axios from 'axios';
import ToastMessage from '../../components/ToastMessage.vue';
import * as LR from "@uploadcare/blocks";

LR.registerBlocks(LR);
 

export default {
  components:{
    ToastMessage,
  },
  data() {
    return {
      showPassword: false,
      namapenuh: '',
      loading: false,
      nokp: '',
      telefon: '',
      emel: '',
      alamat: '',
      idpekerja: '',
      peranan: '',
      password: '',
      gaji: '',
      link: '',
      errors: {
        namapenuh: '',
        nokp: '',
        errorKP: '',
        telefon: '',
        errorTel: '',
        emel: '',
        errorEmel: '',
        alamat: '',
        idpekerja: '',
        errorID: '',
        peranan: '',
        password: '',
        gaji: '',
        existKP: false,
        existTel: false,
        existEmel: false,
        existID: false,
      },
    };
  },
  mounted() {
    window.addEventListener("LR_UPLOAD_FINISH", async (e) => {
    const dataUpload = e.detail.data[0];
    this.link=dataUpload.cdnUrl + dataUpload.name;
    console.log(this.link);
    
});

window.togglePasswordVisibility = this.togglePasswordVisibility;

  },
  methods: {
    togglePasswordVisibility() {
      this.showPassword = !this.showPassword;
      var passwordInput = document.getElementById("floating_password");
      if (passwordInput.type === "password") {
        passwordInput.type = "text";
      } else {
        passwordInput.type = "password";
      }
    },
    async checkExistingData() {
      try {
        const responseKP = await axios.get(`https://lje-ms-backend.onrender.com/noKP?nokp=${this.nokp}`);
        this.errors.existKP = responseKP.data.length > 0;

        const responseEmel = await axios.get(`https://lje-ms-backend.onrender.com/emel?emel=${this.emel}`);
        this.errors.existEmel = responseEmel.data.length > 0;

        const responseTel = await axios.get(`https://lje-ms-backend.onrender.com/telefon?telefon=${this.telefon}`);
        this.errors.existTel = responseTel.data.length > 0;

        const responseID = await axios.get(`https://lje-ms-backend.onrender.com/stafID?idpekerja=${this.idpekerja}`);
        this.errors.existID = responseID.data.length > 0;

        console.log(this.errors.existKP);
        console.log(this.errors.existEmel);
        console.log(this.errors.existID);
        console.log(this.errors.existTel);
      } catch (error) {
        console.log(error);
      }
    },
    async submitForm() {
      this.loading = true; 
      
      await this.checkExistingData();

      const existingKP = this.errors.existKP;
      const existingTel = this.errors.existTel;
      const existingEmel = this.errors.existEmel;
      const existingID = this.errors.existID;

      if (
        this.namapenuh &&
        this.nokp &&
        this.telefon &&
        this.emel &&
        this.alamat &&
        this.idpekerja &&
        this.peranan &&
        this.password &&
        this.gaji &&
        !existingKP &&
        !existingTel &&
        !existingEmel &&
        !existingID
      ) {
        this.errors.errorKP = '';
        this.errors.errorEmel = '';
        this.errors.errorID = '';
        this.errors.errorTel = '';

        if (!/(?=.*[A-Z])(?=.*[0-9]).{8,}/.test(this.password)) {
          this.errors.password = '*Kata Laluan Tidak Sah';
        } else {
          this.errors.password = '';
        }

        if (!/^[\w.-]+@[a-zA-Z_-]+\.[a-zA-Z]{2,4}$/.test(this.emel)) {
          this.errors.emel = '*Emel Tidak Sah';
        } else {
          this.errors.emel = '';
        }

        if (!this.errors.password && !this.errors.emel) {
          
          const formData = {
            Nama_Pekerja: this.namapenuh,
            NoKP_Pekerja: this.nokp,
            Telefon_Pekerja: this.telefon,
            Emel_Pekerja: this.emel,
            Alamat_Pekerja: this.alamat,
            Staf_ID: this.idpekerja,
            Peranan_Pekerja: this.peranan,
            KataLaluan_Pekerja: this.password,
            Gaji_Pekerja: this.gaji,
            GambarPekerja: this.link,
          };

          axios
            .post('https://lje-ms-backend.onrender.com/', formData)
            .then((response) => {
              console.log(response.data);
              this.namapenuh = '';
              this.nokp = '';
              this.telefon = '';
              this.emel = '';
              this.alamat = '';
              this.idpekerja = '';
              this.peranan = '';
              this.password = '';
              this.gaji = '';
              this.link = '';

              const message ='Pendaftaran Pekerja Berjaya'
              const status = 'Berjaya'
              
              this.$refs.toast.toast(message,status,'success')
            })
            .catch((error) => {
              console.error(error);
            }).finally(() => {
              this.loading = false; 
            });

            
        }
      } else {
        if (existingKP && this.nokp !== '') {
          this.errors.errorKP = '*Nombor Kad Pengenalan Sudah Terdaftar';
        } else {
          this.errors.errorKP = '';
        }

        if (existingEmel && this.emel !== '') {
          this.errors.errorEmel = '*Emel Sudah Terdaftar';
        } else {
          this.errors.errorEmel = '';
        }

        if (existingID && this.idpekerja !== '') {
          this.errors.errorID = '*ID Pekerja Sudah Terdaftar';
        } else {
          this.errors.errorID = '';
        }

        if (existingTel && this.telefon !== '') {
          this.errors.errorTel = '*Nombor Telefon Sudah Terdaftar';
        } else {
          this.errors.errorTel = '';
        }

        if (this.namapenuh === '') {
          this.errors.namapenuh = '*Sila Masukkan Nama Penuh Pekerja';
        } else {
          this.errors.namapenuh = '';
        }

        if (this.nokp === '') {
          this.errors.nokp = '*Sila Masukkan Nombor Kad Pengenalan Pekerja';
        } else {
          this.errors.nokp = '';
        }

        if (this.telefon === '') {
          this.errors.telefon = '*Sila Masukkan Nombor Telefon Pekerja';
        } else {
          this.errors.telefon = '';
        }

        if (this.emel === '') {
          this.errors.emel = '*Sila Masukkan Emel Pekerja';
        } else {
          this.errors.emel = '';
        }

        if (this.alamat === '') {
          this.errors.alamat = '*Sila Masukkan Alamat Pekerja';
        } else {
          this.errors.alamat = '';
        }

        if (this.idpekerja === '') {
          this.errors.idpekerja = '*Sila Masukkan ID Pekerja';
        } else {
          this.errors.idpekerja = '';
        }

        if (this.peranan === '') {
          this.errors.peranan = '*Sila Masukkan Peranan Pekerja';
        } else {
          this.errors.peranan = '';
        }

        if (this.password === '') {
          this.errors.password = '*Sila Masukkan Kata Laluan Akaun Pekerja';
        } else {
          this.errors.password = '';
        }

        if (this.gaji === '') {
          this.errors.gaji = '*Sila Masukkan Gaji Pekerja';
        } else {
          this.errors.gaji = '';
        }
      }
      this.loading = false; 
    },
  },
};
</script>

<style>
.loader {
    position: relative;
    width: 120px;
    height: 140px;
    background-image: radial-gradient(circle 30px, #fff 100%, transparent 0),
    radial-gradient(circle 5px, #fff 100%, transparent 0),
    radial-gradient(circle 5px, #fff 100%, transparent 0),
    linear-gradient(#FFF 20px, transparent 0);
    background-position: center 127px , 94px 102px , 16px 18px, center 114px;
    background-size: 60px 60px, 10px 10px , 10px 10px , 4px 14px;
    background-repeat: no-repeat;
    z-index: 10;
    perspective: 500px;
  }
  .loader::before {
    content: '';
    position: absolute;
    width: 100px;
    height: 100px;
    border-radius:50%;
    border: 3px solid #fff;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -55%) rotate(-45deg);
    border-right-color: transparent;
    box-sizing: border-box;
}
  .loader::after {
    content: '';
    position: absolute;
    height: 80px;
    width: 80px;
    transform: translate(-50%, -55%) rotate(-45deg) rotateY(0deg) ;
    left: 50%;
    top: 50%;
    box-sizing: border-box;
    border: 7px solid #0ea5e9;
    border-radius:50%;
    animation: rotate 0.5s linear infinite;
  }

@keyframes rotate {
  to{transform: translate(-50%, -55%) rotate(-45deg) rotateY(360deg)   }
}
</style>