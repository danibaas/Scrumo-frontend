<template>
  <v-layout pa-2 d-block>
    <div>
      <h1>Dashboard</h1>
      {{ message }}
    </div>
    <div class="float-md-right">
      <UserDisplay :user="localUser" />
    </div>
  </v-layout>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator"
import UserDisplay from "@/components/UserDisplay.vue"

class User {
  constructor(firstName: string, lastName: string, bio: string) {
    this.firstName = firstName
    this.lastName = lastName
    this.bio = bio
  }

  fullName(): string {
    return `${this.firstName} ${this.lastName}`
  }

  firstName: string
  lastName: string
  bio: string
}

@Component({
  components: {
    UserDisplay,
  },
})
export default class YourComponent extends Vue {
  private localUser = new User(
    "Wouter",
    "de Bruijn",
    "Always thinking with portals."
  )

  message: string = "This is a message"
}
</script>
