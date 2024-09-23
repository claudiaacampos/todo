<template>
  <nav>
    <router-link to="/">Options API</router-link> |
    <router-link to="/composition">Composition API</router-link>
  </nav>
  <router-view />
</template>

<style>
html, body {
  margin: 0;
  padding: 0;
} 

p {
  margin: 0;
}

#app {
  font-family: "Roboto", sans-serif;
  font-size: 1.125rem;
  line-height: 1.4;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  gap: 2rem;
  margin: 0;
  padding: 0;
}

nav {
  padding: 30px;
  max-width: 100%;
  margin: 0;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  padding: 1rem;
}

nav a.router-link-exact-active {
  color: #42b883;
}

.container {
  display: flex;
  gap: 3rem;
  padding: 2rem;
}

.add-container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 1;
  max-width: 50%;
  max-height: min-content;
}

.logo {
  height: 30%;
  width: 30%;
  margin: 0 auto;
}

h1 {
  font-size: 2rem;
  margin: 0;
}

.todo-bar {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  position: relative;
}

input {
  border: 1px solid #42b883;
  /* border-right: 0;
  border-top-left-radius: 40px;
  border-bottom-left-radius: 40px; */
  border-radius: 40px;
  padding: 0 13.5rem 0 2.5rem;
  height: 65px;
  align-items: center;
  margin: 0 auto;
  max-width: 100%;
  height: 85px;
  flex-grow: 2;
  position: relative;
  box-sizing: border-box;
  outline: 0;
  font-size: 1.75rem;
}
input::placeholder {
  font-size: 1.75rem;
  line-height: 1.4;
}

input:hover {
  border: 2px solid #42b883;
  border-right: 0;
}

.add-btn {
  border-top-right-radius: 40px;
  border-bottom-right-radius: 40px;
  border: 1px solid #42b883; 
  background-color: #42b883;
  color: #FFFFFF;
  z-index: 1;
  padding: 0.5rem 2rem;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 85px;
  
  position: absolute;
  right: 0;
  font-size: 1.75rem;
  font-weight: 600;
  text-transform: uppercase;
  gap: 0.75rem;
  width: 40%;
}

.add-btn:hover {
  background-color: #2c3e50;
  color: #FFFFFF;
}

.list-container {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  padding: 2rem;
  max-width: 40%;
}

h2 {
  margin: 0;
}

ul {
  display: flex;
  flex-direction: column;
  gap: 1.1rem;
  list-style: none;
  padding: 0;
  margin: 20px 0 0;
}

li {
  display: flex;
  align-items: center;
  justify-content: space-between;
  border: none;
  max-width: 50%; 
}

li span {
  font-size: 1.75rem;
  text-transform: capitalize;
}
.btn-remove {
  border: 0;
  outline: 0;
  background-color: transparent;
}
.remove-btn {
  background-color: #FFFFFF;
  fill: #CCCCCC;
  border: 0;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  width: 2.3rem;
  height: 2.3rem;
}
.remove-btn:hover {
  transform: scale(1.3);
  fill: #42b883;
}
</style>
