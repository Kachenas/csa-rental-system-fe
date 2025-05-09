<template>
  <v-container>
    <v-row>
      <v-col v-for="color in colors" :key="color">
        <div class="sample" :style="{ backgroundColor: color }">sample</div>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" lg="6" md="6" sm="6">
        <v-text-field
          v-model="firstName"
          clearable
          label="First Name"
          prepend-icon="$vuetify"
          required
          variant="solo-filled"
        />
      </v-col>
      <v-col cols="12" lg="6" md="6" sm="6">
        <v-text-field
          v-model="lastName"
          clearable
          label="Last Name"
          prepend-icon="$vuetify"
          required
          variant="solo-filled"
        />
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" lg="6" md="6" sm="6">
        <v-text-field
          v-model="email"
          clearable
          label="Email"
          prepend-icon="$vuetify"
          required
          type="email"
          variant="solo-filled"
        />
      </v-col>
      <v-col cols="12" lg="6" md="6" sm="6">
        <v-menu
          v-model="menu"
          :close-on-content-click="false"
          offset-y
          transition="scale-transition"
        >
          <template #activator="{ props }">
            <v-text-field
              v-bind="props"
              v-model="displayDate"
              clearable
              label="Pick a date"
              prepend-icon="mdi-calendar"
              readonly
            />
          </template>

          <v-date-picker v-model="selectedDate" color="primary" @update:model-value="saveDate" />
        </v-menu>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <v-btn block rounded="lg" size="x-large" @click="save">Save</v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup lang="ts">
  import { ref } from 'vue'

  const firstName = ref<string>('');
  const lastName = ref<string>('');
  const email = ref<string>('');
  const selectedDate = ref<Date>('');
  const displayDate = ref<Date>('');
  const menu = ref<boolean>(false)

  const colors = [
    'red', 'yellow', 'white', 'green', 'blue',
    'violet', 'pink', 'brown', 'orange', 'teal',
    'cyan', 'aquamarine',
  ];

  const save = () => {

    menu.value = false;

    const user = {
      'firstName': firstName.value,
      'lastName': lastName.value,
      'email': email.value,
      'birthdate': selectedDate.value,
    }

    console.log('User Info', JSON.stringify(user, null, 2))
  }

  function saveDate (date: string) {
    selectedDate.value = date
    displayDate.value = new Date(date).toLocaleDateString() // Format for display
    menu.value = false // Close the calendar after selecting
  }
</script>

<style scoped>
.sample {
  height: 100px;
  border: 1px solid #ccc;
  color: black;
  padding: 8px;
  text-align: center;
  word-wrap: break-word; /* allow long words to wrap */
  overflow-wrap: break-word; /* modern equivalent for better support */
  white-space: normal; /* allows wrapping */
}
</style>
