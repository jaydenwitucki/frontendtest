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
  max-width: 450px;
  margin-top: 25px;
  margin-bottom: 25px;
  margin-left: 10px;
  margin-right: 10px;
  background-color: #36454F;
  overflow: scroll;
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
  padding: 10px
}

li {
  flex-basis: 50px;
}

@media only screen and (max-width: 600px) {
  #sidebar {
    height: 25vh; /* Small change to height for a better aspect ratio */
    width: 95vw; /* Full width for better use of space on small screens */
    max-width: 95vw;
    overflow-y: scroll; /* 'auto' only shows scrollbar when needed */
    overflow-x:hidden;
  }

  .row {
    width: calc(95vw - 20px)
  }

  li {
    flex-basis: 15%; 
    font-size: 12px; 
    padding: 5px;
  }
}

@media only screen and (min-width: 601px) and (max-width: 1024px) {
  li {
    flex-basis: 25%; /* Increase number of items per row on larger screens */
    font-size: 20px; /* Larger font size for tablets and small desktops */
  }
}
</style>