<template>
    <div class="nav">
        <div class="namber">
            +49151520495185
        </div>
        <div class="tx">
            <h1>Portfolio</h1>
        </div>
        <ul class="links">
            <li class="number"><a href="tel:+49151520495185"><i class="bi bi-telephone-fill"></i></a></li>
            <li class="discord"><a href="https://discordapp.com/users/foxeckck#8670"><i class="bi bi-discord"></i></a></li>
            <li class="telegram"><a href="https://t.me/Fufkaxs"><i class="bi bi-telegram"></i></a></li>
        </ul>
        <div class="open">
            <button @click="changeTheme()" class="btn">
                <i v-if="theme === 'light'" class="bi bi-moon-stars-fill"></i>
                <i v-else class="bi bi-brightness-high-fill"></i>
            </button>
        </div>
    </div>
</template>


<script setup>
import { ref } from 'vue';
const theme = ref("dark")
function startTheme() {
    const dataTheme = localStorage.getItem("theme")
    if (!dataTheme) {
        localStorage.setItem("theme", "dark")
        document.documentElement.setAttribute('data-theme', 'dark');
        theme.value = "dark"
    }
    else {
        document.documentElement.setAttribute('data-theme', dataTheme);
        theme.value = dataTheme
    }
}

startTheme()

function changeTheme() {
    const dataTheme = localStorage.getItem("theme")
    if (dataTheme === "dark") {
        localStorage.setItem("theme", "light")
        document.documentElement.setAttribute('data-theme', 'light');
        theme.value = "light"
    }
    else {
        localStorage.setItem("theme", "dark")
        document.documentElement.setAttribute('data-theme', 'dark');
        theme.value = "dark"
    }
}

</script>


<style scoped lang="scss">
.nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    border: 2px solid black;
    position: relative;
    padding: 0 5px;
    background: rgb(147, 142, 142);
    background: radial-gradient(circle, rgba(147, 142, 142, 1) 0%, rgba(87, 79, 79, 1) 58%, rgba(91, 84, 84, 1) 100%);

}

.bi-telegram{
    color: rgb(67, 67, 248);
}
.bi-discord{
    color: rgb(97, 13, 175);
}
.bi-telephone-fill{
    color:rgb(49, 49, 209)
}

.bi-moon-stars-fill {
    color: white;
}
.bi-brightness-high-fill{
    color: rgb(253, 253, 17);
}

.links {
    display: flex;
    gap: 20px;
    list-style: none;
    margin: 5px;
    padding: 0;
    padding: 10px 45px 10px 35px;
    margin-right: -40px;
    background: rgb(167, 163, 163);
    color: rgb(0, 0, 0);
    border: 2px solid rgb(0, 0, 0);
    border-radius: 30px;
}

.bi {
    font-size: 25px;

}

.open {
    display: flex;
    justify-content: center;
    align-items: center;
    position: absolute;
    bottom: -30px;
    right: 50%;
    transform: translateX(50%);
}

.btn {
    border-radius: 30px;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 50px;
    height: 50px;
    border: 1px solid black;
    background-color: rgb(32, 31, 31);
    color: rgb(0, 0, 0);
}

.bi-arrow-down-short {
    font-size: 35px;
}

.namber {
    color: rgb(0, 0, 0);
    border: 2px solid rgb(0, 0, 0);
    border-radius: 30px;
    padding: 15px 35px 15px 40px;
    margin-left: -40px;
    background: rgb(167, 163, 163);

    @media (max-width: 500px) {
        display: none;
    }
}
</style>

