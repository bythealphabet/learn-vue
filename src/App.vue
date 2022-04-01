<script>
const data = () => ({
  message: "Hello Vue!",
  checkedNames: [],
  bandMembersNames: ["John", "Paul", "George", "Ringo", "Stuart", "wo"],
  tacos: "",
  activeClass: "active",
});

export default { data };
</script>

<template>
  <div>
    <!-- example 1 -->
    <h3>Type here:</h3>
    <textarea v-model="message" class="message" rows="5" maxlength="72" />
    <br />
    <p class="booktext">{{ message }}</p>
    <!-- //////////////////////////////////////////////// -->

    <!-- example 2 -->
    <!-- <input v-model="checkedNames" type="checkbox" id="john" value="John" />
    <label for="john"> John</label>

    <input v-model="checkedNames" type="checkbox" id="paul" value="Paul" />
    <label for="paul"> Paul</label>

    <input v-model="checkedNames" type="checkbox" id="george" value="George" />
    <label for="george"> George</label>

    <input v-model="checkedNames" type="checkbox" id="ringo" value="Ringo" />
    <label for="ringo"> Ringo</label>
    <br />
    <span>Checked names: {{ checkedNames }}</span> -->
    <!-- ////////////////////////////////////////////////////////////////// -->

    <!-- example 3-->

    <span v-for="member in bandMembersNames" :key="member">
      <input
        v-model="checkedNames"
        :id="member"
        :value="member"
        type="checkbox"
      />
      <label for="member.value"> {{ member }}</label>
    </span>

    <br />
    <span>Checked names: {{ checkedNames }}</span>

    <!-- ///////////////////////////////////////////////////////////////////// -->

    <!-- example 4 -->
    <h3>What is your favorite kind of taco? example 4</h3>
    <textarea v-model="tacos"></textarea>
    <br />
    <button v-show="tacos" type="submit">Let us know!</button>
    <button v-if="tacos" type="submit">Let us know!</button>

    <!-- ///////////////////////////////////////////////////////////////////// -->

    <!-- example 5 -->
    <div id="app">
      <h3>What is your favorite kind of taco? example 5</h3>
      <textarea v-model="tacos"></textarea>

      <br />
      <button :class="[tacos ? activeClass : '']">Let us know!</button>
    </div>
    <!-- ///////////////////////////////////////////////////////////////////// -->
    <!-- example 6 -->

    <div id="app">
      <ul>
        <li v-for="num in 5" :key="num">
          {{ num }}
        </li>
      </ul>
    </div>
    <!-- ///////////////////////////////////////////////////////////////////// -->
    <!-- example 7 -->

    <!-- ///////////////////////////////////////////////////////////////////// -->
  </div>
</template>

<style>
button {
  border: none;
  color: white;
  padding: 0.5em 1em;
  border-radius: 3px;
}

button.active {
  background: orangered;
}
</style>
