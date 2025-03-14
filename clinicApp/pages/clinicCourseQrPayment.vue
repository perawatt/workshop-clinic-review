<template>
  <div class="container">
    <img class="round" @click="showModal = true" src="https://failfast.blob.core.windows.net/mcontent-imgs/temps/delivery/dfqr.png" />
    <p class="container-text">บันทึกรูป</p>

    <!-- Modal -->
    <div v-if="showModal" class="modal-overlay" @click.self="showModal = false">
      <div class="modal-content">
        <h2>จ่ายเงินสำเร็จ</h2>
        <button @click="gotoclinicProfile">ปิด</button>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const showModal = ref(false) // สถานะของการแสดง modal
const gotoclinicProfile = () => {
  showModal.value = false,
  navigateTo('clinicProfile')
};
</script>

<style scoped>
.container-text {
  display: flex;
  flex-direction: column; /* จัดให้รายการเป็นคอลัมน์ */
  justify-content: center; /* จัดแนวตั้งให้อยู่ตรงกลาง */
  align-items: center;     /* จัดแนวนอนให้อยู่ตรงกลาง */
  height: 15vh;           /* ให้พื้นที่เต็มหน้าจอ */
}

/* ใช้ Flexbox เพื่อจัดกลางทั้งในแนวนอนและแนวตั้ง */
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 90vh;
}

.round {
  width: 250px;
  height: 250px;
  cursor: pointer;
}

p {
  margin-top: 20px;
}

/* Modal styles */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5); /* สีพื้นหลังของ modal */
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-content {
  background-color: white;
  padding: 20px;
  border-radius: 8px;
  text-align: center;
  width: 300px;
}

button {
  margin-top: 10px;
  padding: 8px 16px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #45a049;
}
</style>