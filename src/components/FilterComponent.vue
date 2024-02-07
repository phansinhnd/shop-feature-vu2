<!-- eslint-disable -->
<template>
  <div class="filter-wrapper">
    <img :src="filterIcon" alt="Image" width="20px" class="filter-icon" />
    <div>
      <!-- <label for="cars">Choose a car:</label> -->
      <select id="" name="category" class="filter-select filter-price">
        <option value="">Chọn mức giá</option>
        <option v-for="item in priceRanges" :key="item.id" value="item.name">
          {{ item.name }}
        </option>
      </select>

      <select id="" name="category" class="filter-select filter-category">
        <option value="">Chọn chuyên mục</option>
        <option v-for="item in categorys" :key="item.id" value="item.name">
          {{ item.name }}
        </option>
      </select>
      <button class="filter-btn">Lọc</button>
    </div>
  </div>
</template>
<script>/* eslint-disable */
import filterIcon from "@/assets/Image/filter.png";
export default {
  name: "FilterComponent",
  props: {},
  data() {
    return {
      filterIcon: filterIcon,
      categorys: [
        {
          id: 0,
          name: "Búa",
        },
        {
          id: 1,
          name: "Kéo",
        },
        {
          id: 2,
          name: "Cuốc",
        },
        {
          id: 3,
          name: "Xẻng",
        },
      ],
      priceRanges: [
        { id: 0, name: "100.000 VNĐ - 200.000 VNĐ" },
        { id: 0, name: "200.000 VNĐ - 400.000 VNĐ" },
        { id: 0, name: "400.000 VNĐ - 600.000 VNĐ" },
        { id: 0, name: "600.000 VNĐ - 800.000 VNĐ" },
        { id: 0, name: "800.000 VNĐ - 1000.000 VNĐ" },
        { id: 0, name: "Trên 1000.000 VNĐ" },
      ],
    };
  },
  methods: {},
};
</script>
<style scoped>
.hover-primary{
    opacity: 0.8;
}
.filter-wrapper {
  display: flex;
  margin-bottom: 40px;
  padding: 20px 0 20px 10px;
  border-bottom: 1px solid rgba(0, 0, 0, 0.05);
  background: white;
  border-radius: 4px;
}
.filter-icon {
  display: inline-block;
  margin-right: 10px;
}
.filter-select {
  position: relative;
  padding: 4px;
  color: rgba(0, 0, 0, 0.5);
  color: rgba(0, 0, 0, 0.7);
  border-radius: 4px;
  border: 1px solid rgba(0, 0, 0, 0.1);
  outline-color: rgb(0, 0, 255, 0.2);
}
.filter-select::before {
  content: "ggggggggg";
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  color: black;
}

.filter-wrapper .filter-select + .filter-select {
  margin-left: 20px;
}
.filter-btn {
  min-width: 80px;
  min-height: 32px;
  margin-left: 20px;
  padding: 0px 8px;
  color: white;
  font-size: 16px;
  font-weight: 500;
  line-height: 1;
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  background: #f05123;
  cursor: pointer;
}
.filter-btn:hover {
    opacity: .7;
}
</style>
