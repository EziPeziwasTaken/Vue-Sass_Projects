const { createApp } = Vue;

createApp({
    data() {
        return {
            newTask: '',
            tasks: []
        };
    },
    methods: {
        addTask() {
            if (this.newTask.trim() !== '') {
                this.tasks.push({ text: this.newTask, completed: false });
                this.newTask = '';
            }
        },
        removeTask(index) {
            this.tasks.splice(index, 1);
        },
        toggleTask(index) {
            this.tasks[index].completed = !this.tasks[index].completed;
        }
    }
}).mount('#app');