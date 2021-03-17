<template>
  <b-container fluid>
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
      <b-form-group
        label="Name"
        label-cols="4"
        label-for="name-input-text"
        label-size="lg"
        label-align="right"
      >
        <b-form-input
          id="name-input-text"
          type="text"
          v-model="form.name"
          required
          placeholder="enter staff name"
        ></b-form-input>
      </b-form-group>
      <b-input-group label="Email:" :append="domain">
        <b-form-input
          type="text"
          v-model="form.email"
          required
          placeholder="enter email"
        ></b-form-input>
      </b-input-group>
      <b-input-group label="Initials:">
        <b-form-input
          type="text"
          v-model="form.initials"
          :formatter="fmtInitials"
          required
          placeholder="enter initials"
        ></b-form-input>
      </b-input-group>
      <b-button-group class="float-right my-1">
        <b-button type="submit" :disabled="saving" variant="outline-success"
          >Save</b-button
        >
        <b-button type="reset" variant="outline-info">Reset</b-button>
        <b-button @click="onCancel" variant="outline-danger">Cancel</b-button>
      </b-button-group>
    </b-form>
  </b-container>
</template>
