<template>
    <div class="container shadow p-3 mb-5 bg-white rounded">
<div  class="coloum-head">
    <div class="d-flex flex-column align-items-end first first-column">
    <div class="dropdown w-100">
      <button
        class="btn dropdown-toggle text-white w-100"
        type="button"
        data-bs-toggle="dropdown"
        aria-haspopup="true"
        aria-expanded="false"
        @click="toggleDropdown1"
        :class="{ show: isDropdown1Open }"
      >
        <span class="name">SHOP BY CATEGORY</span>
      </button>
      <ul class="dropdown-menu w-100" :class="{ show: isDropdown1Open }" aria-labelledby="dropdownMenuButton">
        <li>
          <a class="dropdown-item first-li bold" href="#" @click.stop="toggleColumn2" style="background-color: #eaebeb;  height: 3rem;">    Fruits & Vegetables
    </a>   
            </li>
        <li >
          <a class="dropdown-item bor" v-for="title in Vegetables" :key="title.title">
            {{ title.title }}
          </a>
        </li>
      </ul>
    </div>
  </div>
</div>
      
<div class="wrt " >
  <div class="first second-column">
    <div class="port">
      <span class="material-symbols-outlined">sell</span>
      <span class="dis">OFFER</span>
    </div>
  </div>
  <div id="col2Div" v-if="isColumn2Visible">
    <ul class="data">
  
      <li class="bg bold"  @click.stop="toggleColumn3" >Fresh Vegetables</li>
      <template v-for="title in discount" :key="title.title">
        <li>{{ title.title }}</li>
      </template>
    </ul>
  </div>
</div>

<div class="mrt" >
  <div class="first third-column"></div>
  <div>
    <ul class="vegetable-list" id="col3Div" v-if="isColumn3Visible">
      <template v-for="title in next" :key="title.title">
        <li>{{ title.title }}</li>
      </template>
    </ul>
  </div>
</div>

   
    </div>
  </template>
  
  <style>
  .container {
    display: flex;
    justify-content: center;
    margin-top: 5rem;
    width: 50%;
    max-width: 20rem;
    height: 43rem;
  }
  
  .first {
    display: flex;
    align-items: center;
    justify-content: center;
    color: #fff;
    font-size: 18px;
    font-weight: bold;
    width: 49%;
    text-align: center;
  }
  
  .first-column {
    width: 20rem;
    background-color: #84c325;
  }
  
  .second-column,
  .third-column {
    width: 18rem;
    background-color: #fefffe;
    border: 1px solid #eaebeb;
  }
  .third-column{
    height: 39px;
  }

.dropdown-toggle {
  left: 0;
}
.name{
    margin-right: 4rem;
    font-size: 1.3rem;
    font-weight: bold;
}


.bor{
    border-top: 1px solid #eaebeb;
  border-bottom: 1px solid #eaebeb;
  border-left: 1px solid #eaebeb;
  border-right: none;  height: 3rem;
  line-height: 2; 

}

.dropdown-menu {
  border: none !important;
}
.li-head{
  background-color: #7e7a7a;
}

.dis{
    color: #726b6b;
}

.material-symbols-outlined{
    color: #da241c;
    font-size: 2rem;
    margin-right: 1rem;
    fill: #da241c;
}
.port{
    margin-left: -10rem;
    color: #7e7e7f;
    
}

.data li {
  list-style: none;
  border: none;
  line-height: 3; 
  display: inline-block;
  padding-left: 1rem;

    margin-left: -10px;
    margin-right: -10px;
 
 
}
.data{
    background-color: #eaebeb;
    padding: 0;
    margin: 0;
}
.bg  {
  background-color: #fff;
  height: 3rem;
  margin-top: -10px;
    margin-left: -10px;
    margin-right: -10px;
}
.data {
  padding: 10px;
  margin: 10px 0;
  display: flex;
  flex-direction: column;
  height: 36rem;
}
.vegetable-list {
  padding: 10px;
  margin-top: 1rem;
  display: flex;
  flex-direction: column;
  height: 36rem;
  background-color: #f8f9fa;
}

.vegetable-list li {
  margin: 5px 0;
  list-style: none;
  line-height: 2; 
  display: inline-block;
  border: none;
  height: 3rem;
    margin-left: -10px;
    margin-right: -10px;
    padding-left: 1rem;

}
.vegetable-list li:hover {
    background-color: #ffff;; 
  color: black; 
  text-decoration: none;
 
}

.bold{
    font-weight: bold;
}
.dropdown-menu .li-head.bold {
  font-weight: bold;
}


.data li:hover{
    background-color: #f8f9fa; 
  color: #212529; 
  text-decoration: none; 
}
.data .bg:hover{
    background-color: #fff; 
  color: black; 
  text-decoration: none; 
}
.dropdown .dropdown-item:hover{
    background-color: #eaebeb; 
  color: black; 
  text-decoration: none;
}

</style>


<script setup>
import { ref } from 'vue';

const isDropdown1Open = ref(false);
const isColumn2Visible = ref(false);
const isColumn3Visible = ref(false);




// methods

const toggleDropdown1 = () => {
  isDropdown1Open.value = !isDropdown1Open.value;
};

const toggleColumn2 = () => {
  isColumn2Visible.value = !isColumn2Visible.value;
};

const toggleColumn3 = () => {
  isColumn3Visible.value = !isColumn3Visible.value;
};


const jsonData = {
    
    "categories": [
      {
        "name": "Fruits & Vegetables",
        "titles": [
          {
            "title": "Foodgrains, Oil, & Masala"
          },
          {
            "title": "Bakery, Cakes, & Dairy"
          },
          {
            "title": "Beverages"
          },
          {
            "title": "Snacks & Branded Foods"
          },
          {
            "title": "Beauty & Hygiene"
          },
          {
            "title": "Cleaning & Household"
          },
          {
            "title": "Kitchen, Garden, & Pets"
          },
          {
            "title": "Eggs, Meat, & Fish"
          },
          {
            "title": "Gourmet & World Food"
          },
          {
            "title": "Baby Care"
          },
          {
            "title": "View All"
          }
        ]
      },
      {
        "name": "offer",
        "titles": [
          {
            "title": "Herbs & Seasonings"
          },
          {
            "title": "Fresh Fruits"
          },
          {
            "title": "Organic Fruits & Vegetables"
          },
          {
            "title": "Cuts & Sprouts"
          },
          {
            "title": "Exotic Fruits & Veggies"
          },
          {
            "title": "Flower Bouquets, Bunches"
          }
        ]
      },
      {
        "name": "other",
        "titles": [
          {
            "title": "Potato, Onion & Tomato"
          },
          {
            "title": "Cucumber & Capsicum"
          },
          {
            "title": "Root Vegetables"
          },
          {
            "title": "Leafy Vegetables"
          },
          {
            "title": "Beans, Brinjals & Okra"
          },
          {
            "title": "Cabbage & Cauliflower"
          },
          {
            "title": "Gourd, Pumpkin, Drumstick"
          },
          {
            "title": "Specialty"
          }
        ]
      }
    ]
  }
  


  const  Vegetables = jsonData.categories.find((category) => category.name === 'Fruits & Vegetables').titles;
  const discount = jsonData.categories.find((category) => category.name === 'offer').titles;
  const next = jsonData.categories.find((category) => category.name === 'other').titles;
</script>
  