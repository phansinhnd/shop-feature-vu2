<!-- eslint-disable -->
<template>
  <header>
    <nav class="container">
      <div class="img-nav">
        <img
          src="https://namviet-corp.vn/wp-content/uploads/2022/08/logo-white@1x.png"
          alt=""
        />
      </div>
      <div class="content-nav">
        <ul>
          <li v-for="item in menuItems" :key="item.id">
            <a href="#">{{ item.name }}</a>
          </li>
        </ul>
        <form>
          <input
            type="text"
            name="search"
            placeholder="Tìm kiếm sản phẩm..."
            :style="{ color }"
          />
          <button type="submit">
            <i class="fa fa-search" aria-hidden="true"></i>
          </button>
        </form>
      </div>
      <!-- The Modal -->
      <button id="cart" @click="toggleModal">
        <img
          src="https://cdn-icons-png.flaticon.com/512/3081/3081840.png"
          alt="cart"
          height="20px"
        />
        Giỏ Hàng
      </button>
      <div id="myModal" class="modal" v-if="isShowModal" @click="toggleModal">
        <div class="modal-content" @click="handlePropagation">
          <div class="modal-header">
            <h5 class="modal-title">Giỏ Hàng</h5>
            <span class="close" @click.stop="toggleModal">&times;</span>
          </div>
          <div class="modal-body">
            <div class="cart-row">
              <span class="cart-item cart-header cart-column">Sản Phẩm</span>
              <span class="cart-price cart-header cart-column">Giá</span>
              <span class="cart-quantity cart-header cart-column"
                >Số Lượng</span
              >
            </div>
            <div class="cart-items"></div>
            <div class="cart-total">
              <strong class="cart-total-title">Tổng Cộng:</strong>
              <span class="cart-total-price">0VNĐ</span>
            </div>
          </div>

          <div class="modal-footer">
            <button
              type="button"
              class="btn btn-secondary close-footer"
              @click.stop="toggleModal"
            >
              Đóng
            </button>
            <button type="button" class="btn btn-primary order" @click="handlePayment">
              Thanh Toán
            </button>
          </div>
        </div>
      </div>
    </nav>
  </header>
</template>
<script>/* eslint-disable */
export default {
  name: "HeaderComponent",
  props: {
    menuItems: {
      type: Array,
      required: true,
    },
    isShowModal: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      color: "rgba(0,0,0,0.6)",
      isShowModelHeader: this.isShowModal,
    };
  },
  methods: {
    toggleModal() {
      // this.isShowModelHeader = !this.isShowModelHeader;
      this.$emit("toggleModal");
    },
    handlePropagation(even){
      even.stopPropagation();
      console.log(2);
    },
    handlePayment(){
      this.toggleModal();
      alert("Cảm ơn bạn đã thanh toán!");
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
header {
  background: #f1df11;
}
nav {
  padding: 15px;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav .content-nav {
  display: flex;
  line-height: 2rem;
  flex-direction: row;
  justify-content: flex-end;
  align-items: center;
  width: 60%;
}

nav .content-nav ul {
  display: flex;
}

nav .content-nav ul li a {
  text-decoration: none;
  color: #000;
  text-transform: uppercase;
  padding: 0 15px;
  font-weight: 700;
}

nav .content-nav ul li a:hover {
  color: #fff;
}

.content-nav form {
  position: relative;
}

.content-nav form input {
  border: none;
  background: #fff;
  padding: 7px;
  outline: none;
  border-radius: 12px;
}

.content-nav form button {
  padding: 5px;
  border-radius: 12px;
  position: absolute;
  right: 0;
  top: 2px;
  border: none;
  outline: none;
  background: #fff;
}

/* modal */
.modal {
  /* display: none; */
  position: fixed;
  z-index: 1000;
  padding-top: 100px;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgba(0, 0, 0, 0.5);
}

.modal-content {
  margin: 0 auto;
  width: 50%;
  position: relative;
  display: flex;
  flex-direction: column;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid rgba(0, 0, 0, 0.1);
  box-shadow: 4px 8px 10px rgba(0, 0, 0, 0.2);
  border-radius: 0.3rem;
  outline: 0;
}

.modal-body {
  padding: 1rem;
}

.modal-footer {
  display: flex;
  border-top: 1px solid #aaaaaa;
  padding: 1rem;
  flex-direction: row;
  justify-content: flex-end;
  border-top: 1px solid #aaaaaa;
  padding: 1rem;
}

.modal-footer > :not(:first-child) {
  margin-left: 0.25rem;
}

.btn {
  cursor: pointer;
  outline: none;
  font-weight: 400;
  line-height: 1.25;
  text-align: center;
  white-space: nowrap;
  vertical-align: middle;
  border: 1px solid transparent;
  padding: 0.5rem 1rem;
  font-size: 1rem;
  border-radius: 0.25rem;
  transition: all 0.2s ease-in-out;
}
.modal-footer .btn:hover {
  opacity: 0.8;
}
.modal-footer .close-footer:hover {
  color: #fff;
  opacity: unset;
  background: #f1df11;
}
.btn-secondary {
  color: #292b2c;
  background-color: #fff;
  border-color: #ccc;
}

.btn-primary {
  color: #fff;
  background-color: #0275d8;
  border-color: #0275d8;
}

.modal-header {
  align-items: center;
  display: flex;
  justify-content: space-between;
  border-bottom: 1px solid #aaaaaa;
  padding: 1rem;
}

h5.modal-title {
  font-size: 1.5rem;
}

.close {
  color: #aaaaaa;
  font-size: 28px;
  font-weight: bold;
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
}

.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
}

#cart {
  display: flex;
  gap: 4px;
  font-size: 15px;
  color: #fff;
  background: rgba(0, 0, 0, 0.1);
  border: 1px solid transparent;
  border-radius: 10px;
  outline: none;
  margin-left: 1rem;
  padding: 12px;
  cursor: pointer;
}

#cart:hover {
  border-color: #fff;
}
</style>
