<template>
   <h2>Create a post now</h2>
  <form @submit.prevent="handleSubmit">
    <label>Title: </label>
    <input type="title" v-model="title"> <!--diri-->
    <label>What's on your mind?: </label>
      <input class = "body" type="body" v-model="body"> <!--diri-->
    <div class = "submit">
      <button @click.prevent="submitTask">Submit Post</button>
    </div>
  </form>
    <p>Title: {{ title }}</p>
    <p>What's on your mind?: {{ body }}</p>

  <form class= "new">
    <h2>- New posts will be posted here -</h2>
    <!--make table diri -->
   <!-- <h3>{{ this.title }}</h3>
    <p>{{ this.body }}</p> -->

    <!-- <table class="table table-bordered">-->
      <div class = "submit">
    <table class="table table-bordered mt-5">
  <thead>
    <tr>
      <th scope="col">Title</th>
      <th scope="col">Message</th>
      <th scope="col" class="text-center">#</th>
      <th scope="col" class="text-center">#</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="(task, index) in tasks" :key ="index">
      <td>{{ task.name }}</td>
      <td>{{ task.status }}</td>
      <td>
        <div class="text-center" @click.prevent="editTask(index)">
          <button>edit</button>
        </div>
      </td>
      <td>
        <div class="text-center" @click="deleteTask(index)">
        <button>delete</button>
        </div>
      </td>
    </tr>
  </tbody>
</table>
</div>
  </form>
</template>

<script>
export default {
  name: 'newsFeed',
  components: {
  },
  data() {
    return {
      title: '',
      body: '',
      // make task and tasks array diri
      task: '',
      editedTask: null,
      tasks: [
        {
          name: 'What is Lorem Ipsum?',
          status: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry.',
        },
        {
          name: 'Where does it come from?',
          status: 'Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.',
        },
      ],
    };
  },
  /*  methods: {
    handleSubmit() {
      console.log('Form Submitted');
      // console.log('title:', this.title);
      // console.log('body:', this.body);
    },
    submitTask() {
      console.log('submitTask function intiated');
    },
  },
  */
  methods: {
    submitTask() {
      if (this.title.length === 0) return;

      if (this.editedTask === null) {
        this.tasks.push({
          name: this.title,
          status: this.body,
        });
      } else {
        this.tasks[this.editedTask].name = this.title;
        this.tasks[this.editedTask].status = this.body;
        this.editedTask = null;
      }
      this.title = '';
      this.body = '';
    },
    deleteTask(index) {
      this.tasks.splice(index, 1);
    },
    editTask(index) {
      this.title = this.tasks[index].name;
      this.body = this.tasks[index].status;
      this.editedTask = index;
    },
  },
};
</script>

<style>
  form {
    max-width: 420px;
    margin: 30px auto;
    background: white;
    text-align: left;
    padding: 40px;
    border-radius: 10px;
  }
.posted {
    max-width: 700px;
    margin: 100px auto;
    background: white;
    text-align: center;
    padding: 40px;
    border-radius: 50px;
    margin-top: 10%;
  }
  label{
    color: #aaa;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
  }
  input{
    display: block;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: non;
    border-bottom: 1px solid #ddd;
    color: #555;
  }
  .body{
    display: block;
    padding: 100px 6px;
    width: 100%;
    box-sizing: border-box;
    border: non;
    border-bottom: 1px solid #ddd;
    color: #555;
  }
  button {
    background: #0b6dff;
    border: 0;
    padding: 10px 20px;
    margin-top: 20px;
    color: white;
    border-radius: 20px;
  }
  .submit {
    text-align: center;
    margin-top: 10%;
    padding: 10px 6px;
  }
  .new {
    max-width: 700px;
    margin: 100px auto;
    background: white;
    text-align: center;
    padding: 40px;
    border-radius: 50px;
    margin-top: 10%;
  }
  tr{
    max-width: 700px;
    margin: 10px 50px 20px;
    background: white;
    text-align: center;
    padding: 40px;
    border-radius: 50px;
    margin-top: 10%;
  }
</style>
