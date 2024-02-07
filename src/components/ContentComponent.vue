<!-- eslint-disable -->
<template>
  <section class="wrapper container">
    <FilterComponent />
    <div class="products">
      <ul class="products-list">
        <li class="main-product no-margin" v-for="item in datas" :key="item.id">
          <div class="main-product-sale" v-if="item.isSale">Giảm giá</div>
          <div class="main-product-wrapper">
            <div class="img-product">
              <img class="img-prd" v-bind:src="item.srcImg" alt="Image" />
            </div>
            <div class="content-product">
              <h3 class="content-product-h3">{{ item.title }}</h3>
              <div class="content-product-deltals">
                <div class="price">
                  <span class="money">{{ item.price }}</span>
                </div>
                <button
                  type="button"
                  class="btn btn-cart"
                  :style="{ color: textColor }"
                >
                  Thêm Vào Giỏ
                </button>
              </div>
            </div>
          </div>
        </li>
      </ul>
    </div>
  </section>
</template>
<script>/* eslint-disable */
import FilterComponent from "./FilterComponent";
export default {
  name: "ContentComponent",
  components:{
    FilterComponent,
  },
  props: {
    datas: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      textColor: "black",
    };
  },
};
</script>
<style scoped>
/* wrapper */
.wrapper {
  /* padding-top: 60px; */
  padding-bottom: 60px;
  background: rgba(0, 0, 0, 0.03);
}

.main-product {
  position: relative;
  padding: 0 6px !important;
  padding-bottom: 20px;
}
.main-product-wrapper:hover {
  box-shadow: 2px 8px 12px rgba(0, 0, 0, 0.1);
}
.main-product-sale {
  position: absolute;
  z-index: 100;
  top: 6px;
  left: -0.5px;
  padding: 2px 4px;
  font-size: 14px;
  color: white;
  background: #f05123;
  border-radius: 4px;
}
.main-product-sale::before {
  position: absolute;
  bottom: 0;
  left: 0;

}

.main-product-wrapper {
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  overflow: hidden;
  transition: all 0.2s linear;
}
.products-list {
  margin-right: -6px;
  margin-left: -6px;
}
.products ul {
  display: inline-block;
}

.products ul .main-product {
  margin-bottom: 2rem;
  margin-right: 1rem;
  display: block;
  float: left;
  width: 25%;
}

.products ul .no-margin {
  margin-right: 0;
}
.products ul .img-product {
  overflow: hidden;
}
.products ul .img-product img {
  transition: all 0.2s linear;
}
.products ul .img-product:hover img {
  transform: scale(1.3);
  transform-origin: center;
}

.products ul .img-product img {
  width: 100%;
  cursor: pointer;
}

.content-product {
  background: #fff;
}
.content-product .content-product-h3 {
  padding: 0.5rem;
  overflow: hidden;
  color: #222;
  font-weight: 500;
  font-size: 16px;
  max-height: 50px;
  min-height: 50px;
  text-align: center;
  line-height: 19px;
  margin: 0 0 5px;
  cursor: pointer;
}

.content-product .content-product-deltals {
  display: flex;
  justify-content: center;
  padding: 20px 10px;
}

.main-product .content-product .content-product-deltals .price {
  color: #f05123;
  font-weight: 400;
  margin-right: 1rem;
  vertical-align: middle;
  font-size: 20px;
}

.content-product .content-product-deltals .price .money {
  vertical-align: middle;
}

.content-product .content-product-deltals .btn-cart {
  padding: 10px 20px;
  border: none;
  background: #f1df11;
  border-radius: 5px;
  color: #fff;
  font-weight: 500;
  cursor: pointer;
  box-shadow: 3px 6px 8px rgba(0, 0, 0, 0.2);
}

.content-product .content-product-deltals .btn-cart:hover {
  background: #c7b200;
}

/* footer */
.footer-item {
  padding: 0.5rem 2rem;
  background: #f1df11;
  display: flex;
}

.footer-item .img-footer {
  align-items: center;
  display: flex;
}

.footer-item .img-footer img {
  width: 100%;
}

.footer-item .social-footer {
  display: flex;
  align-items: center;
  width: 100%;
  justify-content: flex-end;
}

.footer-item .social-footer li a {
  color: #000000;
  font-size: 2rem;
}

.footer-item .social-footer li:last-child {
  margin-left: 0.5rem;
}
</style>
