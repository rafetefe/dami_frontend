<template>
    <div class="Gonullu">
        <div class="ml-auto mr-auto bg-gray-600 ">            
            <div class="border-2 ml-auto mr-auto pt-10 h-full w-1/2 rounded-md bg-white pb-20"> 
                <div class="text-4xl font-bold ml-3">
                    <h1>Gönüllü Formu</h1>
                </div>             
                <form @submit.prevent="Create()" class="w-full m-30 bg-white text-left pl-40 rounded-xl pt-10 ">
                    <label class="text-gray-800 inline-block text-xs uppercase tracking-wider font-bold mt-2 mb-4 mx-0">İSİM :</label>
                    <input id="input-isim" v-model="post.isim" class="block w-4/5 box-border px-6 py-3 border-b-solid border-b-black border-b " type="text" required >

                    <label class="text-gray-800 inline-block text-xs uppercase tracking-wider font-bold mt-2 mb-4 mx-0">SOYİSİM :</label>
                    <input id="input-soyisim" v-model="post.soyisim" class="block w-4/5 box-border px-6 py-3 border-b-solid border-b-black border-b " type="text" required >

                    <label class="text-gray-800 inline-block text-xs uppercase tracking-wider font-bold mt-2 mb-4 mx-0">TELEFON :</label>
                    <input id="input-telefon" v-model="post.telefon" class="block w-4/5 box-border px-6 py-3 border-b-solid border-b-black border-b " type="tel" required >
                    
                    <label class="text-gray-800 inline-block text-xs uppercase tracking-wider font-bold mt-2 mb-4 mx-0">POSTAKODU :</label>
                    <input id="input-postakodu" v-model="post.postakodu" class="block w-4/5 box-border px-6 py-3 border-b-solid border-b-black border-b " type="tel" required >

                    <label class="text-gray-800 inline-block text-xs uppercase tracking-wider font-bold mt-2 mb-4 mx-0">ADRES :</label>
                    <input id="input-adres" v-model="post.adres" class="block w-4/5 box-border px-6 py-3 border-b-solid border-b-black border-b " type="tel" required >

                      
                    <div>
                        <button class="rounded-full border-2 h-10  bg-black text-neutral-50 mt-10 w-4/5">Kayıt Oluştur</button>
                    </div>      
                </form>                   
            </div>    
        </div>    
    </div>

</template>
<script>
import axios from 'axios'

export default {
    name:'Gonullu',
    data(){
        return{
            post:{
                isim:'',
                soyisim:'',
                telefon:'',
                postakodu:'',
                adres:''
            }
         };
    },
    methods:{
        Create(){
            axios.post("http://localhost:5000/gonullu",this.post
            ).then(res=>{
                console.log(this.post)
                console.warn(res)
        });
    },

}}
</script>



<style>

</style>