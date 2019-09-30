<template>
  <form  >
    <div class="row">
      <div class="col-md-6">
        <div class="form-group">
          <label for="name">
            Display name
            <small id="passwordHelpInline" class="text-muted float-right">15 characters</small>
          </label>
          <input
            type="text"
            v-model="profile.name"
            placeholder="Name"
            class="form-control"
            maxlength="15"
            required
          />
        </div>
      </div>

      <div class="col-md-6">
        <div class="form-group">
          <label for="tagline">
            Tag line
            <small id="passwordHelpInline" class="text-muted float-right">15 characters</small>
          </label>
          <input
            type="text"
            placeholder="@example"
            v-model="profile.tagline"
            class="form-control"
            maxlength="15"
            required
          />
        </div>
      </div>
    </div>

    <div class="row">
      <div class="col-md-6">
        <div class="form-group">
          <label for="sexual">Sexual</label>
          <select  v-model="profile.sexual" class="form-control">
            <option class="dropdown-item" value selected disabled hidden>Select</option>
            <option class="dropdown-item" value="M">Male</option>
            <option class="dropdown-item" value="F">Female</option>
          </select>
        </div>
      </div>

      <div class="col-md-6">
        <div class="form-group">
          <label for="birthdate">Birthday</label>
          <input
            type="date"
            class="form-control"
            v-model="profile.birthdate"
          />
        </div>
      </div>
    </div>
    <a id="submit" @click="handleSubmit" class="gradient-button float-right">Submit</a>
  </form>
</template>

<script>
export default {
  name: "Form",
  props: {
    name: "", sexual: "", tagline: "", birthdate: ""
  },

  data:function() {
    return {
      profile: { name: "", sexual: "", tagline: "", birthdate: "", }
    };
  },
  methods: {
    handleSubmit:function() {

      this.$emit("handleSubmit", this.profile);
    }
  }
};
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.form-group {
  background: rgba(26, 38, 50);
  padding: 0px 10px 0px 10px;
}

select {
  @extend input, .dropdown-menu;
}

.dropdown-toggle::after {
  width: 0.5em;
  height: 0.5em;
  margin: 0.3em 0 0 0.4em;
  content: "";
  border: 0.5em solid;
  border-width: 0 0.1em 0.1em 0;
  transform: rotateZ(45deg);
  float: right;
}

.drop {
  @extend input;
  border: none;
  border-radius: 0;
  width: 100%;
  color: rgba(69, 80, 93);
  &:hover {
    color: rgba(69, 80, 93);
    background: rgba(26, 38, 50);
  }
  &:focus {
    border: none;
  }
}

.dropdown-menu {
  width: 100%;
  border: none;
  border-radius: 0;
  background: rgba(26, 38, 50);
}

.dropdown-item {
  @extend input;
  background: rgba(26, 38, 50);
  color: rgba(255, 255, 255);
  font-weight: 0;
  &:hover {
    background: rgba(73, 83, 91);
    color: rgba(255, 255, 255);
  }
}

input {
  font-size: 20px;
  background: rgba(26, 38, 50);
  border: none;
  color: rgba(118, 125, 131);
  border-radius: 0;
  &:focus {
    color: rgba(255, 255, 255);
    background: rgba(26, 38, 50);
  }
  &:active {
    color: rgba(255, 255, 255);
    background: rgba(26, 38, 50);
  }
}

label {
  font-weight: 200;
  letter-spacing: 1px;
  width: 100%;
  font: 15px;
  padding: 10px 0 0px 0;
}

[type="date"] {
  @extend input;
  background: url(../assets/calendar.png) 97% 50% no-repeat;
  cursor: default;
  &:focus {
    background: url(../assets/calendar.png) 97% 50% no-repeat;
    opacity: 1;
  }

  &:hover {
    opacity: 1;
  }

  &::-webkit-inner-spin-button {
    display: none;
  }

  &::-webkit-calendar-picker-indicator {
    opacity: 0;
    cursor: pointer;
  }
}
</style>
