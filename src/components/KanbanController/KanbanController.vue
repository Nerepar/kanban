<template src="./template.html">

</template>

<script>

    import KanbanBoard from "@/components/KanbanBoard/KanbanBoard";
    import KanbanAddForm from "@/components/KanbanAddForm/KanbanAddForm";

    export default {
        name: "KanbanController",
        components: {
            KanbanBoard, KanbanAddForm
        },
        data() {
            return {
                boards: [
                    {
                        title: 'В ожидании',
                        background: '#b85353',
                        cardBackground: '#ffffff',
                        tasks: []
                    },

                    {
                        title: 'В работе',
                        background: '#4e64c9',
                        cardBackground: '#ffffff',
                        tasks: []
                    },

                    {
                        title: 'Тестирование',
                        background: '#2e7d39',
                        cardBackground: '#ffffff',
                        tasks: []
                    },
                    {
                        title: 'Выполненные',
                        background: '#de3c9c',
                        cardBackground: '#fffcfd',
                        tasks: []
                    },
                ],
                addFormVisible: false,
                indexTask: 0
            }
        },
        methods: {
            addTask(taskData) {
                this.indexTask++;
                this.boards[0].tasks.push(taskData)
            },
            closeCard() {
                this.addFormVisible = false
            },
            addButtonClick() {
                this.addFormVisible = true
            },
            deleteTask(taskId, boardId) {
                const tasks = this.boards[boardId].tasks;
                const newTasks = [];
                tasks.forEach((item) => {
                    if (item.id !== taskId) {
                        newTasks.push(item);
                    }
                });
                this.boards[boardId].tasks = newTasks;

            },
            moveNextBoard() {

            },
            movePrevBoard() {

            }
        }
    }
</script>

<style scoped src="./Style.less" lang="less">

</style>