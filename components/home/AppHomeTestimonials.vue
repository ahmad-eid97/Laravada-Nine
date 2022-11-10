<template>
    <section class="testimonials">
        <div class="overlay"></div>
        <div class="row m-0">
            <h2>
                What our customers say
            </h2>
        </div>
        <VueSlickCarousel :slidesToShow = "1" :slidesToScroll = "1" :arrows="true" :dots="false">
            <div>
                <div class="item">
                    <div class="row m-0">
                        <p>
                            “Praesent euismod risus ac erat suscipit consectetur. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Suspendisse scelerisque metus quis lectus sodales molestie et et diam. Etiam sed aliquam mauris. Proin non ex justo. Vestibulum ac massa in ex blandit iaculis.”
                        </p>
                        <h3>
                            IT Group Senior Advisor
                        </h3>
                    </div>
                </div>
            </div>
            <div>
                <div class="item">
                    <div class="row m-0">
                        <p>
                            “Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed pretium sollicitudin nisl, ut hendrerit velit semper et. Nunc eget faucibus turpis. Phasellus pharetra diam ut nisi sagittis eleifend. Suspendisse non sapien lobortis, eleifend felis a, tincidunt lacus. Vestibulum malesuada porta laoreet – nulla erat, tincidunt id urna sed, commodo iaculis magna.”
                        </p>
                        <h3>
                            Law Firm Executive Director
                        </h3>
                    </div>
                </div>
            </div>
            <div>
                <div class="item">
                    <div class="row m-0">
                        <p>
                            “I know I have said before but I must say it again – pellentesque habitant morbi tristique senectus et netus et malesuada! elementum non id lorem. Duis porttitor laoreet malesuada. Maecenas elementum, libero id tincidunt ornare, orci quam fringilla erat, sed ”
                        </p>
                        <h3>
                            Nonprofit Organization President
                        </h3>
                    </div>
                </div>
            </div>
        </VueSlickCarousel>
    </section>
</template>

<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
export default {
    components: { VueSlickCarousel },
    name: 'AppHomeTestimonials'
}
</script>

<style lang="scss">
    .testimonials {
        background-size: cover;
        background-repeat: repeat;
        background-color: rgba(0, 0, 0, 0);
        background-image: url("https://the7.io/event-agency/wp-content/uploads/sites/48/2014/03/sl-event-19.jpg");
        background-attachment: fixed;
        padding: 80px 50px 70px;
        position: relative;
    }
    @include sm {
        .testimonials {
            padding: 40px 10px;
        }
    }
    .testimonials .overlay {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        z-index: 0;
        background-color: rgba(0, 0, 0, 0.51);
    }
    .testimonials h2 {
        color: rgb(255, 255, 255);
        font-size: 40px;
        line-height: 50px;
        text-align: center;
        margin-bottom: 80px;
        padding-bottom: 15px;
        position: relative;
        z-index: 1;
    }
    @include sm {
        .testimonials h2 {
            font-size: 30px;
            padding-bottom: 15px;
            margin-bottom: 10px;
        }
    }
    .testimonials h2:after{
        width: 100px;
        height: 4px;
        background-color: #e73935;
        position: absolute;
        bottom: 0;
        left: calc(50% - 50px);
        content: '';
        z-index: 1;
    }
    .testimonials .item {
        padding: 40px;
        margin: 0 auto;
    }
    .testimonials .item p {
        color: rgb(255, 255, 255);
        font-size: 30px;
        font-style: italic;
        line-height: 42px;
        margin-bottom: 10px;
        text-align: center;
    }
    @include sm {
        .testimonials .item p {
            font-size: 22px;
            line-height: 35px;
        }
    }
    .testimonials .item h3 {
        background-color: rgba(0, 0, 0, 0);
        color: rgb(231, 57, 53);
        font-size: 18px;
        font-weight: 700;
        line-height: 28px;
        text-align: center;
        text-transform: uppercase;
    }
    .testimonials .item h4 {
        color: rgb(255, 255, 255);
        font-size: 14px;
        font-weight: 700;
        line-height: 21px;
    }
    .testimonials .slick-prev {
        left: 0px;
    }
    .testimonials .slick-next {
        right: 0px;
    }
    .testimonials .slick-prev, .testimonials .slick-next {
        width: 40px;
        height: 40px;
        z-index: 2;
    }
    .testimonials .slick-prev::before, .testimonials .slick-next::before {
        font-family: 'slick';
        font-size: 40px;
        line-height: 1;
        opacity: 0.75;
        color: #e73935;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
    }
</style>