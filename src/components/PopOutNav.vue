<template>
    <div class="main">
        <ul id="nav-content">
                <li>About</li>
                <li>contact</li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'pop-out-nav'
    }
</script>

<style scoped>
.main {
    margin-top: 6vh;
    width: auto;
    background-color: #404040;
    color: #FABC2A;
}
li {
    list-style: none;
    padding: 20px;
    margin: 0%;
}
li:hover {
    list-style: none;
    background-color: lightgray;
}
</style>