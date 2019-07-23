<template>
  <div class="other">
    <input v-model.number="message" placeholder="edit me">
    <p>Message is: {{ message }}</p>
    <span>Multiline message is:</span>
    <p style="white-space: pre-line;">{{ message_textarea }}</p>
    <br>
    <textarea v-model.lazy.trim="message_textarea" placeholder="add multiple lines"></textarea>
    <input type="checkbox" id="checkbox" v-model="check">
    <label for="checkbox">{{ check }}</label>
    <div class="chenckbox-group">
        <input type="checkbox" id="john" value="john" v-model="checkname">
        <label for="john">john</label>
        <input type="checkbox" id="Jack" value="jack" v-model="checkname">
        <label for="Jack">Jack</label>
        <input type="checkbox" id="mike" value="mike" v-model="checkname">
        <label for="mike">mike</label>
         <br>
        <span>Checked names: {{ checkname }}</span>
    </div>
  <div class="radio_group">
      <input type="radio" id="male" value="male" v-model="picked">
      <label for="male">male</label>
      <input type="radio" id="famale" value="famale" v-model="picked">
      <label for="famale">famale</label>
      <br>
      <span>Picked: {{ picked }}</span>
  </div>
  <div class="selected_group">
     <select v-model="selected">
        <option disabled value="">请选择</option>
        <option>A</option>
        <option>B</option>
        <option>C</option>
    </select>
  <span>Selected: {{ selected }}</span>
  </div>
  <div class="selected_group1">
     <select v-model="selected1" multiple>
        <option disabled value="">请选择</option>
        <option>A</option>
        <option>B</option>
        <option>C</option>
    </select>
  <span>Selected: {{ selected1 }}</span>
  </div>
  <div class="selected_group2">
     <select v-model="selected2">
        <option v-for="option in options" v-bind:key="option.value" v-bind:value="option.value">
            {{ option.text }}
        </option>
    </select>
  <span>Selected: {{ selected2 }}</span>
  </div>
    <Masai></Masai>
    <Masai></Masai>
    <Masai></Masai>
    <Masai></Masai>
    <Ms v-for="option in options" v-bind:key="option.value" v-bind:value="option.value"></Ms>  
    <Ms title="hellohello"></Ms>  
    <Ms title="hellohellohello"></Ms>  
  </div>
</template>
<script>
import Masai from '@/components/Masai.vue'
import Ms from '@/components/Ms.vue'
export default {
    data : function(){
        return {
            message : "",
            message_textarea :"",
            check : false,
            checkname: [],
            picked: '',
            selected: "",
            selected1 :'',
            options: [
                { text: 'One', value: 'A' },
                { text: 'Two', value: 'B' },
                { text: 'Three', value: 'C'}
            ],
            selected2 : 'A'
        }
    },
    methods :{
    },
    components: {
        Masai,
        Ms,
        
  }
}
</script>