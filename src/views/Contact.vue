<template>
  <div class="contact">
    <h1>Contact Us!</h1>
    <div class="container">
      <div class="contact-container">
        <div class="location">
          <h2>Address</h2>
          <p>
            {{ address1 }}
            <br>
            {{ address2 }}
            <br>
            {{ phoneNumber }}
          </p>
        </div>
        <div class="hour">
          <h2>Hours of Operation</h2>
          <div class="hoursOperation">
            <ul>
              <li v-for="operation in hoursOpperation">{{ operation.day }}: {{ operation.hours }}</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      address1: "1385 Woodroffe Avenue,",
      address2: "Ottawa, Ontario. K2G1V8",
      phoneNumber: "(613)727-423",
      hoursOpperation: [
        { day: "Monday", hours: "9am - 5pm" },
        { day: "Tuesday", hours: "9am - 5pm" },
        { day: "Wednesday", hours: "9am - 5pm" },
        { day: "Thursday", hours: "9am - 5pm" },
        { day: "Friday", hours: "9am - 5pm" },
        { day: "Saturday", hours: "11am - 3pm" },
        { day: "Sunday", hours: "11am - 1pm" }
      ]
    };
  }
};
</script>

<style>
.container {
  padding-left: 0px;
}

.contact {
  max-width: 800px;
  margin: auto;
  text-align: left;
  padding-top: 100px;
}

.contact-container {
  display: flex;
}

h1 {
  padding-right: 100px;
}

h2 {
  padding-bottom: 15px;
}

ul {
  margin: 0;
  padding: 0;
  list-style-type: none;
}

.hoursOperation {
  display: flex;
  justify-content: center;
}

.location {
  padding-right: 90px;
}

.hour {
  padding-left: 90px;
}
</style>
