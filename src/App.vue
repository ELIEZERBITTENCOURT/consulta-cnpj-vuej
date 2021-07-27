<template>
  <div id="app">
    <b-form class="p-2">
      <b-form-group label="Nome">
        <b-form-input v-model="form.nome" type="text"></b-form-input>
      </b-form-group>
 
      <b-form-group label="Tipo de pessoa">
        <b-form-radio v-model="mascaraCpfOuCnpj" value="###.###.###-##" selected
          >Pessoa Física</b-form-radio
        >
        <b-form-radio v-model="mascaraCpfOuCnpj" value="##.###.###/####-##"
          >Pessoa Jurídica</b-form-radio
        >
      </b-form-group>
 
      <b-form-group label="CPF/CNPJ">
        <b-form-input
          v-model="form.cpf_ou_cnpj"
          v-mask="mascaraCpfOuCnpj"
        ></b-form-input>
      </b-form-group>
 
      <b-button type="reset" variant="warning" class="mr-2">Limpar</b-button>
      <b-button type="submit" variant="primary">Consultar</b-button>
    </b-form>
  </div>
</template>
<script>
export default {
  name: "App",
  data() {
    return {
      mascaraCpfOuCnpj: "",
      form: {
        nome: "",
        data_nascimento: "",
        cpf_ou_cnpj: "",
      },
    };
  },
};
</script>