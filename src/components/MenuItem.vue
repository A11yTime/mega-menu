<template>
  <!-- Accessible version -->
  <div class="navbar">
    <div class="dropdown" v-for="(dropdown, index) in dropdownItems" :key="index">
      <a href="#" @click.prevent="toggleMenu(index)" @keydown.enter.prevent="toggleMenu(index)" :aria-expanded="visibleDropdown === index ">{{ dropdown.name }}</a>
      <div class="dropdown-content" v-if="visibleDropdown === index">
        <a v-for="(subItem, subIndex) in dropdown.items" :key="subIndex" :href="subItem.url">{{ subItem.name }}</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      visibleDropdown: null, // Track the visible dropdown index
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
    };
  },
  methods: {
    toggleMenu(index) {
      console.log('Toggling menu at index:', index);
      if (this.visibleDropdown === index) {
        this.visibleDropdown = null; // Close the dropdown if it's already open
        console.log('Closing dropdown, current visibleDropdown:', this.visibleDropdown);
      } else {
        this.visibleDropdown = index; // Open the clicked dropdown
        console.log('Opening dropdown, current visibleDropdown:', this.visibleDropdown);
      }
    }
  }
};
</script>

<style scoped>
.navbar {
  background-color: #333;
  padding: 1rem;
  color: #fff;
  display: flex;
  justify-content: space-between;
}
.navbar a {
  color: #fff;
  text-decoration: none;
  margin-right: 1rem;
  cursor: pointer;
}
.navbar a:hover {
  color: #ddd;
}
.dropdown {
  position: relative;
  display: inline-block;
  
}
.dropdown-content {
  margin-top: .66rem;
  position: absolute;
  background-color: #333;
  z-index: 1;
  margin-left: -.8rem;
}
.dropdown-content a {
 
  color: #fff;
  padding: 1rem 1rem;
  text-decoration: none;
  display: block;
}
.dropdown-content a:hover {
  background-color: #555;
}
.dropdown-content[style] {
  display: block;
}
</style>
