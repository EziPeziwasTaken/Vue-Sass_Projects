const { createApp } = Vue;

        createApp({
            data() {
                return {
                    newFood: '',
                    newCalories: '',
                    foods: []
                };
            },
            computed: {
                totalCalories() {
                    return this.foods.reduce((sum, food) => sum + food.calories, 0);
                }
            },
            methods: {
                addFood() {
                    if (this.newFood.trim() !== '' && this.newCalories > 0) {
                        this.foods.push({ name: this.newFood, calories: this.newCalories });
                        this.newFood = '';
                        this.newCalories = '';
                    }
                },
                removeFood(index) {
                    this.foods.splice(index, 1);
                }
            }
        }).mount('#app');