<template>
    <form id="form" action="https://formsubmit.co/your@email.com" method="POST">
        <div class="form_input_parent">
            <label for="name">Name</label>
            <input class="form_input" type="text" name="name" required>
        </div>
        <div class="form_input_parent">
            <label for="email">Email</label>
            <input class="form_input" type="email" name="email" required>
        </div>
        <div class="form_input_parent span2">
            <label for="message">Message</label>
            <textarea class="form_txt" type="message" name="message" required></textarea>
        </div>
        <div class="form_btn_parent">
            <button class="form_btn" type="submit">Send</button>
        </div>

    </form>
</template>
  
<script>
export default {
    name: 'ContactSeg',
    components: {

    },
    props: {

    },
    data() {
        return {

        }
    },
    methods: {

    },
    mounted() {

    }
}
</script>
  
<style scoped>

#form {
    width: 50%;
    height: 50%;
    display: flex;
    color: white;
    justify-content: space-between;
    font-family: 'Alegreya Sans', sans-serif;
    /* background-color: white; */
    gap: 10px;
    font-size: 1.5em;
    flex-wrap: wrap;
    user-select: none;
}
.span2{
    flex-grow: 1;
}
.form_input_parent{
    width: 40%;
    flex-grow: 1;
    flex-direction: column;
    display: flex;
    justify-content: center;
    align-items: start;
}
.form_txt{
    height: 100%;
    width: 100%;
    outline: none; border: none;
    padding: 10px;
    margin: 0;
    background-color: black;
    margin-top: 10px;
    border: 1px solid white;
    box-sizing:border-box;
    height: 120px;
    color: white;
    resize: none;
}
.form_input{
    height: 100%;
    width: 100%;
    outline: none; border: none;
    padding: 0 10px;
    margin: 0;
    background-color: black;
    margin-top: 10px;
    border: 1px solid white;
    box-sizing:border-box;
    height: 40px;
    color: white;
}

.form_btn_parent{
    width: 100%;
    height: 20px;
}
.form_btn{
    width: 100%;
    height: 100%;
    min-height: 40px;
    background-color: white;
    cursor: pointer;
}

@media (max-width: 1201px) {}

@media (max-width: 1025px) {}

@media (max-width: 769px) {}
</style>
  