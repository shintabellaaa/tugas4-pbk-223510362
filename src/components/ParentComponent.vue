<template>
    <!-- Container untuk komponen induk -->
    <div class="parent">
      <!-- Judul komponen induk -->
      <h1>Komponen Induk</h1>
      <!-- Container untuk child component -->
      <div class="child-container">
        <!-- Memanggil ChildComponent dan menambahkan event listener untuk data yang dikirimkan -->
        <ChildComponent @data-emitted="handleDataEmitted" />
        <!-- Menampilkan data yang diterima dari child component jika ada -->
        <p v-if="showReceivedData" class="received-data">Data yang Diterima: {{ receivedData }}</p>
      </div>
    </div>
  </template>
  <script>
  import ChildComponent from './ChildComponent.vue';
  export default {
    components: {
      ChildComponent,
    },
    data() {
      return {
        receivedData: '', // Menyimpan data yang diterima dari ChildComponent
        showReceivedData: false, // Untuk mengontrol animasi tampilan data yang diterima
      };
    },
    methods: {
      // Method untuk menangani data yang diterima dari ChildComponent
      handleDataEmitted(data) {
        this.receivedData = data; // Menyimpan data yang diterima
        this.showReceivedData = true; // Menampilkan teks dengan animasi
        // Sembunyikan teks setelah beberapa detik
        setTimeout(() => {
          this.showReceivedData = false;
        }, 3000);
      },
    },
  };
  </script>
  ini ParentComponent.vue