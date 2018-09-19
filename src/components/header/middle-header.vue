<template>
    <div class="middle-header d-lg-block d-none">
            <div class="container">
                <div class="row">
                    <div class="col-md-5 str-lng">
                        <span class="deliverto">
                            Deliver to
                        </span>
                        <ul class="list-inline m-0">
                            <li class="list-inline-item">
                                <div class="dropdown">
                                    <img src="../../assets/images/UAEFlag.png" alt="" class="store-flag pl-2">
                                    <button class="btn btn-secondary dropdown-toggle store-btn" type="button" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                                 Dubai
                                </button>
                                    <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
                                        <a class="dropdown-item" href="#">Action</a>
                                        <a class="dropdown-item" href="#">Another action</a>
                                        <a class="dropdown-item" href="#">Something else here</a>
                                    </div>
                                </div>
                            </li>
                            <li class="list-inline-item">| عربي</li>
                        </ul>
                    </div>
                    <div class="col-md-2 text-center pt-2">
                        <img src="../../assets/images/logo.png" alt="">
                    </div>
                    <div class="col-md-5 text-right pt-4">
                        <ul class="list-inline">
                            <li class="list-inline-item">
                                <div class="searcharea"><input class="form-control mr-sm-2 search-form" type="search" placeholder="Search" aria-label="Search"><i class="joi-fill-104"></i></div>
                            </li>
                            <li class="list-inline-item account-menu">
                                <div class="dropdown">

                                    <button class="btn btn-secondary dropdown-toggle store-btn" type="button" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                                                <i class="joi-account"></i>
                                    </button>
                                    <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
                                        <a class="dropdown-item" href="#">Action</a>
                                        <a class="dropdown-item" href="#">Another action</a>
                                        <a class="dropdown-item" href="#">Something else here</a>
                                    </div>
                                </div>
                            </li>
                            <li class="list-inline-item shopping-cart">
                                <div class="cartico"><i class="joi-bag"></i><span>2</span></div>
                                <div class="shoppingcart-pannel" style="display: none">
                                    <p class="store text-center">Delivering to <a href="">Dubai, UAE</a></p>
                                    <div class="cart-items">
                                        <div class="ci">
                                            <div class="media">
                                                <img class="mr-3" src="../../assets/images/shoppingcart/image 10.1.jpg" alt="Generic placeholder image">
                                                <div class="media-body">
                                                    <h5 class="mt-0">Chocolate Cake by Magnolia Bakery</h5>
                                                    <p class="m-0">desc-1</p>
                                                    <p class="m-0">desc-1</p>
                                                    <p class="price">100 UAE</p>
                                                </div>
                                            </div>
                                        </div>
                                        <div class="ci">
                                            <div class="media">
                                                <img class="mr-3" src="../../assets/images/shoppingcart/image 4.1.jpg" alt="Generic placeholder image">
                                                <div class="media-body">
                                                    <h5 class="mt-0">Indulgent Rose Box </h5>
                                                    <p class="m-0">desc-1</p>
                                                    <p class="m-0">desc-1</p>
                                                    <p class="price">100 UAE</p>
                                                </div>
                                            </div>
                                        </div>
                                        <div class="ci">
                                            <div class="media">
                                                <img class="mr-3" src="../../assets/images/shoppingcart/image 9.1.jpg" alt="Generic placeholder image">
                                                <div class="media-body">
                                                    <h5 class="mt-0">Your Crystal Heart (M)</h5>
                                                    <p class="m-0">desc-1</p>
                                                    <p class="m-0">desc-1</p>
                                                    <p class="price">100 UAE</p>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                    <div class="cart-btns text-center">
                                        <div class="total-price">
                                            <div class="row">
                                                <div class="col-md-6 text-left">Total</div>
                                                <div class="col-md-6 text-right">1000 UAE</div>
                                            </div>
                                        </div>
                                        <button class="btn joi-btn d-block"><i class="joi-vector-3-3"></i> Secure Checkout</button>
                                        <button class="btn viewbag-btn d-block">View My Bag</button>
                                    </div>
                                </div>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
</template>
<script>
export default {
    data () {
        return {
            
        }
    },
    methods:{
    
    }
}
</script>

