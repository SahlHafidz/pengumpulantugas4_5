<template>
  <div class="">
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Tugas Telat</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav">
            <li class="nav-item">
              <a class="nav-link active" aria-current="page" href="/">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="/tugas4">Tugas 4</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="/tugas5">Tugas 5</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <div class="container">
      <form v-on:submit.prevent="handleSubmit">
        <div class="field">
          <label class="label">Nama Lengkap</label>
          <div class="control">
            <input
              v-model="form.name"
              class="input"
              type="text"
              placeholder="Nama lengkap"
            />
          </div>
        </div>

        <div class="control">
          <label class="label">Apakah Sudah Makan?</label>
          <br />
          <label class="checkbox">
            <input
              type="checkbox"
              v-model="form.info_makan"
              value="sarapan"
            />Sarapan
          </label>
          <label class="checkbox">
            <input
              type="checkbox"
              v-model="form.info_makan"
              value="makan_siang"
            />Makan siang
          </label>
          <label class="checkbox">
            <input
              type="checkbox"
              v-model="form.info_makan"
              value="makan_malam"
            />Makan Malam
          </label>
        </div>
        <button class="button is-primary">Submit</button>
      </form>
      <div>
        <h3>Hasil Submit Form</h3>
        <ul>
          <li
            style="list-style-type: none"
            v-for="item in inputanForm"
            :key="item"
          >
            Nama:
            {{ form.name }}
            <br />
            Info Makan:
            {{ form.info_makan }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout(context) {
    return 'custom'
  },
  data() {
    return {
      form: {
        name: '',
        info_makan: [],
      },
      inputanForm: [],
      heightInp: null,
      inpValSubmitted: 'Not submitted yet',
    }
  },
  methods: {
    handleSubmit() {
      // console.log(this.form)
      const item = {
        form: this.form,
      }
      this.inputanForm.push(item)
    },
    registerAnswer() {
      if (this.heightInp) {
        this.inpValSubmitted = this.heightInp + ' cm'
      }
    },
  },
}
</script>

<style>
</style>