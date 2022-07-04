<template>
  <div class="container">
    <Header title="Task Tracker" />
    <AddTask />
    <Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks"/>
  </div>
</template>

<script>
import Header from './components/Header'
import Tasks from './components/Tasks'
import AddTask from './components/AddTask'

export default {
  name: "App",
  components: {
    Header,
    Tasks,
    AddTask,
  },
  methods: {
    deleteTask(id) {
      if(confirm('Are you sure you want to remove this task?')) {
      this.tasks = this.tasks.filter((task) => task.id !== id)
    }
    },
    toggleReminder(id) {
      this.tasks = this.tasks.map((task) => task.id === id ? {...task , reminder: !task.reminder} : task)
    }
  },

  data() {
    return {
      tasks: [],
    }
  },
  created() {
      this.tasks = [
        {
          id:1,
          text: "Dentist Appointment",
          day: "March 1st at 2:30pm",
          reminder: true,
        },
         {
          id:2,
          text: "Shopping",
          day: "March 5th at 4:00pm",
          reminder: true,
        },
         {
          id:3,
          text: "Meeting at School",
          day: "March 13th at 9:30am",
          reminder: false,
        }
      ]
    }
};
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Poppins', sans-serif;
  background-color: rgba(90, 21, 193, .7);
}

.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 2px solid ;
  padding: 30px;
  border-radius: 10px;
}

.btn {
  display: inline-block;
  background: rgba(21, 193, 98, 0.8);
  color: #fff;
  border: none;
  padding: 5px 10px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}

.btn:focus {
  outline: none;
}

.btn:active {
  transform: scale(0.98);
}

.btn-block {
  display: block;
  width: 100%;
}

</style>

