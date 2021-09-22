<template>
   <div class="conversor">
       <h2> {{moedaA}} para {{moedaB}}</h2>
       <div class="inputs">
            <input type="text" v-model="moedaA_value" v-bind:placeholder="moedaA">
            <input type="button" value="Converter" v-on:click="converter">
       </div>
       <h2>{{moedaB_value}}</h2>
   </div>
</template>

<script>
export default{
    name: "Conversor",
    props: ["moedaA", "moedaB"],
    data() {
        return{
            moedaA_value: "",
            moedaB_value: "-",
        }
    },
    methods: {
        converter(){
            let de_para = this.moedaA + "_" + this.moedaB;
            console.log(de_para)
            let url ="https://free.currconv.com/api/v7/convert?q="+
                de_para
            +"&compact=ultra&apiKey=1ab97c2af38b1dd31e5b"
            console.log(url)
            fetch(url).then(res => res.json()).then(out=>{
                let cotacao = out[de_para];
                console.log(cotacao)
                this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2)
            })
        }
    } 
};
</script>

<style scoped>

.conversor{
    padding: 20px;
    max-width: 300px;
    box-shadow: 0 4px 8px 0 darkgray;
    background-color: rgb(236, 236, 236);
}



</style>
