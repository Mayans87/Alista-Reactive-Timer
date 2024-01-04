<script>

</script>
<template>
    <div class="nav">
        <nav>
            <ul>
                <li>Home</li>
                <li>About</li>
                <li>Career</li>
                <li>Contact Us</li>
            </ul>
        </nav>
    </div>
</template>
<style scoped>
li{
    list-style: none;
    cursor: pointer;
    font: bolder;
}
li:hover{
color:rgb(4, 117, 93);
}
ul{
    display: flex;
    flex-direction: row;
    justify-content: space-around;
}
.nav{
    background-color: rgb(7, 218, 172);
    color: white;
    font-weight: bolder;
    font-size: larger;
    padding: 5px;
    margin-bottom: 10px;
    border: 5px solid rgb(4, 117, 93);
}

</style>