<template>
    <div class="skills">
        <div class="header">
            <h2 class="ski"><i class="bi bi-lightning-charge-fill"></i>Skills<i class="bi bi-lightning-charge-fill"></i></h2>
        </div>
        <div class="items">
            <div class="item">
                <img src="../assets/css.png" alt="">
                <p>CSS</p>
            </div>
            <div class="item">
                <img src="../assets/THREEjs.png" alt="">
                <p>THREE.js</p>
            </div>
            <div class="item">
                <img src="../assets/construct.png" alt="">
                <p>construct3</p>
            </div>
            <div class="item">
                <img src="../assets/js.png" alt="">
                <p>JS</p>
            </div>
            <div class="item">
                <img src="../assets/blender.png" alt="">
                <p>Blender</p>
            </div>
            <div class="item">
                <img src="../assets/html.png" alt="">
                <p>Html</p>
            </div>
            <div class="item">
                <img src="../assets/vue.png" alt="">
                <p>Vue.js</p>
            </div>
            <div class="item">
                <img src="../assets/figma.png" alt="">
                <p>Figma</p>
            </div>
            <div class="item">
                <img src="../assets/pixelart.png" alt="">
                <p>Pixelart</p>
            </div>
            <div class="item">
                <img src="../assets/magic.png" alt="">
                <p>Magicavoxel</p>
            </div>
            <div class="item">
                <img src="../assets/photoshop.png" alt="">
                <p>Photoshop</p>
            </div>
            <div class="item">
                <img src="../assets/vscode.png" alt="">
                <p>Vscode</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
.skills {
    border: 2px solid var(--color-font);
    border-radius: 20px;
    margin-top: 50px;
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
.item{
    min-width: 150px;
    display: flex;
    text-align: center;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    margin: 20px 0 10px 0;
}
</style>

<script></script>