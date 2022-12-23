<template>
  <AGAppContainer>
    <a-g-full-width-page>
      <template v-slot:toolbar>
        <AGHeader>
          <AGButtonDropDown :items="ddOptions">
            <template v-slot:label>Hello</template>
            <AGDropDownButtonItem
              v-for="(item, index) in ddOptions"
              :key="index"
              :icon="item.icon"
              :name="item.name"
              @click="onDDClick(index)"
            />
          </AGButtonDropDown>
        </AGHeader>
      </template>
      <template v-slot:side-menu>
        <AGSideMenu :items="ddOptions">
          <AGSideMenuItem
            v-for="(item, index) in ddOptions"
            :key="index"
            :icon="item.icon"
            :name="item.name"
          />
        </AGSideMenu>
      </template>
      <template v-slot:content-area>
        <AGContainer>
          <AGPanel>
            <AGLogo is-small />
            <h5>Welcome to <span>Aeroglobe</span></h5>
            <p>Sign in to your account to continue...</p>
            <form>
              <AGTextField v-model="email" label="Email" />
              <AGTextField v-model="email" label="Password" error="error" />
              <div class="forgot_card">
                <AGButton type="link">Forgot password</AGButton>
              </div>
              <div class="d-grid">
                <AGButton type="primary">Log In</AGButton>
              </div>
            </form>
          </AGPanel>
        </AGContainer>
      </template>
    </a-g-full-width-page>
  </AGAppContainer>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import {
  AGButton,
  AGFullWidthPage,
  AGTextField,
  AGLogo,
  AGSideMenu,
  AGSideMenuItem,
  AGButtonDropDown,
  AGDropDownButtonItem,
  AGHeader,
  AGAppContainer,
  AGContainer,
  AGPanel,
} from "ag-ui-vite"; // @ is an alias to /src

export default defineComponent({
  name: "HomeView",
  components: {
    AGButton,
    AGFullWidthPage,
    AGTextField,
    AGLogo,
    AGSideMenu,
    AGSideMenuItem,
    AGButtonDropDown,
    AGDropDownButtonItem,
    AGHeader,
    AGAppContainer,
    AGContainer,
    AGPanel,
  },
  data() {
    return {
      email: "",
    };
  },
  computed: {
    ddOptions() {
      return [
        {
          name: "Item1",
          icon: "@/assets/images/logout.svg",
        },
        {
          name: "Item1",
          icon: "@/assets/images/logout.svg",
        },
        {
          name: "Item1",
          icon: "@/assets/images/logout.svg",
        },
        {
          name: "Item1",
          icon: "@/assets/images/logout.svg",
        },
        {
          name: "Item1",
          icon: "@/assets/images/logout.svg",
        },
      ];
    },
  },
  methods: {
    onDDClick(index: number) {
      alert(index);
    },
  },
});
</script>
<style>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
