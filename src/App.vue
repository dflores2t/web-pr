<template>
  <nav>
    <div class="mobile">
      <div class="header">
        <div class="logo">logo</div>
        <div class="more">
          <button id="bMore" @click="isCollapsed = !isCollapsed">
            <span class="material-icons">list</span>
          </button>
        </div>
      </div>
      <div :class="{ collapsed: isCollapsed }">
        <a href="#">Services</a>
        <a href="#">About</a>
        <a href="#">Contact</a>
      </div>
    </div>
    <div class="desktop">
      <div class="logo">logo</div>
      <div class="primary">
        <a href="#">Services</a>
        <a href="#">About</a>
        <a href="#">Contact</a>
      </div>
      <div class="secondary full">
        <a href="#">Search</a>
        <a href="#">Sign Up</a>
        <a href="#">Login</a>
      </div>
      <div class="secondary mini">
        <a href="#" class="more">More</a>
        <div class="submenu">
          <a href="#">Search</a>
          <a href="#">Sign Up</a>
          <a href="#">Login</a>
        </div>
      </div>
    </div>
    <!-- <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> -->
  </nav>
  <router-view />
</template>

<script>
export default {
  data() {
    return {
      isCollapsed: true,
    };
  },
  methods: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.material-icons {
  font-family: "Material Icons";
  font-weight: normal;
  font-style: normal;
  font-size: 24px;
  display: inline-block;
  line-height: 1;
  text-transform: none;
  letter-spacing: normal;
  word-wrap: normal;
  white-space: nowrap;
  direction: ltr;
  /* Support for all WebKit browsers. */
  -webkit-font-smoothing: antialiased;
  /* Support for Safari and Chrome. */
  text-rendering: optimizeLegibility;

  /* Support for Firefox. */
  -moz-osx-font-smoothing: grayscale;

  /* Support for IE. */
  font-feature-settings: "liga";
}
.collapsed {
  display: none;
}
nav {
  background-color: black;
  color: white;
  width: 100%;
  /* padding: 30px; */
}
nav .mobile {
  display: none;
}
nav .mobile .header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-left: 10px;
}
nav .mobile .header .more button {
  border: none;
  background-color: black;
  color: white;
  padding: 15px;
  cursor: pointer;
}

nav .logo {
  min-width: 250px;
}

nav a {
  font-weight: bold;
  color: #fafbfc;
  text-decoration: none;
  display: block;
  padding: 20px 25px;
}
nav a:hover {
  color: #42b983;
  backdrop-filter: rgb(0, 195, 255);
}
nav a.router-link-exact-active {
  color: #42b983;
}
nav .desktop {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;
}
nav .desktop .primary,
nav .desktop .secondary {
  display: flex;
}
nav .desktop .secondary.mini {
  display: none;
}
@media screen and (max-width: 853px) {
  nav .logo {
    min-width: 100px;
  }
  nav .secondary.full {
    display: none;
  }
  nav .secondary.mini {
    display: block;
  }
  nav .secondary.mini .submenu {
    background-color: black;
    position: absolute;
    display: none;
    width: 200px;
    right: 0;
  }
  nav .secondary.mini:hover .submenu {
    display: block;
  }
}
@media screen and (max-width: 500px) {
  nav .desktop {
    display: none;
  }
  nav .mobile {
    display: block;
    text-align: center;
  }
}
</style>
