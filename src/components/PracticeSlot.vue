<template>
  <div class="header">
    <slot name="header"></slot>
  </div>
  <div class="body">
    <h1>Tile</h1>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Facere voluptate ad, similique illo vitae suscipit saepe aut esse quas earum labore voluptatibus quis cupiditate, doloremque laudantium? Animi temporibus corporis placeat!</p>
    <slot></slot>
  </div>
  <div class="footer">
    <slot name="footer"></slot>
  </div>
</template>