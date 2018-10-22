<template>
    <div class="layout block-body">
        <div class="layout__block shrink header-mm">
            <div class="control-bar control-bar--sub">
                <div class="control-bar__layout shrink">
                    <div class="search">
                        <button type="button" class="search__button button">
                            <span class="button__icon icon icon--baseline">
                                <svg class="icon__svg" viewBox="0 0 31 31" version="1.1">
                                    <path d="M20.797,13.185c0,-2.095 -0.745,-3.888 -2.234,-5.377c-1.49,-1.49 -3.282,-2.235 -5.378,-2.235c-2.095,0 -3.888,0.745 -5.377,2.235c-1.49,1.489 -2.235,3.282 -2.235,5.377c0,2.096 0.745,3.888 2.235,5.378c1.489,1.489 3.282,2.234 5.377,2.234c2.096,0 3.888,-0.745 5.378,-2.234c1.489,-1.49 2.234,-3.282 2.234,-5.378Zm8.699,14.136c0,0.589 -0.215,1.099 -0.645,1.53c-0.431,0.43 -0.941,0.645 -1.53,0.645c-0.611,0 -1.121,-0.215 -1.529,-0.645l-5.828,-5.811c-2.027,1.404 -4.287,2.107 -6.779,2.107c-1.62,0 -3.169,-0.315 -4.647,-0.943c-1.478,-0.629 -2.752,-1.479 -3.823,-2.549c-1.07,-1.07 -1.92,-2.345 -2.548,-3.823c-0.629,-1.478 -0.943,-3.027 -0.943,-4.647c0,-1.62 0.314,-3.169 0.943,-4.647c0.628,-1.478 1.478,-2.752 2.548,-3.823c1.071,-1.07 2.345,-1.92 3.823,-2.548c1.478,-0.629 3.027,-0.943 4.647,-0.943c1.62,0 3.169,0.314 4.647,0.943c1.478,0.628 2.753,1.478 3.823,2.548c1.07,1.071 1.92,2.345 2.549,3.823c0.628,1.478 0.943,3.027 0.943,4.647c0,2.492 -0.703,4.752 -2.107,6.779l5.828,5.828c0.419,0.419 0.628,0.929 0.628,1.529Z"></path>
                                </svg>
                            </span>
                        </button>
                        <div class="search__div">
                            <input class="search__input" placeholder="Enter service ..."
                                v-model="search" @input="onChange"/>
                            <ul class="autocomplete-results" v-show="isOpen">
                                <li class="autocomplete-result" v-for="(result,i) in results" :key='i'
                                    @click="setResult(result)">{{result.name}}                                    
                                </li>
                            </ul>
                        </div>
                        <button type="button" class="search__clear-button button">
                            <span class="button__icon icon icon--baseline">
                                <svg class="icon__svg" viewBox="0 0 31 31" version="1.1">
                                    <path d="m 22.47134,19.635231 q 0,-0.475735 -0.347652,-0.823387 L 18.811844,15.5 22.123688,12.188156 q 0.347652,-0.347652 0.347652,-0.823387 0,-0.494032 -0.347652,-0.841684 L 20.476915,8.8763118 q -0.347652,-0.3476521 -0.841684,-0.3476521 -0.475735,0 -0.823387,0.3476521 L 15.5,12.188156 12.188156,8.8763118 q -0.347652,-0.3476521 -0.823387,-0.3476521 -0.494032,0 -0.841684,0.3476521 L 8.8763117,10.523085 q -0.3476519,0.347652 -0.3476519,0.841684 0,0.475735 0.3476519,0.823387 L 12.188156,15.5 8.8763117,18.811844 q -0.3476519,0.347652 -0.3476519,0.823387 0,0.494032 0.3476519,0.841684 l 1.6467733,1.646773 q 0.347652,0.347652 0.841684,0.347652 0.475735,0 0.823387,-0.347652 L 15.5,18.811844 l 3.311844,3.311844 q 0.347652,0.347652 0.823387,0.347652 0.494032,0 0.841684,-0.347652 l 1.646773,-1.646773 Q 22.47134,20.129263 22.47134,19.635231 Z M 29.552465,15.5 q 0,3.824174 -1.88464,7.053679 -1.88464,3.229506 -5.114146,5.114146 -3.229505,1.88464 -7.053679,1.88464 -3.824174,0 -7.0536791,-1.88464 Q 5.2168155,25.783185 3.332175,22.553679 1.4475342,19.324174 1.4475342,15.5 q 0,-3.824174 1.8846408,-7.053679 Q 5.2168155,5.2168155 8.4463209,3.332175 11.675826,1.4475342 15.5,1.4475342 q 3.824174,0 7.053679,1.8846408 3.229506,1.8846405 5.114146,5.114146 1.88464,3.229505 1.88464,7.053679 z">
                                    </path>
                                </svg>
                            </span>
                        </button>
                    </div>
                </div>
                <div class="control-bar__layout">
                    <button v-on:click="showModal = true" class="button">Add service</button>
                </div>
            </div>
        </div>
        <div class="layout__block">
            <div class="layout__row">
                <div class="layout__block shrink">
                    <div class="service-list">
                        <div class="service-list__header">
                            <span class="text-large bold">Service List</span>
                        </div>
                        <div class="service-list__body">
                            <ul class="list">
                                <li class="list__layout" v-for="(item,index) in orderedList" :key="index" v-on:click="showDescription(item['_id'])">{{item.name}}</li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="layout__block">
                    <div class="layout__table">
                        <table class="table table--details">
                            <thead class="table__thead">
                                <tr class="table__row">
                                    <th class="table__th table__th--nowrap">
                                        <span class="text-large bold">Details</span>
                                    </th>
                                    <th class="table__th">
                                        <div class="panel">
                                            <div class="panel__layout shrink">
                                                <button v-on:click="edit_modal" class="button">Edit</button>
                                            </div>
                                            <div class="panel_layout">
                                                <button class="button">Delete</button>
                                            </div>
                                        </div>
                                    </th>
                                </tr>
                            </thead>
                            <tbody class="table__tbody">
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right table__td--nowrap">Name</td>
                                    <td id="name-and-id" class="table__td">{{desc_name}} ({{desc_id}})</td>
                                </tr>
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right">Description</td>
                                    <td id="description-id" class="table__td">{{desc_desc}}</td>
                                </tr>
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right">Projects</td>
                                    <td class="table__td">
                                        <div class="panel">
                                            <ul>
                                                <li style="float: left;" class="panel__layout shrink"
                                                    v-for="(item,index) in projects" :key="index">
                                                    <a class="link" :href="item.link">
                                                        {{item.name}}
                                                    </a>
                                                </li>
                                            </ul>                                            
                                        </div>
                                    </td>
                                </tr>
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right">End Points</td>
                                    <td class="table__td">{{desc_end}}</td>
                                </tr>
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right">Git</td>
                                    <td class="table__td"><a id="git-text" class="link">{{desc_git}}</a></td>
                                </tr>
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right">.JARs</td>
                                    <td class="table__td">
                                        <div class="panel">
                                            <ul>
                                                <li style="float: left;" class="panel__layout shrink"
                                                    v-for="(item,index) in jars" :key="index">
                                                    <a class="link" :href="item.link">
                                                        {{item.name}}
                                                    </a>
                                                </li>
                                            </ul>     
                                        </div>
                                    </td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
        <div class="modal" v-show="showModal">
            <div class="modal-wrapper">
                <div class="modal-container">
                    <content select=".modal-header">
                        <div class="modal-header">
                            <h3 v-if="adding">
                                Fill out this forms:
                            </h3>
                            <h3 v-if="!adding">
                                Edit what you need:
                            </h3>
                            <hr>
                            <br/>                            
                        </div>
                    </content>
                    <div class="modal-body">
                        <table class="table table--details">
                            <tbody class="table__tbody">
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right table__td--nowrap">Name</td>
                                    <td>
                                        <input v-model="toAdd.name" class="search__input" placeholder="Enter name of service ..."/>
                                        <p class="warning-p" v-show="addformtemps.show_name_warning">Enter a name</p>
                                    </td>
                                </tr>
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right table__td--nowrap">Description</td>
                                    <td>
                                        <input v-model="toAdd.description" class="search__input" placeholder="What does a service perform?"/>
                                        <p class="warning-p" v-show="addformtemps.show_desc_warning">Enter a brief description</p>
                                    </td>
                                </tr>
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right table__td--nowrap">Projects</td>
                                    <td>
                                        <ul class="add-form-list">
                                            <li class="autocomplete-results" v-for="(item,index) in toAdd.projects" :key="index">{{item.name}}</li>
                                        </ul>
                                        <div>
                                            <div class="name-link-form">
                                                <input v-model="addformtemps.pr_name" class="search__input" placeholder="Project Name"/>
                                                <input v-model="addformtemps.pr_link" class="search__input" placeholder="Project Link"/>
                                                <button v-on:click="addToAdd('projects', addformtemps.pr_name, addformtemps.pr_link)" class="button">+</button>
                                            </div>
                                            <p class="warning-p" v-show="addformtemps.show_pr_warning">Enter at least 1 project</p>
                                        </div>
                                    </td>
                                </tr>
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right table__td--nowrap">.JARs</td>
                                    <td>
                                        <ul class="add-form-list">
                                            <li class="autocomplete-results" v-for="(item,index) in toAdd.jars" :key="index">{{item.name}}</li>
                                        </ul>
                                        <div>
                                            <div class="name-link-form">
                                                <input v-model="addformtemps.jr_name" class="search__input" placeholder="JAR Name"/>
                                                <input v-model="addformtemps.jr_link" class="search__input" placeholder="JAR Link"/>
                                                <button v-on:click="addToAdd('jars', addformtemps.jr_name, addformtemps.jr_link)" class="button">+</button>
                                            </div>
                                            <p class="warning-p" v-show="addformtemps.show_jr_warning">Enter at least 1 .jar file name</p>
                                        </div>
                                    </td>
                                </tr>
                                <tr class="table__row">
                                    <td class="table__td table__td--txt-right table__td--nowrap">End Points</td>
                                    <td>
                                        <input v-model="toAdd.endpoints" class="search__input" placeholder="Enter end points ..."/>
                                        <p class="warning-p" v-show="addformtemps.show_endp_warning">Enter an end point</p>
                                    </td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                    <div class="modal-footer uk-clearfix">
                        <button v-on:click="addService" v-if='adding' class="button button--add">Add</button>
                        <button v-on:click="editService" v-if='!adding' class="button button--progress">Edit</button>
                        <button style="float: right;" v-on:click="showModal = false" class="button button--close">Close</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import data from './../assets/json/generated.json'
import $ from 'jquery'

export default { 
    data(){
        return{
            listData: data,
            search: '',
            desc_id: '',
            desc_name: '',
            desc_end:'',
            desc_git:'',
            desc_desc:'',
            results: [],
            isOpen: false,
            projects: [],
            jars: [],
            showModal: false,
            adding: true,
            toAdd: {
                '_id': '',
                'name': "",
                'description': "",
                'projects': [],
                'endpoints': "",
                'git': '',
                'jars': []
            },
            addformtemps: {
                'pr_name':'',
                'pr_link':'',
                'jr_name':'',
                'jr_link':'',
                'show_name_warning': false,
                'show_desc_warning': false,
                'show_endp_warning': false,
                'show_pr_warning': false,
                'show_jr_warning': false
            }
        }
    },
    methods:{
        showDescription(_id){
            let obj = null;
            this.listData.forEach(el => {
                if(el._id === _id)
                    obj = el;
            });
            this.desc_name = obj.name;
            this.desc_id = obj._id;
            //this.desc_end = obj.endpoints;
            this.desc_desc = obj.description;
            this.desc_git = obj.git;
            $('#name-and-id').html(obj.name+" ("+obj._id+")");
            $('#description-id').html(obj.description);
            $('#git-text').html(obj.git);
            this.projects = obj['projects'];
            this.jars = obj['jars'];
        },
        onChange(){
            this.isOpen = true;
            this.filterResults();
        },
        filterResults(){
            this.results = this.listData.filter(item => item.name.toLowerCase().indexOf(this.search.toLowerCase())>-1)
        },
        setResult(result){
            this.search = result.name;
            this.isOpen = false;
            this.listData.forEach(element => {
                if(element.name == result.name)
                {
                    this.showDescription(element['_id']);
                    return;
                }
            });
        },
        addService(){
            if(this.toAdd.name === ""){
                this.addformtemps.show_name_warning = true;
                return;
            }
            if(this.toAdd.description === ""){
                this.addformtemps.show_desc_warning = true;
                return;
            }
            if(this.toAdd.endpoints === ""){
                this.addformtemps.show_endp_warning = true;
                return;
            }
            if(this.toAdd.projects.length === 0){
                this.addformtemps.show_pr_warning = true;
                return;
            }
            if(this.toAdd.jars.length === 0){
                this.addformtemps.show_jr_warning = true;
                return;
            }
            this.toAdd._id = this.fakeID();
            this.listData.push(this.toAdd);
            this.reset_addform();
        },
        reset_addform(){
            this.toAdd = {
                '_id': '',
                'name': "",
                'description': "",
                'projects': [],
                'endpoints': "",
                'git': '',
                'jars': []
            };
            this.addformtemps = {
                'pr_name':'',
                'pr_link':'',
                'jr_name':'',
                'jr_link':'',
                'show_name_warning': false,
                'show_desc_warning': false,
                'show_endp_warning': false,
                'show_pr_warning': false,
                'show_jr_warning': false
            }
        },
        addToAdd(arrayname, name, link){
            if(arrayname === 'projects'){
                if(name !== ''){
                        this.toAdd.projects.push({
                        'name': name,
                        'link': link
                    });
                }
                this.addformtemps.pr_name = "";
                this.addformtemps.pr_link = "";
            }
            else if(arrayname === 'jars'){
                if(name !== ''){
                        this.toAdd.jars.push({
                        'name': name,
                        'link': link
                    });
                }
                this.addformtemps.jr_name = "";
                this.addformtemps.jr_link = "";
            }
        },
        predicateBy(prop){
            return function(a,b){
                if( a[prop] > b[prop]){
                    return 1;
                }else if( a[prop] < b[prop] ){
                    return -1;
                }
                return 0;
            }
        },
        fakeID() {
            var text = "";
            var possible = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789";
            for (var i = 0; i < 10; i++)
                text += possible.charAt(Math.floor(Math.random() * possible.length));
            return text;
        },
        edit_modal(){
            this.adding = false;
            this.showModal = true;
            this.toAdd = {
                '_id': this.desc_id,
                'name': this.desc_name,
                'description': this.desc_desc,
                'projects': this.projects,
                'endpoints': this.desc_end,
                'git': this.desc_git,
                'jars': this.jars
            };
        },
        editService(){
            this.listData.forEach(element => {
                if(element._id === this.toAdd._id){
                    let k;
                    for(key in element){
                        element[key] = this.toAdd[key];
                    }
                }
            });
            this.reset_addform();
            this.showModal=false;
        }
    },
    computed:{
        orderedList(){
            return this.listData.slice().sort(this.predicateBy('name'));
        }
    },
    beforeMount(){
        this.showDescription(this.orderedList[0]._id);
    }
}
</script>

<style scoped>
    @import './css/service_list.css';

    .header-mm{
        margin-bottom: 1rem;
    }
    .search__div{
        width: 100%;
    }
    .autocomplete-result{
        z-index: 999;
        padding: 0;
        margin: 0;
        border: 1px solid #a0a0a0;
        height: 10rem;
        width: 93%;
        overflow:auto;
        position: absolute;
        background-color: rgba(255, 255, 255, 0.804);
        font-size: 0.76562rem;
    }
    .autocomplete-results{
        list-style: none;
        text-align: left;
        cursor: pointer;
    }

    .modal {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.7);
        display: table;
        transition: opacity .3s ease;
        z-index: 5;
    }
    .modal-wrapper {
        display: table-cell;
        vertical-align: middle;
    }
    .modal-container {
        background: #fff;
        width: 450px;
        border-radius: 5px;
        box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
        transition: all .3s ease;
        margin: 0 auto;
        padding: 20px 30px;
    }
    .modal-footer {
        margin-top: 15px;
    }
    .button--add{
        color:white;
        background-color: #6bae6e;
    }
    .button--close{
        color:white;
        background-color: #b83737;
    }
    .button--progress{
        color:white;
        background-color: #0f5fa5;
    }
    .button--ready{
        background-color: #ffffff;
        color: black;
    }
    .modal-enter, .modal-leave {
        opacity: 0;
    }
    .modal-enter .modal-container, .modal-leave .modal-container {
        -webkit-transform: scale(1.1);
        transform: scale(1.1);
    }
    .name-link-form{
        display: flex;
        flex-direction: row;
    }
    .add-form-list{
        padding: 1rem;
    }
    .warning-p{
        color: #b83737;
    }
</style>