<template>
    <div class="projects">
        <div class="header">
            <h2 class="ski"><i class="bi bi-robot"></i> Projects <i class="bi bi-robot"></i>
            </h2>
        </div>
        <div class="project" v-for="project in projectsData">
            <a class="links" :href="project.link">
                <img class="imge" :src="project.imge" alt="">
                <div class="back_img"><i class="bi bi-eye"></i></div>
            </a>
            <div class="rehts">
                <h3 class="header">{{ project.title }}</h3>
                <p>{{ project.beshreibung }}</p>
                <a class="btn" :href="project.link">Switch to the project</a>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
.links img {
    width: 100%;
    object-fit: contain;
    object-position: center;
}

.links {
    position: relative;
    overflow: hidden;
    border: 2px solid var(--color-font);
    border-radius: 20px;
}

.back_img {
    position: absolute;
    inset: 0;
    background-color: rgba(0, 0, 0, 0.493);
    opacity: 0;
    transition: 0.5s;
    display: flex;
    align-items: center;
    justify-content: center;
}

.back_img i {
    font-size: 80px;
    color: whitesmoke;

}

.back_img:hover {
    opacity: 1;
}

.header {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    border-bottom: 2px solid var(--color-font);
}

.btn {
    border: 2px solid var(--color-font);
    color: var(--color-font);
    padding: 5px 10px;
    margin-bottom: 20px;
    border-radius: 5px;
    transition: 0.5s ease-out;
}

.btn:hover {
    padding: 5px 30px;
}

.projects {
    border: 2px solid var(--color-font);
    border-radius: 20px;
    margin-top: 100px;
    color: var(--color-font);
}

.project {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 50px;
    text-align: center;
    padding: 20px 10px;

    @media (max-width: 600px) {
        grid-template-columns: 1fr;
        gap: 0;
        margin: 10px;
    }

}

.rehts {
    border: 2px solid var(--color-font);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    border-radius: 20px;
}

.rehts h3 {
    padding-bottom: 20px;
}

.rehts p {
    padding: 5px;
    max-width: 300px;
}
</style>

<script setup>
import { projects } from '../data/projects';
import { ref } from 'vue';
const projectsData = ref(projects)
</script>
