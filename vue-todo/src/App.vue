<script>
import TodoHeader from './TodoHeader.vue'
import TodoList from './TodoList.vue'

export default {
  components: {
    TodoHeader,
    TodoList
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    font-family: Arial, Helvetica, sans-serif;
  }

  body {
    margin: 0;
    font-family: Arial, Helvetica, sans-serif;
    height: 100%;
    width: 100%;
    background-color: white;
  }

  /* Style the top navigation bar */
  .topnav {
    overflow: hidden;
    background-color: #333;
    color: white;
    text-align: center;
  }

  /* Style the topnav links */
  .topnav a {
    float: left;
    display: block;
    color: #f2f2f2;
    text-align: center;
    padding: 14px 16px;
    text-decoration: none;
  }

  /* Change color on hover */
  .topnav a:hover {
    background-color: #ddd;
    color: black;
  }

  /* Style the content */
  .content {
    background-color: #ddd;
    padding: 10px;
    height: 100%;
  }

  /* Style the footer */
  .footer {
    background-color: #f1f1f1;
    padding: 10px;
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    text-align: center;
  }
</style>

<template>
  <body>
    <div class='topnav'>
      <TodoHeader />
    </div>
    <div class='content'>
      <TodoList />
    </div>
    <div class='footer'>
      <p>Things to do.</p>
    </div>
  </body>
</template>
