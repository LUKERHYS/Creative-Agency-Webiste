<template>
    <div class="footer-container">
        <div class="footer-child left">
            <ul>
                <li><p>hello@lukemelvin.com</p></li>
            </ul>
        </div>
        <div class="footer-child middle">
            <ul>
                <li><p>&copy; 2020 LukeMelvin.com</p></li>
            </ul>
        </div>
        <div class="footer-child">
            <ul>
                <li><p>T&C's</p></li>
                <li><p>privacy/cookies</p></li>
                <li><p>GDPR Compliance</p></li>
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
.footer-container {
    /* display: flex;
    justify-content: space-between;
    position: relative;
    bottom: -1;
    height: 10vh;
    width: 100vw;
    margin-top: 5vh; */
     position: absolute;
    bottom: 0;
    width: 100%;
    height: 2.5rem; 
    background-color: #404040;;
    color: #FBFBFB;
}
.footer-child {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-end;
    width: 30vw;
}
.left, .middle {
    border-right: #FABC2A dashed 1px;
}
li {
    list-style: none;
}
p {
    font-size: 15px;
}
</style>