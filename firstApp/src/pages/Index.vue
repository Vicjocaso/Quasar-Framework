<template>
  <q-page padding>
    <ul>
      <li v-for="(task,index) in task" :key="task">
        <div>
          {{task.name}} {{ index + 1  }}
        </div>
        <small>{{task.date}} {{task.time}}</small>
        <button @click="deleteTask(index)">X</button>
      </li>
    </ul>
      </q-page>
</template>

<script>
export default {
  data () {
    return {
      task: [
        {
          name: 'Go to shop',
          date: '2020/02/15',
          time: '8:00'
        },
        {
          name: 'Get banana',
          date: '2019/03/28',
          time: '3:00'
        },
        {
          name: 'Feed Rocky',
          date: '2022/04/25',
          time: '7:00'
        }
      ]
    }
  },
  methods: {
    deleteTask (index) {
      this.task.splice(index, 1)
    }
  }
}
</script>
<style>
</style>
