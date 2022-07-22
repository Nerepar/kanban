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
                addFormVisible: false
            }
        },
        methods: {
            addTask(taskData) {
              this.boards[0].tasks.push(taskData)
            },
            closeCard() {
                this.addFormVisible = false
            },
            addButtonClick() {
                this.addFormVisible = true
            },
        }
    }
</script>

<style scoped src="./Style.less" lang="less">

</style>