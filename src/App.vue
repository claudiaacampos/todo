<template>
  <nav>
    <router-link to="/">Options API</router-link> |
    <router-link to="/composition">Composition API</router-link>
  </nav>
  <router-view />
</template>

<style>
html,
body {
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
  gap: 3rem;
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

.todo-container {
  display: flex;
  gap: 4rem;
  padding: 2rem;
  border-top: thin solid #cccccc;
  border-bottom: thin solid #cccccc;
  box-shadow: 0px 5px 15px -15px;
}

.logo-container {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
  width: 40%;
}

.logo {
  width: 30%;
  margin: 0 auto;
}

h1 {
  font-size: 2rem;
  margin: 0;
}

.todo-add-bar {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  position: relative;
}

input {
  border: 1px solid #42b883;
  border-radius: 40px;
  padding: 0 9.5rem 0 2rem;
  height: 60px;
  align-items: center;
  justify-content: flex-end;
  margin: 0 auto;
  max-width: 100%;
  flex-grow: 2;
  position: relative;
  box-sizing: border-box;
  outline: 0;
  font-size: 1rem;
}

input::placeholder {
  font-size: 1.125rem;
  line-height: 1.4rem;
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
  color: #ffffff;
  font-size: 1.75rem;
  font-weight: 600;
  text-transform: uppercase;
  z-index: 1;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  right: 0;
  gap: 0.75rem;
  height: 60px;
  width: 20%;
}

.add-btn:hover {
  background-color: #2c3e50;
  color: #ffffff;
}

.todo-add-container {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  width: 50%;
}

h2 {
  margin: 0;
}

.list-container {
  display: flex;
  flex-direction: column;
  padding: 3rem 3rem 6rem;
  gap: 2rem;
}

ul {
  display: grid;
  grid-template-columns: auto auto;
  gap: 1.5rem;
  list-style: none;
  padding: 0;
  margin: 0;
}

li {
  display: flex;
  align-items: center;
  justify-content: space-between;
  border: none;
  text-transform: capitalize;
  font-size: 1.5rem;
  gap: 2rem;
  min-width: 100%;
}

li span {
  font-size: 1.75rem;
  line-height: 0.75rem;
  font-weight: bolder;
  color: #42b883;
  margin: 0 0.5rem 0 0;
}

.remove-btn {
  background-color: #ffffff;
  fill: #42b883;
  border: 0;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  width: 2rem;
  height: 2rem;
}
.remove-btn:hover {
  transform: scale(1.3);
  fill: #42b883;
}

.send-list {
  display: flex;
  align-content: center;
}
.send-form {
  display: flex;
  align-items: center;
}
.send-btn {
  background-color: #42b883;
  outline: none;
  border: 0;
  min-height: 60px;
}
</style>
