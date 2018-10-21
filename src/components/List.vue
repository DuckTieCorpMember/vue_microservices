<template>
<div>
    <div class="upper-bar">
        <div class="search-div autocomplete">
            <input type="text" placeholder="Type to find service ..."
                v-model="search" @input="onChange"/>
            <ul v-show="isOpen" class='autocomplete-results'>
                <li class="autocomplete-result"
                    v-for="(result, i) in results" :key='i'
                    @click="setResult(result)">{{result}}</li>
            </ul>
        </div>
        <div class="add-div">
            <button class='add-button' @click="showModal = true">+</button>
        </div>
    </div>
    <div class="listanddesc">
        <div class="list-div">
            <ul class="list-ul">
                <li v-for="(item, index) in forlist" :key="index" v-on:click="showDescription(item['_id'])">{{item.name.first}} {{item.name.last}}</li>
            </ul>
        </div>
        <div class="service-details">
            <div id='details-text'>EMPTY</div>
        </div>
    </div>
</div>
</template>

<script>
import data from './../assets/json/data.json'
import $ from 'jquery'
export default {
    data(){
        return{
            forlist: data,
            search: '',
            results: [],
            isOpen: false
        }
    },
    methods:{
        showDescription(_id){
            let obj = null;
            this.forlist.forEach(el => {
                if(el._id === _id)
                    obj = el;
            });
            $('#details-text').html(obj.email);
        },
        onChange(){
            this.isOpen = true;
            this.filterResults();
        },
        filterResults(){
            this.results = this.arrayForSearch.filter(item => item.toLowerCase().indexOf(this.search.toLowerCase())>-1)
        },
        setResult(result){
            this.search = result;
            this.isOpen = false;
            let strarr = result.split(' ');
            this.forlist.forEach(element => {
                if(element['name']['first'] === strarr[0] && element['name']['last'] === strarr[1])
                {
                    this.showDescription(element['_id']);
                    return;
                }
            });
        }
    },
    computed:{
        arrayForSearch(){
            let newarr = [];
            this.forlist.forEach(el => {
                newarr.push(el['name']['first']+" "+el['name']['last']);
            });
            return newarr;
        }
    }
}
</script>

<style scoped>
    .listanddesc{
        display: flex;
        flex-direction: row;
        width: 600px;
    }
    .list-div{
        width: 30%;
        background-color: rgb(208, 208, 208);
    }
    .service-details{
        width: 70%;
        background-color:rgb(43, 43, 43);
        color: white; 
    }
    .autocomplete{
        width: 100%;
    }
    .autocomplete input{
        width: 100%;
    }
    .autocomplete-results{
        padding: 0;
        margin: 0;
        border: 1px solid #eeeeee;
        height: 100px;
        overflow: overlay;
        position: absolute;
        background-color: rgb(208, 208, 208);
        width: 500px;
    }
    .autocomplete-result{
        list-style: none;
        text-align: left;
        padding: 4px, 2px;
        cursor: pointer;
    }
    .autocomplete-result:hover{
        background-color: #4AAE98;
        color: rgb(43, 43, 43);
    }
    .add-button{
        font-size: 26px;
    }
    .add-div{
        width: 0;
        height: 100%;
    }
    .search-div{
        width: 94%;
        margin-right: 5px;
    }
    .search-div input{
        height: 100%;
        font-size: 24px;
    }
    .upper-bar{
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: flex-start;
        align-items: stretch;
        box-sizing: border-box;
        position: relative;
        width: 600px;
        height: auto;
        font-size: 0.76562rem;
        background-color: #ffffff;
        justify-content: space-between;
        margin-bottom: 15px;
    }

</style>
