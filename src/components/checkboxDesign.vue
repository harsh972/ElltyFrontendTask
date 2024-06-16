<template>
  <div>  
    <!-- checkbox deign container -->
    <div class="checkboxs">
    <!-- All select checkbox -->
    <div class="check-div d-flex justify-content-between">
      <label for="selectAll">All Pages</label>
      <input v-model="selectAllChecked" class="form-check-input custom-checkbox" type="checkbox" id="selectAll" @change="showChecked=false">
    </div>
    <hr>
    <!-- Checkbox options container-->
    <div class="checkbox-container">
      <template v-for="(item, index) in checkboxItems">
        <div class="check-div d-flex justify-content-between" :key="index">
          <label :for="'checkbox_' + index">{{ item.label }}</label>
          <input v-model="selectedValues" class="form-check-input custom-checkbox" type="checkbox" :value="item.value" :id="'checkbox_' + index" @change="showChecked=false">
        </div>
      </template>
    </div>
    <hr>
    <button type="button" class="btn button" @click="showChecked=true">Done</button>
  </div>
  <div v-if="showChecked && selectedValues.length>0" class="mt-5" style="width: 360px;">Selected Values are - {{ selectedValues }}</div>
</div>

</template>

<script>
export default {
  name: 'checkBoxDesign',
  data() {
    return {
      selectedValues: [],
      checkboxItems: [
        { label: 'Page 1', value: 'Page 1' },
        { label: 'Page 2', value: 'Page 2' },
        { label: 'Page 3', value: 'Page 3' },
        { label: 'Page 4', value: 'Page 4' },
      ],
      showChecked: false,
    }
  },
  computed: {
    selectAllChecked: {
      get() {
        return this.selectedValues.length === this.checkboxItems.length;
      },
      set(value) {
        if (value) {
          this.selectedValues = this.checkboxItems.map(item => item.value);
        } else {
          this.selectedValues = [];
        }
      }
    }
  }
}
</script>


<!-- Added "scoped" attribute to limit CSS to this component only -->
<style scoped>

.checkbox-container{
  width: 370px; 
  height: 164px; 
}

.custom-checkbox {
  width: 23px;
  height: 23px;
  border-radius: 6px;
  cursor: pointer;
  margin: 0px !important;
}

.form-check-input:checked[type=checkbox]{
  background-image:url("data:image/svg+xml,%3Csvg width='17' height='13' viewBox='0 0 17 13' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M0.68 6.592L6.22879 11.5272C6.24925 11.5454 6.28055 11.5437 6.29899 11.5235L16.32 0.520004' stroke='white' stroke-linecap='round'/%3E%3C/svg%3E%0A");
  background-size: 15.8px !important;
  background-repeat: no-repeat;
  background-position: center;
}

.form-check-input[type=checkbox]:not(:checked):hover {
  background-image: url("data:image/svg+xml,%3Csvg width='17' height='13' viewBox='0 0 17 13' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M0.68 6.592L6.22879 11.5272C6.24925 11.5454 6.28055 11.5437 6.29899 11.5235L16.32 0.519997' stroke='%23E3E3E3' stroke-linecap='round'/%3E%3C/svg%3E%0A");
  background-size: 15.8px !important;
  background-repeat: no-repeat;
  background-position: center;
  border: 0.5px solid #BDBDBD;
}

.form-check-input[type=checkbox]:checked:hover {
  background-color: #5087F8;
}

.form-check-input:not(:checked):active{
  box-shadow: 0 0 0 .25rem rgba(10,80,231,0.15);
}

.form-check-input:focus{
  box-shadow: none;
  border-color: #dee2e6;
}

.custom-checkbox:checked {
  background-color: #2469F6;
  border-color: #2469F6;
}

.check-div{
  width: 370px !important;
  height: 42px !important;
  top: -1px;
  left: -1px;
  padding: 8px 15px 8px 22px;
  gap: 0px;
  justify: space-between;
}

.checkboxs{
  width: 370px;
  height: 326px;
  padding: 10px 0px 10px 0px;
  gap: 0px;
  border-radius: 6px;
  box-shadow: -2px 8px 15px 3px #1414141F;
}

.button{
  width: 340px;
  height: 40px;
  gap: 10px;
  radius: 4px;
  background-color: #FFCE22;
  margin-top: 10px;
}

.button:hover{
  background-color: #FFD84D;
}

.button:active{
  background-color: #FFCE22;
  border-color: #FFCE22 !important;
}

hr{
  margin: 10px 15px 10px 15px;
  gap: 10px;
  opacity: 0.2;
  display: flex;
}

</style>
