<template>
  <div class="card-container">
    <div class="card">
      <h3>คลีนิค</h3>
      <p>Clinic M</p>

      <h3>Course A</h3>
      <p>ทำจมูก</p>

      <h3>Title</h3>
      <p>เสริมจมูกให้โด่งๆ จ๊ะ</p>

      <h3>ราคา Course A</h3>
      <p>15000 บาท</p>

      <h3>ราคามัดจำจอง Course A</h3>
      <p>1500 บาท</p>
    </div>
  </div>

</template>

<script lang="ts" setup>
const onClickBookingCourse = () => {
  navigateTo('clinicCourseQrPayment')
};
</script>

<style scoped>
/* ใช้ Flexbox เพื่อจัดปุ่มให้อยู่กลาง */
.button-container {
  display: flex;
  justify-content: center;  /* จัดปุ่มให้อยู่ตรงกลางแนวนอน */
  align-items: center;      /* จัดปุ่มให้อยู่ตรงกลางแนวตั้ง */
  height: 10vh;            /* ให้พื้นที่เต็มหน้าจอ */
}

.styled-button {
  background-color: #4CAF50; /* สีพื้นหลังของปุ่ม */
  color: white;              /* สีข้อความ */
  border: none;              /* ไม่ให้มีขอบ */
  padding: 15px 32px;        /* กำหนดขนาดของปุ่ม */
  text-align: center;        /* จัดข้อความตรงกลาง */
  text-decoration: none;     /* เอาขีดเส้นใต้ข้อความออก */
  display: inline-block;     /* ทำให้ปุ่มเป็นบล็อกที่สามารถจัดตำแหน่งได้ */
  font-size: 16px;           /* ขนาดฟอนต์ */
  border-radius: 8px;        /* มุมมนให้ปุ่ม */
  cursor: pointer;          /* แสดงเคอร์เซอร์เป็นมือ */
  transition: background-color 0.3s; /* เอฟเฟกต์เปลี่ยนสีเมื่อ hover */
}

.styled-button:hover {
  background-color: #45a049; /* เปลี่ยนสีปุ่มเมื่อ hover */
}

.card {
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 20px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.card-container {
  margin-bottom: 20px; /* เพิ่มช่องว่างระหว่างการ์ดกับปุ่ม */
}
</style>
