<template>
  <div class="bg-light rounded">
    <div class="d-flex justify-content-between p-1">
      <h1>Contrato</h1>
      <b-button variant="primary" v-b-modal.newRegisterModal
        ><b-icon-person-plus-fill></b-icon-person-plus-fill> Novo
        Contrato</b-button
      >
      <span>Teste</span>
    </div>
    <hr />
    <b-table striped hover :items="items"></b-table>
    <b-modal
      id="newRegisterModal"
      ref="modal"
      title="Submit Your Name"
      @show="resetModal"
      @hidden="resetModal"
      @ok="handleOk"
    >
      <form ref="form" @submit.stop.prevent="handleSubmit">
        <b-form-group
          label="Name"
          label-for="name-input"
          invalid-feedback="Name is required"
          :state="nameState"
        >
          <b-form-input
            id="name-input"
            v-model="name"
            :state="nameState"
            required
          ></b-form-input>
        </b-form-group>
      </form>
    </b-modal>
  </div>
</template>
<script>
export default {
  data() {
    return {
      items: [
        { id: 40, Nome: "Dickerson", last_name: "Macdonald" },
        { id: 21, Nome: "Larsen", last_name: "Shaw" },
        { id: 89, Nome: "Geneva", last_name: "Wilson" },
        { id: 38, Nome: "Jami", last_name: "Carney" },
      ],
    };
  },
};
</script>
<style>
</style>