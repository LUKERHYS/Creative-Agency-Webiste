<template>
    <div class="footer-container">
        <div class="footer-child">
            <ul>
                <li><p>hello@lukemelvin.com</p></li>
            </ul>
        </div>
        <div class="footer-child">
            <ul>
                <li><p>&copy; 2020 LukeMelvin.com</p></li>
            </ul>
        </div>
        <div class="footer-child">
            <ul>
                <li><p>hello@lukemelvin.com</p></li>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'footer-bar'
        }
</script>

<style lang="css" scoped>
div {
    /* border: red solid; */
}
.footer-container {
    display: flex;
    justify-content: space-between;
    position: relative;
    left: 0;
    bottom: 0;
    height: 20vh;
    width: 100vw;
    margin-top: 5vh;
    background-color: #404040;;
    color: #FABC2A;
}
.footer-child {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-end;
    width: 30vw;
}
li {
    list-style: none;
    list-style-position: ;
}
p {
    font-size: 15px;
}
</style>