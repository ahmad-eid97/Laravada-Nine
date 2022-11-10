<template>
    <section class="services">
        <div class="row m-0 justify-content-center">
            <h2>
                WHAT WE DO
            </h2>
        </div>
        <div class="row m-0">
            <div class="col-sm-6 col-lg-4 col-xl-3 p-0">
                <div class="item">
                    <div class="image">
                        <img class="img-fluid" src="https://the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl-event-06-600x400.jpg" alt="">
                        <div class="overlay">
                            <font-awesome-icon icon="fa-solid fa-bars-staggered" />
                        </div>
                    </div>
                    <h3>
                        CONFERENCES & EVENTS
                    </h3>
                    <p>
                        Cras hendrerit purus a hendrerit semper
                    </p>
                    <a href="#" class="btn">
                        VIEW DETAILS
                    </a>
                </div>
            </div>
            <div class="col-sm-6 col-lg-4 col-xl-3 p-0">
                <div class="item">
                    <div class="image">
                        <img class="img-fluid" src="https://the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl-event-01-600x400.jpg" alt="">
                        <div class="overlay">
                            <font-awesome-icon icon="fa-solid fa-bars-staggered" />
                        </div>
                    </div>
                    <h3>
                        TRADE SHOW SERVICES
                    </h3>
                    <p>
                        Fusce auctor tellus eget lectus malesuada
                    </p>
                    <a href="#" class="btn">
                        VIEW DETAILS
                    </a>
                </div>
            </div>
            <div class="col-sm-6 col-lg-4 col-xl-3 p-0">
                <div class="item">
                    <div class="image">
                        <img class="img-fluid" src="https://the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl-event-05-600x400.jpg" alt="">
                        <div class="overlay">
                            <font-awesome-icon icon="fa-solid fa-bars-staggered" />
                        </div>
                    </div>
                    <h3>
                        INCENTIVE PROGRAMS
                    </h3>
                    <p>
                        Erat ante convallis est et euismod nunc
                    </p>
                    <a href="#" class="btn">
                        VIEW DETAILS
                    </a>
                </div>
            </div>
            <div class="col-sm-6 col-lg-4 col-xl-3 p-0">
                <div class="item">
                    <div class="image">
                        <img class="img-fluid" src="https://the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl002-600x400.jpg" alt="">
                        <div class="overlay">
                            <font-awesome-icon icon="fa-solid fa-bars-staggered" />
                        </div>
                    </div>
                    <h3>
                        STRATEGIC MEETING MANAGEMENT
                    </h3>
                    <p>
                        Vestibulum a aliquam mauris
                    </p>
                    <a href="#" class="btn">
                        VIEW DETAILS
                    </a>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppHomeServices'
}
</script>

<style lang="scss">
    .services {
        font-size: 16px;
        padding-bottom: 30px;
        padding-left: 50px;
        padding-right: 50px;
        padding-top: 80px;
        background-color: #f7f7f7;
    }
    @include sm {
        .services {
            padding-left: 10px;
            padding-right: 10px;
            padding-top: 80px;
        }
    }
    .services h2 {
        color: rgb(36, 46, 53);
        font-size: 40px;
        line-height: 50px;
        text-align: center;
        margin-bottom: 80px;
        max-width: 970px;
        padding-bottom: 15px;
        position: relative;
    }
    @include sm {
        .services h2 {
            font-size: 30px;
            line-height: 50px;
        }
    }
    .services h2:after{
        width: 100px;
        height: 4px;
        background-color: #e73935;
        position: absolute;
        bottom: 0;
        left: calc(50% - 50px);
        content: '';
    }
    .services .item {
        margin: 0 25px 50px;
        text-align: center;
    }
    .services .image {
        margin-bottom: 30px;
        position: relative;
    }
    .services .image img {
        position: relative;
        z-index: 0;
    }
    .services .image .overlay {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        z-index: 1;
        display: flex;
        align-items: center;
        justify-content: center;
        background-color: rgba(231, 57, 53, 0.5);
        opacity: 0;
        transition: all 0.3s linear;
    }
    .services .image:hover .overlay {
        opacity: 1;
    }

    .services .image .overlay svg {
        color: #fff;
        font-size: 36px;
    }
    .services .item h3 {
        color: rgb(36, 46, 53);
        font-size: 26px;
        line-height: 36px;
        margin-bottom: 5px;
        text-align: center;
    }
    @include sm {
        .services .item h3 {
            font-size: 20px;
            line-height: 28px;
        }
    }
    .services .item p {
        color: rgb(113, 120, 124);
        font-size: 16px;
        font-weight: 400;
        line-height: 28px;
        margin-bottom: 20px;
        text-align: center;
    }
    .services .item .btn {
        background: var(--main-color);
        border-radius: 100px;
        box-shadow: rgba(0, 0, 0, 0) 0px 0px 10px 0px;
        box-sizing: border-box;
        color: rgb(255, 255, 255);
        font-size: 12px;
        max-width: 100%;
        padding-bottom: 9px;
        padding-left: 20px;
        padding-right: 20px;
        padding-top: 10px;
        text-align: center;
        transition-duration: 0.3s;
        transition-property: all;
        transition-timing-function: ease-out;
        border: none;
    }
</style>