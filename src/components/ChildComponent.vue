<template>
    <!-- Container untuk komponen anak -->
    <div class="child">
      <!-- Judul komponen anak -->
      <h2>Komponen Anak</h2>
      <!-- Tombol untuk memicu event dan mengirim data ke parent component -->
      <button @click="emitData" aria-label="Kirim Data">Kirim Data</button>
    </div>
  </template>

  <script>
  export default {
    data() {
      return {
        emittedData: '', // Menyimpan data yang akan dikirim ke parent component
      };
    },
    methods: {
      // Method untuk mengirim data ke parent component
      emitData() {
        const data = 'Kata Anak HALLO!'; // Data yang akan dikirim
        this.emittedData = data; // Menyimpan data yang dikirim
        this.$emit('data-emitted', data); // Memancarkan event dengan data yang dikirim
      },
    },
  };
  </script> ini ChildComponent.vue