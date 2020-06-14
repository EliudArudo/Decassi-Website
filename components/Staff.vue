<template>
  <div class="full-width staff">
    <div class="flex-center dark-blue-text section-title">
      <span>MEET OUR STAFF</span>
    </div>

    <div class="flex-center staff-wrapper">
      <div
        class="flex-center dark-blue-text person"
        v-for="(person, index) of staff"
        :key="`person-${index}`"
      >
        <v-avatar :size="90" color="grey lighten-4">
          <img :src="require(`@/assets/img/avatars/${person.picture}`)" alt="avatar" />
        </v-avatar>

        <h4>{{person.name}}</h4>

        <span class="light-blue-text position">{{person.position}}</span>

        <p>{{person.about}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      staff: [
        {
          picture: "avatar-1.png",
          name: "Name",
          position: "Position",
          about:
            "sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et"
        },
        {
          picture: "avatar-2.png",
          name: "Name",
          position: "Position",
          about:
            "sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et"
        },
        {
          picture: "avatar-3.png",
          name: "Name",
          position: "Position",
          about:
            "sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et"
        },
        {
          picture: "avatar-4.png",
          name: "Name",
          position: "Position",
          about:
            "sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et"
        }
      ]
    };
  }
};
</script>

<style scoped>
.staff {
  /* height: 300px; */
  flex-direction: column;
}

.staff-wrapper {
  align-items: flex-start;
  flex-wrap: wrap;
}

.person {
  flex-direction: column;
  margin: 20px;
  padding: 20px;
}

.person:hover {
  box-shadow: -1px 0px 2px 6px rgba(0, 0, 0, 0.02);
}

.v-avatar {
  margin-bottom: 15px;
  box-shadow: -1px 0px 2px 6px rgba(0, 0, 0, 0.02);
}

.person p {
  margin-left: auto;
  margin-right: auto;
  text-align: center;
  width: 180px;
}

.person .position {
  font-size: 13px;
}
</style>