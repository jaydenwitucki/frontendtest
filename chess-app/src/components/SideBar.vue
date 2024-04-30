<template>
    <div id="sidebar">
      <ul class="selected">
        <div class="row">
          <li v-bind:key="selectedSquare" v-for="selectedSquare of selectedSquares">{{ selectedSquare }}</li>
        </div>
      </ul>
    </div>
</template>

<script>
export default {
  name: "SideBar",
  props: {
    selectedSquares: { type: Array }
  }
};
</script>

<style>
#sidebar {
  height: calc(100vh - 40px);
  width: 35vw;
  max-width: 400px;
  margin:10px;
  background-color: #36454F;
  overflow: scroll;
  border-radius: 3px;
  font-weight: bold;
  flood-color: rgb(5, 0, 0);
}

.selected {
  color: #050505;
  list-style-type: none;
  display: contents;
}

.row {
  display: flex;
  justify-content: flex-start;
  align-items: flex-start;
  flex-wrap: wrap;
  width: 100%;
  padding: 10px 5px 10px 5px;
}

li {
  flex: 0 1 calc(30% - 5px)
}

@media only screen and (min-width: 320px) and (max-width: 600px) {
  #sidebar {
    height: 25vh; 
    width: 95vw; /* Full width for better use of space on small screens */
    max-width: 95vw;
    overflow-y: scroll; /* 'auto' only shows scrollbar when needed */
    overflow-x:hidden;
  }

  .row {
    width: calc(95vw - 30px)
  }

  li {
    flex-basis: 15%; 
    font-size: 12px; 
    padding: 5px;
  }
}

@media only screen and (min-width: 600px) and (max-width: 1024px) {
  li {
    flex-basis: 30%; /* Increase number of items per row on larger screens */
  }
}
</style>

