<template>
  <div>
    <div :key="task.id" v-for="task in tasks">
      <Task
        @reminder-click="$emit('reminder-click', task.id)"
        @delete-task="$emit('delete-task', task.id)"
        :task="task"
      />
    </div>
  </div>
</template>

<script>
import Task from "./Task";

export default {
  name: "Tasks",
  props: {
    tasks: Array,
  },
  components: {
    Task,
  },
  emits: ["delete-task", "reminder-click"],
};
</script>