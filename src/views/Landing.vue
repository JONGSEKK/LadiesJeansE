<script setup>
import { RouterLink } from 'vue-router';
const scrollToLogMasuk = () => {
  const logMasukSection = document.getElementById('logmasuk');
  logMasukSection.scrollIntoView({ behavior: 'smooth' });
};

const scrollToFeatures = () => {
  const logMasukSection = document.getElementById('features');
  logMasukSection.scrollIntoView({ behavior: 'smooth' });
};
</script>
  
<template>
    <div class="w-screen h-full backkk ">
        <div class="flex justify-between px-20 max-lg:px-8">
            <img src="/lJE__3_-removebg-preview.png" class="w-36 float-left max-md:w-28" alt="">
            <button class="text-white bg-gradient-to-r from-sky-500 to-indigo-500 h-12 px-12 rounded-full my-auto shadow-[0_20px_50px_rgba(8,_112,_184,_0.7)] max-md:h-10 max-md:px-10" @click="scrollToLogMasuk">Log Masuk</button>
        </div>
        <div class="flex w-10/12 mx-auto h-[80vh]">
            <div class="w-4/5 m-auto max-lg:w-auto max-lg:mt-[20%] max-md:text-center max-md:w-full">
                <h1 class="text-white text-6xl max-md:text-4xl font-bold w-3/5 max-md:w-full mb-10 max-lg:w-4/5 ">Cara yang lebih baik untuk mengurus <span class="text-sky-500 text-8xl max-md:text-5xl font-bold ">Bisnes</span> anda.</h1>
                <h2 class="text-white text-2xl max-md:text-xl w-3/5 max-md:w-full max-md:mb-8 mb-12 ax-lg:w-4/5">Urus. Jejak. Susun. <span class="text-sky-500 text-3xl max-md:text-2xl">Sistem Pengurusan Ladies Jeans Enterprise</span> ialah penyelesaian semua-dalam-satu baharu anda. </h2>
                <button class="text-white bg-gradient-to-r from-sky-500 to-indigo-500 h-12 px-12 max-md:h-10 max-md:px-10 max-md:mt-10 rounded-full my-auto shadow-[0_20px_50px_rgba(8,_112,_184,_0.7)]"  @click="scrollToFeatures">Lihat Modul Fungsi</button>
            </div>
            <div class="w-1/5 m-auto max-lg:hidden">
                <img data-aos="fade-left" src="/undraw_predictive_analytics_re_wxt8.svg" alt="">
            </div>
        </div>
        <div id="features" class="text-white w-4/5 m-auto h-screen max-md:h-[80vh]">
            <h2 class="text-center text-6xl font-bold pt-40 max-md:pt-16 max-md:text-5xl">Ciri-Ciri</h2>
            <div class="flex justify-between pt-24 w-full h-3/5 max-lg:hidden ">
                <div data-aos="zoom-in" class="bg-white rounded-3xl bg-clip-padding backdrop-filter backdrop-blur-md bg-opacity-10 border border-gray-100 mr-10 h-4/5 w-1/6">
                    <img class="w-4/5 m-auto mt-[30%]" src="/undraw_empty_cart_co35.svg"/>
                    <p class="text-xl font-semibold text-center mt-[20%] max-md:text-sm ">Rekod Jualan</p>
                </div>
                <div data-aos="zoom-in" class="h-4/5 w-1/6 bg-white rounded-3xl bg-clip-padding backdrop-filter backdrop-blur-md bg-opacity-10 border border-gray-100 mr-10">
                    <img class="w-4/5 m-auto mt-[20%]" src="/undraw_file_manager_re_ms29.svg"/>
                    <p class="text-xl font-semibold text-center mt-[23.5%]">Pengurusan Inventori</p>
                </div>
                <div data-aos="zoom-in" class="h-4/5 w-1/6 bg-white rounded-3xl bg-clip-padding backdrop-filter backdrop-blur-md bg-opacity-10 border border-gray-100 mr-10">
                    <img class="w-4/5 m-auto mt-[20%]" src="/undraw_team_page_re_cffb.svg"/>
                    <p class="text-xl font-semibold text-center mt-[19%]">Pengurusan Pekerja</p>
                </div>
                <div data-aos="zoom-in" class="h-4/5 w-1/6 bg-white rounded-3xl bg-clip-padding backdrop-filter backdrop-blur-md bg-opacity-10 border border-gray-100 mr-10">
                    <img class="w-4/5 m-auto mt-[40%]" src="/undraw_discount_d-4-bd.svg"/>
                    <p class="text-xl font-semibold text-center mt-[31%]">Pengurusan Promosi</p>
                </div>
                <div data-aos="zoom-in" class="h-4/5 w-1/6 bg-white rounded-3xl bg-clip-padding backdrop-filter backdrop-blur-md bg-opacity-10 border border-gray-100 mr-10">
                    <img class="w-4/5 m-auto mt-[37%]" src="/undraw_data_report_re_p4so.svg"/>
                    <p class="text-xl font-semibold text-center mt-[20%]">Laporan Jualan</p>
                </div>
            </div>
            <div class="flex flex-col justify-between pt-24 w-full h-3/5  xl:hidden max-lg:md:show">
                <div class="flex justify-between mx-auto mb-[5%]">
                    <div data-aos="zoom-in" class="bg-white rounded-3xl bg-clip-padding backdrop-filter backdrop-blur-md bg-opacity-10 border border-gray-100 w-[30%] max-md:pb-4">
                        <img class="w-4/5 m-auto mt-[30%]" src="/undraw_empty_cart_co35.svg"/>
                        <p class="text-xl max-md:text-sm max-md:font-normal max-md:px-4 font-semibold text-center mt-[20%]">Rekod Jualan</p>
                    </div>
                    <div data-aos="zoom-in" class="w-[30%] bg-white rounded-3xl bg-clip-padding backdrop-filter backdrop-blur-md bg-opacity-10 border border-gray-100 max-md:pb-4">
                        <img class="w-4/5 m-auto mt-[20%]" src="/undraw_file_manager_re_ms29.svg"/>
                        <p class="text-xl max-md:text-xs max-md:font-normal max-md:px-4  font-semibold text-center mt-[23.5%]">Pengurusan Inventori</p>
                    </div>
                    <div data-aos="zoom-in" class="w-[30%] bg-white rounded-3xl bg-clip-padding backdrop-filter backdrop-blur-md bg-opacity-10 border border-gray-100 max-md:pb-4">
                        <img class="w-4/5 m-auto mt-[20%]" src="/undraw_team_page_re_cffb.svg"/>
                        <p class="text-xl max-md:text-xs max-md:font-normal max-md:px-4  font-semibold text-center mt-[19%]">Pengurusan Pekerja</p>
                    </div>
                </div >
                <div class="flex justify-center mx-auto mb-[5%]">
                    <div data-aos="zoom-in" class="w-[30%] bg-white rounded-3xl bg-clip-padding backdrop-filter backdrop-blur-md bg-opacity-10 border border-gray-100 mr-[2.5%] max-md:pb-4">
                        <img class="w-4/5 m-auto mt-[40%]" src="/undraw_discount_d-4-bd.svg"/>
                        <p class="text-xl max-md:text-xs max-md:font-normal max-md:px-4  font-semibold text-center mt-[31%]">Pengurusan Promosi</p>
                    </div>
                    <div data-aos="zoom-in" class="w-[30%] bg-white rounded-3xl bg-clip-padding backdrop-filter backdrop-blur-md bg-opacity-10 border border-gray-100 ml-[2.5%] max-md:pb-4">
                        <img class="w-4/5 m-auto mt-[37%]" src="/undraw_data_report_re_p4so.svg"/>
                        <p class="text-xl max-md:text-sm max-md:font-normal max-md:px-4  font-semibold text-center mt-[20%]">Laporan Jualan</p>
                    </div>
                </div>
            </div>
        </div>
        <div id="logmasuk" class="h-screen frontt text-white w-4/5 m-auto ">
            <h2 class="text-center text-6xl font-bold pt-40 max-md:pt-32 max-md:text-5xl">Log Masuk Sebagai</h2>
            <div class="flex justify-center pt-24 w-full h-3/5">
                <div data-aos="zoom-in-right" class="h-full w-[23%] max-md:w-1/2 bg-white rounded-3xl bg-clip-padding backdrop-filter backdrop-blur-md bg-opacity-10 border border-gray-100 mr-10 max-md:mr-3 max-lg:w-[45%] max-lg:h-[80%]">
                    <img class="w-3/5 h-[73%] m-auto py-12" src="/undraw_ideas_flow_re_bmea.svg">
                    <RouterLink to="/logmasuk-pekerja"><button  class="text-white bg-gradient-to-r from-sky-500 to-indigo-500 h-12 px-12 max-md:h-10 max-md:px-10 max-md:text-sm rounded-full shadow-[0_20px_50px_rgba(8,_112,_184,_0.7)] ml-[30%] max-md:ml-3.5 max-lg:ml-[24%]">Pekerja</button></RouterLink>
                    </div>
                <div data-aos="zoom-in-left" class="h-full w-[23%] max-md:w-1/2 bg-white rounded-3xl bg-clip-padding backdrop-filter backdrop-blur-md bg-opacity-10 border border-gray-100 max-lg:w-[45%] max-lg:h-[80%]">
                    <img class="w-4/5 h-[73%] m-auto py-12" src="/undraw_co-working_re_w93t.svg">
                    <RouterLink to="/logmasuk-pengurus"><button class="text-white bg-gradient-to-r from-sky-500 to-indigo-500 h-12 px-12 max-md:h-10 max-md:px-10 max-md:text-sm rounded-full shadow-[0_20px_50px_rgba(8,_112,_184,_0.7)] ml-[30%] max-md:ml-1.5 max-lg:ml-[22%]">Pengurus</button></RouterLink>
                </div>
            </div>
        </div>
    </div>
</template>
  
  
<style>
.backkk{
    background-image: url("/layered-waves-haikei.svg");
    background-repeat: no-repeat;
    background-size: cover;
}

.glass{
    background: rgba( 2, 2, 2, 0.35 );
box-shadow: 0 8px 32px 0 rgba( 31, 38, 135, 0.37 );
backdrop-filter: blur( 11.5px );
-webkit-backdrop-filter: blur( 11.5px );
border-radius: 10px;
border: 1px solid rgba( 255, 255, 255, 0.18 );
}
</style>