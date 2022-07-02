<template>
    <form class="form" @submit.prevent>
            <div class="form__group">
                <label for="title" class="points">Наименование товара</label>
                <input 
                    type="text" 
                    id="title" 
                    placeholder="Введите наименование товара"
                    v-bind:value="title"
                    @input="title = $event.target.value"
                >
            </div>

            <div class="form__group">
                <label for="description">Описание товара</label>
                <textarea
                    id="description"
                    placeholder="Введите описание товара"
                    v-bind:value="description"
                    @input="description = $event.target.value"
                ></textarea>
            </div>

            <div class="form__group">
                <label for="img-link" class="points">Ссылка на изобржаение товара</label>
                <input 
                    type="img-link" 
                    id="img-link" 
                    placeholder="Введите ссылку"
                    v-bind:value="image"
                    @input="image = $event.target.value"
                >
            </div>

            <div class="form__group">
                <label for="price" class="points">Цена товара</label>
                <input 
                    type="text" 
                    id="price" 
                    placeholder="Введите цену"
                    v-bind:value="price"
                    @input="price = $event.target.value"
                >
            </div>

            <button class="add-btn" @click="addToList">
                Добавить товар 
            </button>
          </form>
</template>


<style lang="scss" scoped>
.form {
        background: #FFFEFB;
        box-shadow: 0 20px 30px rgba(0, 0, 0, 0.04), 0 6px 10px rgba(0, 0, 0, 0.02);
        border-radius: 4px;
        padding: 24px;
        position: sticky;
        top: 24px;
        &__group {
            margin-bottom: 16px;
        }
        label {
            margin-bottom: 4px;
            display: inline-block;
            position: relative;  
        }
        .points::after {
            content: '';
            position: absolute;
            top: 0;
            right: -4px;
            display: block;
            width: 4px;
            height: 4px;
            border-radius: 50%;
            background-color: #FF8484;
        }
        input, textarea {
            color: #3F3F3F;
            padding: 10px 16px;
            width: 90%;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            border-radius: 4px;
            border: none;
            resize: none;
            font-style: normal;
            font-weight: 400;
            font-size: 12px;
            line-height: 15px;
        }
        textarea {
             height: 100px;
        }
        .add-btn {
            margin-top: 24px;
            width: 100%;
            background-color: #7BAE73;
            border-radius: 10px;
            border: none;
            padding: 10px 0;
            color: white;
            font-weight: 600;
            cursor: pointer;
            transition: background-color ease .4s;
        } 
    }
    input:focus {
        color: #7BAE73;
    }
</style>