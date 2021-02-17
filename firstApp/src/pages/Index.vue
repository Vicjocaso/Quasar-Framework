<template>
  <q-page padding>
    <ul>
      <task v-for="(task, index) in task" :key="task.id" :task="task" :index="index">{{task.name}}</task>
    </ul>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      task: [
        {
          id: '1',
          name: 'Go to shop',
          date: '2020/02/15',
          time: '8:00'
        },
        {
          id: '2',
          name: 'Get banana',
          date: '2019/03/28',
          time: '3:00'
        },
        {
          id: '3',
          name: 'Feed Rocky',
          date: '2022/04/25',
          time: '7:00'
        }
      ]
    }
  },

  components: {
    task: require('components/Task.vue').default
  }
}
</script>
<style>

</style>
