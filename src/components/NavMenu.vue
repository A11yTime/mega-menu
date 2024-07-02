<template>
  <!-- Inaccessible version -->
    <div class="navbar">
   
    <div class="dropdown" v-for="(dropdown, index) in dropdownItems" :key="index">
      <a href="#" @click="toggleMenu" @keydown.enter="toggleMenu(subIndex)">{{ dropdown.name }}</a>
      <div class="dropdown-content" v-if="isVisible">
        <a v-for="(subItem, subIndex) in dropdown.items" :key="subIndex" :href="subItem.url">{{ subItem.name }}</a>
      </div>
    </div>
  </div>
</template>
<script>


export default {
    data() {
        return {
            isVisible: false,
 
      dropdownItems: [
        {
          name: 'Furniture',
          items: [
            { name: 'Item 1.1', url: '#item1.1' },
            { name: 'Item 1.2', url: '#item1.2' },
            { name: 'Item 1.3', url: '#item1.3' }
          ]
        },
        {
          name: 'Outdoor',
          items: [
            { name: 'Item 2.1', url: '#item2.1' },
            { name: 'Item 2.2', url: '#item2.2' },
            { name: 'Item 2.3', url: '#item2.3' }
          ]
         },
         {
          name: 'Bedding',
          items: [
            { name: 'Item 2.1', url: '#item2.1' },
            { name: 'Item 2.2', url: '#item2.2' },
            { name: 'Item 2.3', url: '#item2.3' }
          ]
         },
         {
          name: 'Bath',
          items: [
            { name: 'Item 2.1', url: '#item2.1' },
            { name: 'Item 2.2', url: '#item2.2' },
            { name: 'Item 2.3', url: '#item2.3' }
          ]
         },
         {
          name: 'Lighting',
          items: [
            { name: 'Item 2.1', url: '#item2.1' },
            { name: 'Item 2.2', url: '#item2.2' },
            { name: 'Item 2.3', url: '#item2.3' }
          ]
         },
         {
          name: 'Rugs',
          items: [
            { name: 'Item 2.1', url: '#item2.1' },
            { name: 'Item 2.2', url: '#item2.2' },
            { name: 'Item 2.3', url: '#item2.3' }
          ]
         }
        ]
      }
    },
    methods: {
        toggleMenu(){
            this.isVisible = !this.isVisible
        }
    }

}
</script>
<style scoped>
         .navbar {
      background-color: #333;
      padding: 10px;
      color: #fff;
      display: flex;
      justify-content: space-between;
    }
    .navbar a {
      color: #fff;
      text-decoration: none;
      margin-right: 10px;
    }
    .navbar a:hover {
      color: #ddd;
    }
    .dropdown {
      position: relative;
      display: inline-block;
    }
    .dropdown-content {
      display: none;
      position: absolute;
      background-color: #333;
      min-width: 160px;
      z-index: 1;
    }
    .dropdown-content a {
      color: #fff;
      padding: 12px 16px;
      text-decoration: none;
      display: block;
    }
    .dropdown-content a:hover {
      background-color: #555;
    }
    .dropdown:hover, .dropdown-content {
      display: block;
    }
</style>