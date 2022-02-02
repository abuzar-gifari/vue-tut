<template>
<!--  <slot>Default value</slot> &lt;!&ndash; without passing html data &ndash;&gt;-->
<div class="card">
  <header>
    <slot name="header">Default header</slot>
  </header>
  <main>
    <slot name="main">Default main</slot>
  </main>
  <footer>
    <slot name="footer">Default footer</slot>
  </footer>
</div>

</template>

<script>
export default {
  name:"Child"
}
</script>

<style>
.card{
  border: 1px solid;
  width:130px;
  padding: 20px;
  margin: 20px;
  text-align: center;

}
</style>
