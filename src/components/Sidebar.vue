<script>
export default {
    data() {
        return {
            
        }
    }
}
</script>

<template>
    <div class="sidebar shadow">
        <ul>
            <li><i class="fa-solid fa-ruler-combined"></i></li>
            <li><i class="fa-solid fa-life-ring"></i></li>
            <li><i class="fa-solid fa-book"></i></li>
            <li><i class="fa-solid fa-cart-shopping"></i></li>
        </ul>
    </div>
</template>

<style scoped lang="scss"> 
    .sidebar {
        position: fixed;
        top: 20%;
        right: 0;
        z-index: 99;
        background-color: white;
        padding: 0.5rem;
        border-radius: 5px;
        ul{
            display: flex;
            flex-direction: column;
            gap: 16px;
            li:hover{
                cursor: pointer;
            }
        }
    }
</style>