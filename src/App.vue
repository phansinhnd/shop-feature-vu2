<template>
  <div id="app">
    <HeaderComponent
      :menuItems="menuItems"
      :isShowModal="isShowModal"
      @toggleModal="toggleModal"
    />
    <ContentComponent v-bind:datas="contentCards" />
    <FooterComponent v:on-click="toggleModal" />
  </div>
</template>

<script>
import HeaderComponent from "./components/HeaderComponent";
import ContentComponent from "./components/ContentComponent";
import FooterComponent from "./components/FooterComponent";

export default {
  name: "App",
  methods: {
    toggleModal() {
      this.isShowModal = !this.isShowModal;
      console.log(1);
    },
  },
  data() {
    return {
      isShowModal: false,
      menuItems: [
        { id: 0, name: "Trang Chủ" },
        { id: 1, name: "Sản Phẩm" },
        { id: 2, name: "Liên Hệ" },
        { id: 3, name: "Giới Thiệu" },
      ],
      contentCards: [
        {
          id: 0,
          srcImg:
            "https://bizweb.dktcdn.net/thumb/large/100/228/168/products/sualai.jpg",
          title: "Mũi Hàn 500",
          price: "25.000đ",
          isSale: true,
          category: "Keo",
        },
        {
          id: 1,
          srcImg:
            "https://bizweb.dktcdn.net/thumb/large/100/228/168/products/sp1-57698689-e2c0-429a-bf4f-3bd0f39230d8.jpg?v=1575337954000",
          title: "Trạm Hàn Hakko 942 75W 200-480*C 220VAC Cực Nóng",
          price: "1.299.000đ",
          isSale: false,
          category: "Cuoc",
        },
        {
          id: 2,
          srcImg:
            "https://pos.nvncdn.com/ed5efb-71717/ps/20200403_FYXXPG69g3KXSfByuP8PMGvQ.jpg",
          title: "Máy Bơm Chìm Hộ Gia Đình QDX 1500W 220VAC 40L/1min H=8m",
          price: "1.599.000đ",
          isSale: false,
          category: "Bua",
        },
        {
          id: 3,
          srcImg:
            "https://bizweb.dktcdn.net/thumb/large/100/228/168/products/module-diy-sac-khong-day-5.jpg?v=1570011041000",
          title: "Module DIY Sạc Không Dây Qi IOS/Androi - Bộ phát V2",
          price: "89.000đ",
          isSale: true,
          category: "Xeng",
        },
        {
          id: 4,
          srcImg:
            "https://bizweb.dktcdn.net/thumb/large/100/228/168/products/bo-dieu-chinh-dien-ap-sdty-200p.jpg?v=1560155769920",
          title:
            "Bộ Điều Chỉnh Điện Áp CHLVFU SDTY-200P 20KW 200A (BH 06 Tháng)",
          price: "2.199.000đ",
          isSale: false,
          category: "Keo",
        },
        {
          id: 5,
          srcImg:
            "https://bizweb.dktcdn.net/thumb/large/100/228/168/products/isd1760-thu-am-thanh-phat-am-thanh-2.jpg?v=1568951032960",
          title: "Module ISD1760 Thu Âm Thanh - Phát Âm Thanh 75s",
          price: "115.000đ",
          isSale: true,
          category: "Bua",
        },
        {
          id: 6,
          srcImg:
            "https://salt.tikicdn.com/cache/750x750/ts/product/c1/d4/66/f01388cf240b1d8f50103ff5047ef55c.jpg",
          title: "Raspberry Pi 3 E14 Model B Plus B+ 2.4G/5G Bluetooth",
          price: "1.295.000đ",
          isSale: false,
          category: "Cuoc",
        },
        {
          id: 7,
          srcImg:
            "https://bizweb.dktcdn.net/100/422/895/products/arduinonodemculuawifiv3ch34048-81fb3bcf-7edb-4831-8198-8db165c4f711.jpg",
          title: "Module IOT ESP8266 ESP-12E CH340 V3",
          price: "85.000đ",
          isSale: true,
          category: "Cuoc",
        },
      ],
    };
  },
  components: {
    HeaderComponent,
    ContentComponent,
    FooterComponent,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;600;700;800&display=swap");

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
}
a {
  outline: none;
}
li {
  list-style: none;
}
.container {
  padding: 0 20px;
  max-width: 1400px;
  margin: 0 auto;
}
</style>
