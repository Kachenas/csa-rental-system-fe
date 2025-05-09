<template>
  <v-container>
    <v-row>
      <v-col v-for="color in colors" :key="color">
        <div class="sample" :style="{ backgroundColor: color }">
          sample
        </div>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" lg="6" md="6" sm="6">
        <v-text-field clearable label="First Name" prepend-icon="$vuetify" variant="solo-filled" />
      </v-col>
      <v-col cols="12" lg="6" md="6" sm="6">
        <v-text-field clearable label="Last Name" prepend-icon="$vuetify" variant="solo-filled" />
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" lg="6" md="6" sm="6">
        <v-text-field clearable label="Email" prepend-icon="$vuetify" type="email" variant="solo-filled" />
      </v-col>
      <v-col cols="12" lg="6" md="6" sm="6">
        <v-text-field clearable label="Last Name" prepend-icon="$vuetify" variant="solo-filled" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup lang="ts">
  const colors = [
    'red', 'yellow', 'white', 'green', 'blue',
    'violet', 'pink', 'brown', 'orange', 'teal',
    'cyan', 'aquamarine',
  ];
</script>

<style scoped>
.sample {
  height: 100px;
  /* display: flex;
  justify-content: center;
  align-items: center; */
  border: 1px solid #ccc;
  color: black;
  padding: 8px;
  text-align: center;
  word-wrap: break-word;     /* allow long words to wrap */
  overflow-wrap: break-word; /* modern equivalent for better support */
  white-space: normal;       /* allows wrapping */
}

</style>
