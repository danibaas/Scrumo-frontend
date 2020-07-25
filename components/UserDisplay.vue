<template>
  <v-card class="mx-auto" max-width="344" outlined>
    <v-list-item three-line>
      <v-list-item-content>
        <div class="overline mb-4">USER</div>
        <v-list-item-title class="headline mb-1">{{
          user.fullName()
        }}</v-list-item-title>
        <v-list-item-subtitle>{{ user.bio }}</v-list-item-subtitle>
      </v-list-item-content>

      <v-list-item-avatar tile size="80"
        ><v-icon x-large>mdi-dog</v-icon></v-list-item-avatar
      >
    </v-list-item>
  </v-card>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator"

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

@Component
export default class UserDisplay extends Vue {
  @Prop({ type: Object, required: true }) readonly user!: User

  message: string = "This is a message"
}
</script>
