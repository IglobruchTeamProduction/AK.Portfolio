<template>
    <div class="header">
        <div class="links">
            <div class="ava">
                <div class="avatarka"><img src="../assets/avatar.png" alt=""></div>
            </div>
        </div>
        <div class="rehts">
            <h1 class="name">Artem Karpov</h1>
            <p class="disc">
                Hello! I'm a developer from Germany. I create creative websites and games. </p>
        </div>
    </div>
</template>
<style scoped lang="scss"> 

.name{
    color: var(--color-font);
}
.disc{
    color: var(--color-font);
}
.links {
    margin: 30px;
    @media (max-width: 550px){
        display: flex;
        align-items: center;
        justify-content: center;

    }
}

.header {
    display: grid;
    grid-template-columns: 1fr 2fr;
    @media (max-width: 550px){
        grid-template-columns: 1fr;
    }
}
.name{
    margin: 0;
}

.avatarka img {
    width: 100%;
}

.avatarka {
    border: 2px solid var(--color-font);;
    border-radius: 50%;
    background: rgb(51,49,49);
background: radial-gradient(circle, rgba(51,49,49,1) 0%, rgba(121,119,119,1) 58%, rgba(182,182,182,1) 100%);
@media (max-width: 550px){
        max-width: 200px;
    }
}
.rehts{
    display: flex;
    justify-content: center;
    flex-direction: column;
}
</style>
