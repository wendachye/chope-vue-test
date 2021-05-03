<template>
  <div>
    <div class="flexCenter table tableOne" ref="draggableDiv1" @mousedown="(e) =>dragMouseDown(e, 1)">
      <div class="tableText">table 1</div>
    </div>
    <div class="flexCenter table tableTwo" ref="draggableDiv2" @mousedown="(e) =>dragMouseDown(e, 2)">
      <div class="tableText">table 2</div>
    </div>
    <div class="flexCenter table tableThree" ref="draggableDiv3" @mousedown="(e) =>dragMouseDown(e, 3)">
      <div class="tableText">table 3</div>
    </div>
    <div class="flexCenter table tableFour" ref="draggableDiv4" @mousedown="(e) =>dragMouseDown(e, 4)">
      <div class="tableText">table 4</div>
    </div>
    <div class="flexCenter table tableFive" ref="draggableDiv5" @mousedown="(e) =>dragMouseDown(e, 5)">
      <div class="tableText">table 5</div>
    </div>
    <div class="flexCenter table tableSix" ref="draggableDiv6" @mousedown="(e) =>dragMouseDown(e, 6)">
      <div class="tableText">table 6</div>
    </div>
    <div class="horizontalLine" />
    <div class="verticalLine" />
  </div>
</template>

<script>
export default {
  name: 'FloorPlan',
  data: function () {
    return {
      positions: {
        table: null,
        clientX: undefined,
        clientY: undefined,
        movementX: 0,
        movementY: 0
      },
    }
  },
  methods: {
    dragMouseDown: function (event, table) {
      event.preventDefault()

      this.positions.table = table

      // get the mouse cursor position at startup:
      this.positions.clientX = event.clientX
      this.positions.clientY = event.clientY
      document.onmousemove = this.elementDrag
      document.onmouseup = this.closeDragElement  
    },
    elementDrag: function (event) {
      event.preventDefault()

      this.positions.movementX = this.positions.clientX - event.clientX
      this.positions.movementY = this.positions.clientY - event.clientY
      this.positions.clientX = event.clientX
      this.positions.clientY = event.clientY

      // set the element's new position:
      switch(this.positions.table) {
        case 1:
          this.$refs.draggableDiv1.style.top = (this.$refs.draggableDiv1.offsetTop - this.positions.movementY) + 'px'
          this.$refs.draggableDiv1.style.left = (this.$refs.draggableDiv1.offsetLeft - this.positions.movementX) + 'px'
          break;
        case 2:
          this.$refs.draggableDiv2.style.top = (this.$refs.draggableDiv2.offsetTop - this.positions.movementY) + 'px'
          this.$refs.draggableDiv2.style.left = (this.$refs.draggableDiv2.offsetLeft - this.positions.movementX) + 'px'
          break;
        case 3:
          this.$refs.draggableDiv3.style.top = (this.$refs.draggableDiv3.offsetTop - this.positions.movementY) + 'px'
          this.$refs.draggableDiv3.style.left = (this.$refs.draggableDiv3.offsetLeft - this.positions.movementX) + 'px'
          break;
        case 4:
          this.$refs.draggableDiv4.style.top = (this.$refs.draggableDiv4.offsetTop - this.positions.movementY) + 'px'
          this.$refs.draggableDiv4.style.left = (this.$refs.draggableDiv4.offsetLeft - this.positions.movementX) + 'px'
          break;
        case 5:
          this.$refs.draggableDiv5.style.top = (this.$refs.draggableDiv5.offsetTop - this.positions.movementY) + 'px'
          this.$refs.draggableDiv5.style.left = (this.$refs.draggableDiv5.offsetLeft - this.positions.movementX) + 'px'
          break;
        case 6:
          this.$refs.draggableDiv6.style.top = (this.$refs.draggableDiv6.offsetTop - this.positions.movementY) + 'px'
          this.$refs.draggableDiv6.style.left = (this.$refs.draggableDiv6.offsetLeft - this.positions.movementX) + 'px'
          break;
        default: 
          break;
      }
    },
    closeDragElement () {
      document.onmouseup = null
      document.onmousemove = null
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.flexCenter {
  display: flex;
  justify-content: center;
  align-items: center;
}
.tableText {
  font-size: 12px;
  color: white;
}
.table {
  position: absolute;
  border-width: 1px;
  border-style: solid;
  border-color: black;
  cursor: pointer;
  background-color: #a17e58;
}
.tableOne {
  width: 60px;
  height: 60px;
  left: 76px;
  top: 36px;
}
.tableTwo {
  width: 60px;
  height: 60px;
  left: 173px;
  top: 36px;
}
.tableThree {
  width: 300px;
  height: 60px;
  left: 278px;
  top: 36px;
}
.tableFour {
  width: 60px;
  height: 60px;
  left: 82px;
  top: 210px;
}
.tableFive {
  width: 60px;
  height: 60px;
  left: 180px;
  top: 210px;
}
.tableSix {
  width: 200px;
  height: 100px;
  left: 353px;
  top: 190px;
}
.horizontalLine {
  width: 300px;
  height: 2px;
  position: absolute;
  left: 144px;
  top: 139px;
  background-color: black;
}
.verticalLine {
  width: 2px;
  height: 100px;
  position: absolute;
  left: 295px;
  top: 194px;
  background-color: black;
}
</style>
