<template>
    <h1 class="text-2xl font-semibold text-center pt-[2%] pb-[1%]">Tambah Kategori</h1>
    <p class="text-center text-lg pb-[2%]">Sila masukkan maklumat kategori di dalam ruangan yang disediakan</p>

    <div v-if="loading" class="fixed inset-0 flex items-center bg-black bg-opacity-50 justify-center z-50">
            <div class="loader">
          </div>
        </div>

    <form v-else class="w-[80%] m-auto" @submit.prevent="submitForm">
        <div class="flex justify-around">
            <div class="relative z-0 w-[45%] mb-6 group m-auto">
                <input type="text" name="floating_IDPromosi" v-model="IDPromosi" id="floating_IDPromosi" class="block py-2.5 px-0 w-full text-md text-black bg-transparent border-0 border-b-2 border-black appearance-none dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" "  />
                <label for="floating_IDPromosi" class="peer-focus:font-medium absolute text-md text-black duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">ID Promosi</label>
                <span class="text-red-500 text-sm">{{ errors.IDPromosi }}</span>
                <span class="text-red-500 text-sm">{{ errors.errorIDPromosi }}</span>
              </div>
    
            <div class="relative z-0 w-[45%] mb-6 group m-auto">
                <input type="text" name="floating_NamaPromosi" id="floating_NamaPromosi" v-model="NamaPromosi" class="block py-2.5 px-0 w-full text-md text-black bg-transparent border-0 border-b-2 border-black appearance-none dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" "  />
                <label for="floating_NamaPromosi" class="peer-focus:font-medium absolute text-md text-black duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">Nama Promosi</label>
                <span class="text-red-500 text-sm">{{ errors.NamaPromosi }}</span>
                <span class="text-red-500 text-sm">{{ errors.errorNamaPromosi }}</span>
              </div>
        </div>

        <div class="flex justify-around">
            <div class="relative z-0 w-[65%] mb-6 group m-auto">
                <input type="text" name="floating_DeskripsiPromosi" v-model="DeskripsiPromosi" id="floating_DeskripsiPromosi" class="block py-2.5 px-0 w-full text-md text-black bg-transparent border-0 border-b-2 border-black appearance-none dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" "  />
                <label for="floating_DeskripsiPromosi" class="peer-focus:font-medium absolute text-md text-black duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">Deskripsi Promosi</label>
                <span class="text-red-500 text-sm">{{ errors.DeskripsiPromosi }}</span>
              </div>
    
            <div class="relative z-0 w-[25%] mb-6 group m-auto">
                <input type="text" name="floating_HargaPromosi" id="floating_HargaPromosi" v-model="HargaPromosi" class="block py-2.5 px-0 w-full text-md text-black bg-transparent border-0 border-b-2 border-black appearance-none dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-blue-600 peer" placeholder=" "  />
                <label for="floating_HargaPromosi" class="peer-focus:font-medium absolute text-md text-black duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6">Harga Promosi (RM)</label>
                <span class="text-red-500 text-sm">{{ errors.HargaPromosi }}</span>
            </div>
        </div>

        <div class="flex justify-center">
          <div class="relative z-0 w-[45%] group m-auto flex">
            <label for="items" class="pt-3 pr-3">Pilih Kategori:</label>
            <div>
              <select id="items" v-model="selectedItem" placeholder="Select Item" class="block mt-2 appearance-none w-full bg-gray-200 border border-gray-200 text-gray-700 py-[6PX] px-4 pr-8 rounded leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
                <option disabled>-Select Item-</option>
                <option v-for="kategori in kategoriList" :key="kategori.Nama_Kategori" :value="kategori.id">{{ kategori.Nama_Kategori }}</option>
              </select>
              <span class="text-red-500 text-sm">{{ errors.selectedItem }}</span>
            </div>
          </div>

          <div class="relative z-0 w-[45%] group m-auto flex">
            <label for="status" class="pt-3 pr-3">Pilih Status Promosi:</label>
            <div>
              <select id="status" v-model="selectedStatus" class="block mt-2 appearance-none w-[175%] bg-gray-200 border border-gray-200 text-gray-700 py-[6PX] px-4 pr-8 rounded leading-tight focus:outline-none focus:bg-white focus:border-gray-500">
                <option disabled>-Select Item-</option>
                <option value="Aktif">Aktif</option>
                <option value="Tidak Aktif">Tidak Aktif</option>
              </select>
              <span class="text-red-500 text-sm">{{ errors.selectedStatus }}</span>
            </div>
          </div>
        </div>

        <div class="flex justify-between">
            <RouterLink to="/urus-promosi" class="w-[47%] mt-[2.8%]"><button class="text-white w-full bg-gradient-to-r from-red-400 to-red-300 h-12 px-12 rounded-full  shadow-xl hover:scale-105 duration-200">Batal</button></RouterLink>
            <button type="submit" class="text-white w-[47%] bg-gradient-to-r from-sky-400 to-indigo-300 h-12 px-12 rounded-full  shadow-xl hover:scale-105 duration-200 mt-[2.8%]">Daftar</button>
        </div>
    </form>
    <ToastMessage ref="toast"/>
</template>

<script>
import axios from 'axios';
import ToastMessage from '../../components/ToastMessage.vue';


export default {
  components:{
    ToastMessage,
  },
  data() {
    return {
      kategoriList: [],
      selectedItem: null,
      selectedStatus: null,
      IDPromosi: '',
      loading: false,
      NamaPromosi: '',
      DeskripsiPromosi: '',
      HargaPromosi: '',
      errors: {
        IDPromosi: '',
        NamaPromosi: '',
        DeskripsiPromosi: '',
        HargaPromosi: '',
        selectedItem: null,
        selectedStatus: null,

        existID: '',
        existNama: '',
        errorIDPromosi: '',
        errorNamaPromosi: '',
      },
    };
  },
  mounted() {
    this.fetchKategoriData();
  },
  methods: {
    fetchKategoriData() {
      axios
        .get('https://lje-ms-backend.onrender.com/kategori')
        .then((response) => {
          this.kategoriList = response.data;
        })
        .catch((error) => {
          console.error('Error fetching kategori data:', error);
        });
    },
    async submitForm() {
      this.loading = true; 

      await axios
        .get('https://lje-ms-backend.onrender.com/cekIDPromosi')
        .then((response) => {
          this.errors.existID = response.data;
          console.log(this.errors.existID);
        })
        .catch((error) => console.log(error));

      await axios
        .get('https://lje-ms-backend.onrender.com/cekNamaPromosi')
        .then((response) => {
          this.errors.existNama = response.data;
          console.log(this.errors.existNama);
        })
        .catch((error) => console.log(error));

      const formData = {
        ID_Promosi: this.IDPromosi,
        Nama_Promosi: this.NamaPromosi,
        Deskripsi_Promosi: this.DeskripsiPromosi,
        Harga_Promosi: parseInt(this.HargaPromosi),
        kategoriTerlibat: this.selectedItem,
        Status_Promosi: this.selectedStatus,
      };

      const existingIDPromosi = this.errors.existID.some(
        (promosi) => promosi.ID_Promosi === this.IDPromosi
      );
      const existingNamaPromosi = this.errors.existNama.some(
        (promosi) => promosi.Nama_Promosi === this.NamaPromosi
      );

      if (
        this.IDPromosi &&
        this.NamaPromosi &&
        this.DeskripsiPromosi &&
        this.HargaPromosi &&
        this.selectedItem &&
        this.selectedStatus &&
        !existingIDPromosi &&
        !existingNamaPromosi
      ) {
        this.errors.errorIDPromosi = '';
        this.errors.errorNamaPromosi = '';

        axios
          .post('https://lje-ms-backend.onrender.com/promosi', formData)
          .then((response) => {
            console.log(response.data);
            this.IDPromosi = '';
            this.NamaPromosi = '';
            this.DeskripsiPromosi = '';
            this.HargaPromosi = '';
            this.selectedItem = null;
            this.selectedStatus = null;

            const message ='Pendaftaran Promosi Berjaya'
            const status = 'Berjaya'
            
            this.$refs.toast.toast(message,status,'success')
            
          })
          .catch((error) => {
            console.error(error);
          })
          .finally(() => {
              this.loading = false; 
            });
      } else {
        if (existingIDPromosi && this.IDPromosi !== '') {
          this.errors.errorIDPromosi = '*ID Promosi Sudah Terdaftar';
        } else {
          this.errors.errorIDPromosi = '';
        }

        if (existingNamaPromosi && this.NamaPromosi !== '') {
          this.errors.errorNamaPromosi = '*Promosi Sudah Terdaftar';
        } else {
          this.errors.errorNamaPromosi = '';
        }

        if (this.IDPromosi === '') {
          this.errors.IDPromosi = '*Sila Masukkan ID Promosi';
        } else {
          this.errors.IDPromosi = '';
        }

        if (this.NamaPromosi === '') {
          this.errors.NamaPromosi = '*Sila Masukkan Nama Promosi';
        } else {
          this.errors.NamaPromosi = '';
        }

        if (this.DeskripsiPromosi === '') {
          this.errors.DeskripsiPromosi = '*Sila Masukkan Deskripsi Promosi';
        } else {
          this.errors.DeskripsiPromosi = '';
        }

        if (this.HargaPromosi === '') {
          this.errors.HargaPromosi = '*Sila Masukkan Harga Promosi';
        } else {
          this.errors.HargaPromosi = '';
        }

        if (this.selectedItem === null) {
          this.errors.selectedItem = '*Sila Pilih Kategori Promosi';
        } else {
          this.errors.selectedItem = '';
        }

        if (this.selectedStatus === null) {
          this.errors.selectedStatus = '*Sila Pilih Status Promosi';
        } else {
          this.errors.selectedStatus = '';
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