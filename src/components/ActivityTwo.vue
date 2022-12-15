<script setup>

</script>

<template>
  <div>Calculator</div>
 
    <div class="app">
      
      <div class="display">
        <div class="content">
          <div class="input"></div>
          <div class="output"></div>
        </div>
      </div>

    </div>
    <div class="keys">
      <div data-key="clear" class="key action">
        <span>AC</span>
      </div>

      <div data-key="+-" class="key action">
        <span>+/-</span>
      </div>

      <div data-key="%" class="key action">
        <span>%</span>
      </div>

      <div data-key="/" class="key operator">
        <span>/</span>
      </div>

      <div data-key="7" class="key">
        <span>7</span>
      </div>

      <div data-key="8" class="key">
        <span>8</span>
      </div>

      <div data-key="9" class="key">
        <span>9</span>
      </div>

      <div data-key="*" class="key operator">
        <span>&#215;</span>
      </div>

      <div data-key="4" class="key">
        <span>4</span>
      </div>

      <div data-key="5" class="key">
        <span>5</span>
      </div>

      <div data-key="6" class="key">
        <span>6</span>
      </div>

      <div data-key="-" class="key operator">
        <span>-</span>
      </div>

      <div data-key="1" class="key">
        <span>1</span>
      </div>

      <div data-key="2" class="key">
        <span>2</span>
      </div>

      <div data-key="3" class="key">
        <span>3</span>
      </div>

      <div data-key="+" class="key operator">
        <span>+</span>
      </div>

      <div data-key="backspace" class="key">
        <span>&#8634;</span>
      </div>

      <div data-key="0" class="key">
        <span>0</span>
      </div>

      <div data-key="." class="key">
        <span>.</span>
      </div>

      <div data-key="=" class="key operator">
        <span>=</span>
      </div>

    </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: sans-serif;
}
.app {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.calculator {
  background-color: whitesmoke;
  width: 100%;
  max-width: 375px;
  min-height: 640px;
  display: flex;
}
.display{
  min-height: 200px;
  padding: 1.5rem;
  display: flex;
  justify-content: flex-end;
  align-items: flex-end;
  color: black;
  text-align: right;
  flex: 1 1 0%;
}
.display .content {
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  width: 100%;
  max-width: 100%;
  overflow: auto;
}
display .input {
  width: 100%;
  font-size: 1.25rem;
  margin-bottom: 0.5rem;
}
.display .operator {
  color: #EB6666;
}
.display .brackets
.display .percent {
  color: #26FED7;
}
.keys {
  background-color: white;
  padding: 1.5rem;
  border-radius: 1.5rem 1.5rem 0 0;
  display: grid;
  grid-template-columns: repeat(4,1fr);
  grid-template-rows: repeat(5,1fr);
  grid-gap: 1rem;
  box-shadow: 0px -2px 16px rgba(0,0,0,0.2)
}
.keys .key {
  position: relative;
  cursor: pointer;
  display: block;
  height: 0;
  padding-top: 100%;
  background-color: whitesmoke;
  border-radius: 1rem;
  transition: 0.2s;
  user-select: none;
}
.keys key span {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 2rem;
  font-weight: 700;
  color: black;
}

.keys .key:hover {
  box-shadow: inset 0px 0px 8px rgba(0,0,0,0.2);
}
.keys .key.operator span {
  color: #EB6666;
}
.keys .key.action span {
  color: #26FED7;
}
</style>