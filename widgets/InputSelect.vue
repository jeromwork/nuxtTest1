<template>
  <div class="dropdown search-container" v-if="options">
    <span class="search-special-icon second">
        <svg xmlns="http://www.w3.org/2000/svg" width="16px" height="20px">
          <path fill="rgb(0, 152, 152)" fill-rule="evenodd" :d="iconPath" />
        </svg>
    </span>
    <!-- Dropdown Input -->
    <input class="dropdown-input search-input"
           :name="name"
           @focus="showOptions()"
           @blur="exit()"
           @input="search"
           v-model="searchFilter"
           :disabled="disabled"
           :placeholder="placeholder"
           autocomplete="off"/>

    <!-- Dropdown Menu -->
    <div class="dropdown-content"
         v-show="optionsShown">
      <div
        class="dropdown-item"
        @mousedown="selectOption(option)"
        v-for="(option, index) in healthItems"
        :key="index">
        {{ option.name || option.text || option.id || '-' }}
      </div>
    </div>
  </div>
</template>

<script>
// import axios from 'axios'

    export default {

        name: "InputSelect",
      template: 'Dropdown',
      props: {
        name: {
          type: String,
          required: false,
          default: 'dropdown',
          note: 'Input name'
        },
        options: {
          // type: Array,
          required: false,
          // default: [],
          note: 'Options of dropdown. An array of options with id and name',
        },
        placeholder: {
          type: String,
          required: false,
          default: 'Please select an option',
          note: 'Placeholder of dropdown'
        },
        disabled: {
          type: Boolean,
          required: false,
          default: false,
          note: 'Disable the dropdown'
        },
        maxItem: {
          type: Number,
          required: false,
          default: 6,
          note: 'Max items showing'
        },
        iconPath:{
          type: String,
          required: false,},
      },
      data() {
        return {
          selected: {},
          optionsShown: false,
          searchFilter: '',
          healthItems : [],

        }
      },
      created() {
        this.$emit('selected', this.selected);
        this.search();

      },
      computed: {
        filteredOptions() {
          const filtered = [];
          const regOption = new RegExp(this.searchFilter, 'ig');
          // for (const option of this.options) {
          //   if (this.searchFilter.length < 1 || option.name.match(regOption)){
          //     if (filtered.length < this.maxItem) filtered.push(option);
          //   }
          // }
          return filtered;
        }
      },
      methods: {
          async search(searchString){
            //searchString = (searchString ) ? searchString : '';
            this.$axios.get('api/search/health', (searchString ) ? {search :searchString} : {}).then(response => {
              this.healthItems = (response.data) ? response.data: [];
              console.log(response)
            }).catch( (error) => {
              console.log(error.response)
              // if(error.response.status === 422 && error.response.data){//ошибка заполнения полей
              //   this.commit('Login/SET_SERVER_ERRORS', error.response.data);
              // }
            });
            return ;
          },
        selectOption(option) {
          this.selected = option;
          this.optionsShown = false;
          this.searchFilter = this.selected.name;
          this.$emit('selected', this.selected);
        },
        showOptions(){
          if (!this.disabled) {
            this.searchFilter = '';
            this.optionsShown = true;
          }
        },
        exit() {
          if (!this.selected.id) {
            this.selected = {};
            this.searchFilter = '';
          } else {
            this.searchFilter = this.selected.name;
          }
          this.$emit('selected', this.selected);
          this.optionsShown = false;
        },
        // Selecting when pressing Enter
        keyMonitor: function(event) {
          if (event.key === "Enter" && this.filteredOptions[0])
            this.selectOption(this.filteredOptions[0]);
        }
      },
      watch: {
        searchFilter() {
          if (this.filteredOptions.length === 0) {
            this.selected = {};
          } else {
            this.selected = this.filteredOptions[0];
          }
          this.$emit('filter', this.searchFilter);
        }
      }
    }
</script>

<style lang="scss" scoped>


  .search-input {
    width: 320px;
    margin: 0 5px 15px 0;
    padding: 8px 4px 8px 35px;
    line-height: 0.9em;
    border-radius: 4px;
    border: 1px solid var(--border-color);
    z-index: 100;
  }
  .search-container {
    position: relative;
    display: inline-block;
  }

  .search-special-icon {
    top: 6px;
    left: 8px;
    position: absolute;
    display: block;
    z-index: 110;
  }

  .dropdown {
    position: relative;
    display: block;
    margin: auto;
  .dropdown-input {
    background: #fff;
    cursor: pointer;
    border: 1px solid #e7ecf5;
    border-radius: 3px;
    display: block;
    min-width: 250px;
    max-width: 250px;
  &:hover {
     background: #f8f8fa;
   }
  }
  .dropdown-content {
    position: absolute;
    background-color: #fff;
    min-width: 248px;
    max-width: 248px;
    max-height: 248px;
    border: 1px solid #e7ecf5;
    box-shadow: 0px -8px 34px 0px rgba(0,0,0,0.05);
    overflow: auto;
    z-index: 1;
  .dropdown-item {
    color: black;
    font-size: .7em;
    line-height: 1em;
    padding: 8px;
    text-decoration: none;
    display: block;
    cursor: pointer;
  &:hover {
     background-color: #e7ecf5;
   }
  }
  }
  .dropdown:hover .dropdowncontent {
    display: block;
  }
  }
</style>
