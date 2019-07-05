<template>
  <div class="testimonials">
    <!-- Loop Comments -->
    <el-row :gutter="12">
      <el-col :span="12" v-for="(commentList,index) in comments" :key="index">
        <el-card shadow="always">
          <p>
            <strong>{{commentList.Name}} | {{commentList.Position}}</strong>
          </p>
          <p>{{commentList.Comment}}</p>
        </el-card>
      </el-col>
    </el-row>

    <!-- Form Begins Here -->
    <div class="userForm">
      <el-form :model="form" :rules="rules" ref="form">
        <h3>Leave a Testimonial!</h3>
        <el-row>
          <div class="userInfo">
            <el-col :span="12">
              <!--Your Name -->
              <el-form-item prop="yourName">
                <el-input
                  placeholder="Your Name (Max. 50 Words)"
                  id="userName"
                  v-model="form.yourName"
                ></el-input>
              </el-form-item>
            </el-col>
            <el-col :span="12">
              <!-- position Title -->
              <el-form-item prop="position">
                <el-input
                  placeholder="Your Position Title (Max. 50 Words)"
                  id="userPosition"
                  v-model="form.position"
                ></el-input>
              </el-form-item>
            </el-col>
          </div>

          <!-- Your Comments -->
          <el-form-item prop="desc">
            <el-input
              type="textarea"
              placeholder="Your Comments (Max. 120 Words)"
              id="userDesc"
              v-model="form.desc"
            ></el-input>
          </el-form-item>
        </el-row>
      </el-form>

      <!-- Submit button -->
      <el-button type="primary" @click="submitForm('form')">Submit</el-button>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      form: {
        yourName: null,
        position: null,
        desc: null
      },

      comments: [],

      rules: {
        yourName: [
          {
            required: true,
            message: "Type your Name here.",
            trigger: "blur"
          },
          {
            min: 0,
            max: 50,
            message: "50 Word Limit for your Name has been exceeded.",
            trigger: ["blur", "change"]
          }
        ],
        position: [
          {
            required: true,
            message: "Type your Position here.",
            trigger: "blur"
          },
          {
            min: 0,
            max: 50,
            message: "50 Word Limit for your Position has been exceeded.",
            trigger: ["blur", "change"]
          }
        ],
        desc: [
          {
            required: true,
            message: "Type your Comments here.",
            trigger: "blur"
          },
          {
            min: 0,
            max: 120,
            message: "120 Word Limit for your Comments has been exceeded.",
            trigger: ["blur", "change"]
          }
        ]
      }
    };
  },

  methods: {
    submitForm(form) {
      this.$refs[form].validate(valid => {
        if (valid) {
          let obj = {
            Name: this.form.yourName,
            Position: this.form.position,
            Comment: this.form.desc
          };

          // Axios is imported here
          axios
            // POST Request is placed here
            .post(
              "https://midterm-zeid0012.firebaseio.com/data.json ",
              JSON.stringify(obj)
            )
            .then(response => {
              console.log(response);
              console.log("Your data was saved status:" + response.status);

              // GET request is placed here
              axios
                .get("https://midterm-zeid0012.firebaseio.com/data.json")
                .then(response => {
                  // console.log(response);
                  console.log(response.data);
                  // Checking if the response has some data
                  if (response.data) {
                    this.comments = response.data;
                  }
                })
                .catch(error => {
                  console.log(
                    "There was an error in getting data: " + error.response
                  );
                });
            })

            // Error Message is shown here
            .catch(error => {
              console.log(error);
            });

          // Resets the Form here.
          this.$refs[form].resetFields();
        } else {
          console.log("error submit!!");
          return false;
        }
      });
    }
  },

  // Life Cycle Hook runs here.
  created() {
    // GET request using AXIOS to acquire the data.
    axios
      .get("https://midterm-zeid0012.firebaseio.com/data.json")
      .then(response => {
        console.log(response.data);
        // Checks to observe if the Response data here.
        if (response.data) {
          this.comments = response.data;
        }
      })
      .catch(error => {
        console.log("There was an error in getting data: " + error.response);
      });
  }
};
</script>

<style scoped>
.userForm {
  border: 1px solid black;
  padding: 4rem;
  margin: 3rem;
}
.el-row {
  margin-bottom: 1.5rem;
  margin: 3rem;
}

.el-card {
  margin-bottom: 1.5rem;
  background-color: #ffffff;
  margin: 2rem;
}
</style>


