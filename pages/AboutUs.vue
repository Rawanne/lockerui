<template>
  <v-row>
    <v-col class="text-center">
      <div class="hero-image">
        <div class="about-section">
          <h1>About Us</h1>
          <p>We are group M 15 Supervied by Dr.Abeer Almakki</p>
          <p>
            Lockers Management and reservation System will be an efficient solution to facilitate
            managing locker reservations and minimize all the management problems that the student
            affairs employees are facing in every reservation request.
          </p>
        </div>
      </div>
      <h2 class="h1mar" style="text-align: center margin-top: 50px;">Our Team</h2>
      <div class="row h1mar">
        <div class="column">
          <div class="card">
            <div class="container">
              <img src="/AvatarVectorIcons1.png" alt="Esraa" style="width: 50%" />
              <h4>Esraa Shargawi</h4>
              <p class="title">Leader</p>
              <p>Back end Team</p>
              <p>ishargawi@stu.kau.edu.sa</p>
              <p><button class="button">Contact</button></p>
            </div>
          </div>
        </div>

        <div class="column">
          <div class="card">
            <div class="container">
              <img src="/AvatarVectorIcons3.png" alt="Esraa" style="width: 50%" />
              <h4>Rawan Almalki</h4>
              <p class="title">Team member</p>
              <p>Front end Team</p>
              <p>ralmalki0268@stu.kau.edu.sa</p>
              <p><button class="button">Contact</button></p>
            </div>
          </div>
        </div>

        <div class="column">
          <div class="card">
            <div class="container">
              <img src="/AvatarVectorIcon4.png" alt="Esraa" style="width: 50%" />
              <h4>Ghadeer Alghamdi</h4>
              <p class="title">Team member</p>
              <p>Back end Team</p>
              <p>gghamdi0005@stu.kau.edu.sa</p>
              <p><button class="button">Contact</button></p>
            </div>
          </div>
        </div>

        <div class="column">
          <div class="card">
            <div class="container">
              <img src="/AvatarVectorIcons2.png" alt="Esraa" style="width: 50%" />
              <h4>Batool Alnakhbi</h4>
              <p class="title">Team member</p>
              <p>Front end Team</p>
              <p>balnakhbi@stu.kau.edu.sa</p>
              <p><button class="button">Contact</button></p>
            </div>
          </div>
        </div>
      </div>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'AboutUs',
}
</script>
<style scoped>
.column {
  float: left;
  width: 24.5%;
  margin-bottom: 16px;
  padding: 0 8px;
}

.card {
  box-shadow: 0 4px 8px 0 rgba(215, 167, 90, 0.2);
  margin: 8px;
}

.about-section {
  padding: 20px;
  text-align: center;
  color: black;
}
.hero-image {
  background-image: url('/BlobDown.png');
  background-position: center;
  background-color: #f2e3df;
  background-repeat: repeat;
  background-size: cover;
  position: relative;
}

.container {
  padding: 0 16px;
}

.container::after,
.row::after {
  content: '';
  clear: both;
  display: table;
}
.h1mar {
  margin-top: 50px;
}
.title {
  color: grey;
}

.button {
  border: none;
  outline: 0;
  display: inline-block;
  padding: 8px;
  color: white;
  background-color: #de556a;
  text-align: center;
  cursor: pointer;
  width: 100%;
}

.button:hover {
  background-color: #ffccbc;
}

@media screen and (max-width: 650px) {
  .column {
    width: 100%;
    display: block;
  }
}
</style>