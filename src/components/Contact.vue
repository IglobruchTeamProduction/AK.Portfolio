<template>
    <div class="skills">
        <div class="header">
            <h2 class="ski"><i class="bi bi-browser-chrome"></i> Contact <i class="bi bi-browser-chrome"></i></h2>
        </div>
        <div class="grid">
            <ul class="info">
                <li><a href="https://discordapp.com/users/foxeckck#8670">Discord</a></li>
                <li><a href="https://t.me/Fufkaxs">Telegram</a></li>
                <li><a href="mailto:vufka33@gmail.com">vufka33@gmail.com</a></li>
                <li><a href="tel:+49151520495185">+49151520495185</a></li>
            </ul>
            <form class="form" @submit.prevent="sendMessage">
                <h3>Feel free to contact me</h3>
                <input type="text" v-model="telegramm" placeholder="Enter your Telegram username, for example '@name'">
                <textarea v-model="message" placeholder="Write your question..." id="message"></textarea>
                <button type="submit">Send</button>
            </form>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            telegramm: "",
            message: "",
        };
    },
    methods: {
        sendMessage() {
            const chatId = "5084794202"; // Замените на свой chat_id
            const url = "https://api.telegram.org/bot6449439101:AAHgmB9NycU_eziy4NpuI0wsMmNH6uUyvnM/sendMessage"

            const regex = /^@[a-zA-Z0-9_]+$/;
            if (!regex.test(this.telegramm)) {
                alert("Введите телеграмм ник")
                return
            }

            if (this.message) {
                // Формируем тело запроса
                const formData = new FormData();
                formData.append("chat_id", chatId);
                formData.append("text", this.telegramm + ": " + this.message);

                // Отправляем POST запрос к API Telegram Bot
                fetch(url, {
                    method: "POST",
                    body: formData,
                })
                    .then(response => response.json())
                    .then(data => {
                        console.log("Ответ от Telegram API:", data);
                        // Обработка ответа, если необходимо
                    })
                    .catch(error => {
                        console.error("Ошибка при отправке сообщения:", error);
                        // Обработка ошибки, если необходимо
                    });
                this.message = ""
            }


        },
    },
};
</script>

<style scoped lang="scss">
.skills {
    border: 2px solid var(--color-font);
    border-radius: 20px;
    margin-top: 50px;
    margin-bottom: 50px;
    color: var(--color-font);
}

.header {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    border-bottom: 2px solid var(--color-font);
}

.item img {
    width: 80px;
    height: 80px;
    object-fit: contain;
    object-position: center;
}

.item p {
    text-align: center;
    margin: 0;
}

.items {
    /* display: grid;
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    gap: 45px; */
    display: flex;
    align-items: center;
    justify-content: space-around;
    flex-wrap: wrap;
}

.item {
    min-width: 150px;
    display: flex;
    text-align: center;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    margin: 20px 0 10px 0;
}

.grid {
    display: grid;
    grid-template-columns: 1fr 2fr;

    @media (max-width: 510px) {
        grid-template-columns: 1fr;
        padding-bottom: 20px;
    }
}

.form {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    border-left: 2px solid var(--color-font);

    @media (max-width: 510px) {
        border-left: none;
        order: -1;
    }
}

.form textarea {
    width: 80%;
    height: 120px;
    background-color: rgb(255, 255, 255);
    border: 2px solid black;
    padding: 10px;
    border-radius: 10px;
}

.form input {
    width: 80%;
    background-color: rgb(255, 255, 255);
    border: 2px solid black;
    padding: 10px;
    border-radius: 10px;
}

.form button {
    border: 2px solid var(--color-font);
    color: var(--color-font);
    padding: 5px 35px;
    margin-bottom: 20px;
    border-radius: 5px;
    background-color: rgba(0, 0, 0, 0);
    margin-top: 10px;
    transition: 0.5s ease-out;
    cursor: pointer;
}
.form button:hover {
    padding: 5px 50px;
    transition: 0.5s ease-out;
}
.info {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    gap: 15px;
    padding: 0;
    margin: 0 10px;
    color: var(--color-font);

}

.info a{
    color: var(--color-font);
}

.info li {
    list-style: none;
    text-align: center;
    border: 2px solid var(--color-font);
    border-radius: 20px;
    padding: 10px 25px;
    width: 100%;
    box-sizing: border-box;


}
</style>

