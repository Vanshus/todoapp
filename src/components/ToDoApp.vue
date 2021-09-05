<template>
  <div class="container" >
    <h2 class="text-center mt-5">To Do App</h2>
    

    <!--------------inputs---------------- -->
    <div class="d-flex">
      <input v-model="task" type="text" placeholder="Enter the tast" class="form-control">
      <button @click="submitTask" class="btn btn-warning rounded-0">Submit</button>
    </div>

    <!--  -----------Task Table-----------    -->
    <table class="table table-bordered mt-5">
  <thead>
    <tr>
      <th scope="col">Task</th>
      <th scope="col">Status</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="(task, index) in tasks" :key="index">
      <th>{{task.itemName}}</th>
      <td>{{task.status}}</td>
      
    </tr>
    
  </tbody>
</table>


  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return {
      task: "",
      tasks:[
        {
          itemName: "Apple",
          status: "to-do"
        },
        {
          itemName: "Rice",
          status: "to-do"
        }
        
      ]
    }

  },

  methods: {
    submitTask(){
      if(this.task.length === 0) return;

      this.tasks.push({
        itemName: this.task,
        status: 'to-do'
      })
    }

  }
  
}
</script>
