<template>
  <h2>รายการ Course ที่จองไว้ </h2>

  <div class="card-container">
    <div @click="onClickDetailCourse" class="card">
      <h3>Course A</h3>
      <p>ทำจมูก</p>
    </div>
    <br>

    <div @click="onClickDetailCourse" class="card">
      <h3>Course B</h3>
      <p>ทำปาก</p>
    </div>
  </div>


</template>

<script setup lang="ts">
const onClickDetailCourse = () => {
  navigateTo('userMyOrderDetail')
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  margin: 30px;
}

.xxx {
  background-color: gray;
}

.round {
  border-radius: 50%;
}

.card-container {
  justify-items: space-around;
  /* ทำให้การ์ดอยู่ห่างกัน */
  gap: 20px;

}

.card {
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 20px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.card h3 {
  margin: 0 0 10px 0;
}

.card p {
  margin: 0;
}
</style>