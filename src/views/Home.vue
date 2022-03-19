<template>
  <div id="content">
    <div class="post">
      <h1 class="title">Welcome to Pro Workout</h1>
      <p class="meta"><small>results guaranteed</small></p>
    </div>
    <div id="abt">
      <div class="abText">
        <h2>About us</h2>
        <div class="abImg">
          <img src="../images/runing.jpg" />
        </div>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Lorem ipsum
          dolor sit amet consectetur adipisicing elit Lorem ipsum dolor sit amet
          consectetur adipisicing elit Ipsa minima explicabo cupiditate, error
          perferendis, repudiandae suscipit eaque minus assumenda voluptates
          necessitatibus deserunt! Reprehenderit odit optio aspernatur,
          repudiandae id sunt eaque.
        </p>
      </div>
    </div>
    <div class="exercises">
      <div class="exercise">
        <div class="pic">
          <img src="../images/cardio.jpg" alt="" />
        </div>
        <div class="picDescription">
          <h2>Cardio Fitness</h2>
          <p>Mon,Wed,Fri</p>
          <p>30-60 min</p>
          <p>Home/Gym</p>
          <br />
          <button>Checkout</button>
        </div>
      </div>
      <div class="exercise">
        <div class="pic">
          <img src="../images/masa.jpg" alt="" />
        </div>
        <div class="picDescription">
          <h2>Muscle building</h2>
          <p>Mon,Tue,Fri,Sat</p>
          <p>1-2 hrs</p>
          <p>Gym</p>
          <br />
          <button>Checkout</button>
        </div>
      </div>
      <div class="exercise">
        <div class="pic">
          <img src="../images/definition.jpg" alt="" />
        </div>
        <div class="picDescription">
          <h2>Muscle definition</h2>
          <p>Mon,Wed,Fri,Sat</p>
          <p>60 min</p>
          <p>Home/Gym</p>
          <br />
          <button>Checkout</button>
        </div>
      </div>
    </div>
    <div class="coaches">
      <h1>Our coaches</h1>
      <div class="coachesDiv">
        <div class="coach">
          <div class="coachImg">
            <img src="../images/ProfilePictureMaker.png" alt="" />
          </div>
          <div class="coachDesc">
            <h2>Bogdan</h2>
            <p>
              Lorem ipsum dolor, sit amet consectetur adipisicing elit.
              Inventore consequuntur amet placeat optio soluta maiores, sit quos
              assumenda vel molestiae quis quae accusantium, nisi repellendus
              incidunt earum? Numquam, nihil possimus!
            </p>
          </div>         
        </div>
        <div class="coach">
          <div class="coachImg"><img src="../images/pagi.png" alt="" /></div>
          <div class="coachDesc">
            <h2>Miodrag</h2>
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Eos
              eveniet error nostrum cumque repellat amet incidunt omnis
              explicabo? Vitae quam adipisci dolorem. Explicabo voluptates iusto
              repudiandae necessitatibus, dignissimos harum doloribus!
            </p>
          </div>        
        </div>
        <div class="coach">
          <div class="coachImg"><img src="../images/lazar.png" alt="" /></div>
          <div class="coachDesc"> 
            <h2>Lazar</h2>
            <p>
              Lorem ipsum dolor sit amet consectetur, adipisicing elit.
              Explicabo dolores fugiat illo dolor minus magnam obcaecati omnis a
              illum ipsum, harum at praesentium beatae magni voluptate nesciunt,
              labore totam optio.
            </p>
          </div>         
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { mapState, mapActions } from "vuex";
export default {
  name: "Home",
  components: {},
  computed:{
    ...mapState(["isLoggedIn", "user", "exc", "sid","isAdmin"]),
  }
};
</script>
<style scoped>
#content {
  display: flex;
  flex-direction: column;
  padding: 0 40px;
}

.post {
  display: flex;
  flex-direction: column;
  width: 98%;
}

.post .title {
  margin: 0;
  font-weight: normal;
}

.post h1.title {
  height: 30px;
  font-size: 2.4em;
}

.post .entry {
  padding: 0 10px 30px 15px;
}

.post .meta {
  width: auto;
  margin: 0;
  padding: 5px 0px 0px 15px;
  text-transform: uppercase;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 10px;
  color: #cd9f46;
}

.post .meta a {
  color: #cd9f46;
}

.post .links {
  margin: 0;
}

.post .tags {
  margin: 0;
  text-transform: uppercase;
  font-size: 0.8em;
  font-weight: bold;
}

.post .links a,
.post .tags a {
  border: none;
}

#abt {
  width: 100%;
  margin-top: 30px;
  justify-content: space-between;
  background-color: #f5f5f5;
  background-size: cover;
  text-align: center;
}

.abText {
  padding: 3% !important;
  text-align: justify;
  padding: 5%;
}
.abText p {
  text-align: justify;
  padding: 4%;
}

.abImg img {
  width: 60%;
  padding: 4% 4% 2% 0;
  float: left;
}

.exercises {
  display: flex;
  margin-top: 30px;
  justify-content: space-between;
  background-color: #f5f5f5;
  margin-bottom: 30px;
  width: 100%;
}

.exercise {
  flex-basis: 30% 30%;
  border: 1px solid #857f7f;
  display: flex;
  flex-direction: column;
  width: 30%;
}

.pic img {
  width: 100%;
  background-size: auto;
}

.picDescription {
  margin-top: 10px;
  padding: 10px;
  overflow-wrap: break-word;
}

.picDescription h2 {
  border-bottom: 1px solid #666666;
  padding: 5px;
  color: #666666;
  display: flex;
  flex-direction: column;
}

.picDescription p {
  font-size: 0, 5em;
}

.picDescription button {
  background-color: rgba(51, 51, 51, 0.05);
  border-width: 0;
  color: #333333;
  cursor: pointer;
  display: inline-block;
  font-size: 14px;
  font-weight: 500;
  line-height: 20px;
  list-style: none;
  margin: 0;
  width: auto;
  padding: 10px 12px;
  text-align: center;
  transition: all 200ms;
  vertical-align: baseline;
  white-space: nowrap;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
}

.coacheDesc {
  width: 100% !important;
  min-height: 500px;
}

.coaches {
  margin-bottom: 30px;
  background-color: #f5f5f5;
  display: flex;
  flex-direction: column;
  width: 100%;
}

.coaches h1 {
  font-size: 0, 5em;
}

.coachesDiv {
  display: flex;
  padding: 30px;
  justify-content: space-between;
  text-align: center;
}

.coach {
  width: 100%;
  height: 100%;
  flex-basis: 30% !important;
  display: flex;
  flex-direction: column;
  padding: 5px;
  align-items: center;
}

.coach h2 {
  margin-top: 15px;
}

.coach .coachImg img {
  background-color: #f5f5f5;
  border-radius: 50%;
}

@media screen and (max-width: 1099px) {
  .menu-button {
    display: block;
  }
}

@media screen and (max-width: 740px) {
  .coachesDiv {
    width: 90%;
  }
  .coaches img {
    width: 100%;
  }
}

@media screen and (max-width: 640px) {
  .coachesDiv {
    width: 90% !important;
  }
  .coaches {
    width: 100% !important;
  }
  .coach {
    width: 33%;
  }
  .coaches img {
    width: 100%;
  }
}

@media screen and (max-width: 420px) {
  .coachesDiv {
    width: 70vw !important;
  }
  .coaches img {
    width: 100%;
  }
  .coaches {
    width: 90%;
  }
  .coach {
    width: 30%;
  }
}
</style>