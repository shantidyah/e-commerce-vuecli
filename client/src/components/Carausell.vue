<template>
    <div id="carouselExampleControls" class="carousel slide" data-ride="carousel">
        <div class="carousel-inner">
            <div class="carousel-item active" >
                <img class="img-fluid" id="car1" src="https://eigerindostore.com/media/wysiwyg/landingpage/exsport-brandpage/Main_Banner_exsport.jpg" alt="First slide">
            </div>
            <div class="carousel-item" id='car2'>
                <img class="d-block w-100" src="http://www.pension-chladek.com/includes/templates/pension-chladek/images/adidas-banner.jpg" alt="Second slide">
            </div>
            <div class="carousel-item">
                <img class="d-block w-100" id='car3' src="https://www.ragesa.co.za/wp-content/uploads/2018/03/WINTER-18_WEBSITE-BANNERS_JACKETS-2.jpg" alt="Third slide">
            </div>
        </div>   
        <a class="carousel-control-prev" href="#carouselExampleControls" role="button" data-slide="prev">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="sr-only">Previous</span>
        </a>
        <a class="carousel-control-next" href="#carouselExampleControls" role="button" data-slide="next">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="sr-only">Next</span>
        </a> 
    </div>
</template>

<script>
export default {

}
</script>

<style>
    #car1 {
        width: 100%;
        height:  100%;
    }
    #car2 {
        height: 470px;
    }
    /* .carousel-inner {
        width: 10%;
        height: 10%;
    } */
</style>
