<template>
  <v-card>
    <v-card-title class="headline font-weight-regular blue-grey white--text">Profile</v-card-title>
    <v-card-text>
      <v-subheader class="pa-0">Where do you live?</v-subheader>
      <v-autocomplete
        v-model="model"
        :hint="!isEditing ? 'Click the icon to edit' : 'Click the icon to save'"
        :items="states"
        :readonly="!isEditing"
        :label="`State — ${isEditing ? 'Editable' : 'Readonly'}`"
        persistent-hint
        prepend-icon="mdi-city"
      >
        <v-slide-x-reverse-transition
          slot="append-outer"
          mode="out-in"
        >
          <v-icon
            :color="isEditing ? 'success' : 'info'"
            :key="`icon-${isEditing}`"
            @click="isEditing = !isEditing"
            v-text="isEditing ? 'mdi-check-outline' : 'mdi-circle-edit-outline'"
          ></v-icon>
        </v-slide-x-reverse-transition>
      </v-autocomplete>
    </v-card-text>
  </v-card>
</template>

<script>
  export default {
    data () {
      return {
        isEditing: false,
        model: null,
        states: [
          'Alabama', 'Alaska', 'American Samoa', 'Arizona',
          'Arkansas', 'California', 'Colorado', 'Connecticut',
          'Delaware', 'District of Columbia', 'Federated States of Micronesia',
          'Florida', 'Georgia', 'Guam', 'Hawaii', 'Idaho',
          'Illinois', 'Indiana', 'Iowa', 'Kansas', 'Kentucky',
          'Louisiana', 'Maine', 'Marshall Islands', 'Maryland',
          'Massachusetts', 'Michigan', 'Minnesota', 'Mississippi',
          'Missouri', 'Montana', 'Nebraska', 'Nevada',
          'New Hampshire', 'New Jersey', 'New Mexico', 'New York',
          'North Carolina', 'North Dakota', 'Northern Mariana Islands', 'Ohio',
          'Oklahoma', 'Oregon', 'Palau', 'Pennsylvania', 'Puerto Rico',
          'Rhode Island', 'South Carolina', 'South Dakota', 'Tennessee',
          'Texas', 'Utah', 'Vermont', 'Virgin Island', 'Virginia',
          'Washington', 'West Virginia', 'Wisconsin', 'Wyoming'
        ]
      }
    }
  }
</script>

<codepen-resources lang="json">
  {
    "css": ["https://cdn.materialdesignicons.com/2.5.94/css/materialdesignicons.min.css"]
  }
</codepen-resources>
