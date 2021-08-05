<template>
        <br>
        <div class="d-flex align-items-center justify-content-center flex-column py-5 text-center" >
            <form class="form-signin">
                <h3 class="mb-3 danger font-weight-normal display-4">Contact Me <img class="mb-4" src="../../public/contact.svg" alt="" width="50"></h3>
                <input type="email" id="inputEmail" class="form-control" placeholder="Johndoe@gmail.com" required autofocus>
                <textarea class="form-control" rows="3" placeholder="Write something ..."></textarea><br>
                <button class="btn btn-lg btn-primary btn-block" type="submit">Send</button> <br>
                <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d15838.166682610798!2d125.53889033601045!3d7.063012863303649!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x32f90d42c66770b9%3A0xb670046ced381d8a!2sCrossing%20Ulas!5e0!3m2!1sen!2sph!4v1628146547884!5m2!1sen!2sph" width="350" height="100" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
            </form>
            <br><br><br><br><br>
            <img class="d-none d-md-block" src="../../public/contact2.jpg" alt="" width="450">
        </div>
    <Footer/>
</template>

<script>
import Footer from '../components/Footer.vue'
export default {
    name:'Contact',
    components: {Footer}
}
</script>

<style scoped>


</style>