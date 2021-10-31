<template>
    <div class="wrapper" >
        <div class="question">
            <p> This is Questions </p>
            <form action="">
                <div class="option">
                    <input type="radio" id="option1" name="option" value="a">
                    <label for="option1"> option 1</label>
                </div>
                <div class="option" >
                    <input type="radio" id="option2" name="option" value="b">
                    <label for="option2"> option 2</label>
                </div>
                <div class="option">
                    <input type="radio" id="option3" name="option" value="c">
                    <label for="option3"> option 3</label>
                </div>
                <div class="option">
                    <input type="radio" id="option4" name="option" value="d">
                    <label for="option4"> option 4</label>
                </div>
            </form>
        </div>
        <div class="btn"> this submit button</div>
    </div>
</template>

<script setup lang="ts">


</script>

<style scoped>
.wrapper {
    height: 300px;
    width: 400px;
    background-color: #fff;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
}

.question { 
    flex: 1;
    text-align: center;
}

.option {
    padding: 0.5rem 0.25rem;
}
.btn { 
    background-color: #4273F4;
    padding: 1rem 0.5rem;
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
    text-align: center;
    color: #fff;
}

</style>