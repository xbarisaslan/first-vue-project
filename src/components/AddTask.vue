<template>
    <form class="add-form">
      <div class="form-control">
        <label>Task</label>
        <input type="text" name="text" placeholder="Add Task" v-model="task"/>
      </div>
      <div class="form-control">
        <label>Day & Time</label>
        <input type="text" name="day" placeholder="Add Day & Time" v-model="day" />
      </div>
      <div class="form-control form-control-check">
        <label>Set Reminder</label>
        <input id="checkbox" type="checkbox" name="reminder" v-model="reminder" />
      </div>

      <input class="btn btn-block" type="submit" value="Save Task" />
    </form>
</template>

<script>
 export default {
    name: "AddTask",
    data() {
        return {
            text: '',
            day:'',
            reminder: false,
        }
    }
 }
</script>

<style scoped>
.add-form {
    margin-bottom:40px;
}

.form-control {
    margin: 20px 0;
}

.form-control label {
    display:block;
}

.form-control input {
    width: 100%;
    height: 40px;
    margin: 5px;
    padding: 5px 8px;
    font-size: 17px;
}

.form-control-check {
   display:flex;
   align-items: center ;
}

#checkbox {
    width:20px;
    margin-left: 15px;
}

</style>