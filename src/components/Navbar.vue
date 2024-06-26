<template>
    <nav class="navbar">
      <div class="brand">
        <span>Daftar List</span>
      </div>
      <ul class="nav-links">
        <li @click="navigate('home')" :class="{ active: currentPage === 'home' }">Home</li>
        <li @click="navigate('about')" :class="{ active: currentPage === 'about' }">About</li>
      </ul>
    </nav>
  </template>
  
  <script>
  export default {
    name: 'Navbar',
    props: {
      currentPage: String,
      navigate: Function,
    },
  };
  </script>
  
  <style scoped>
  .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: rgba(51, 51, 51, 0.74);
    color: white;
    padding: 10px 20px;
  }
  
  .brand {
    font-size: 1.5rem;
  }
  
  .nav-links {
    list-style-type: none;
    display: flex;
    gap: 20px;
  }
  
  .nav-links li {
    cursor: pointer;
  }
  
  .nav-links li.active {
    text-decoration: underline;
  }
  </style>
  