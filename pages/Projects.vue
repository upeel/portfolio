<template>
  <div class="about page  animate__animated animate__fadeIn">
    <h2>Recent Projects</h2>
    <div class="container">
      <div class="row" v-for="(project, index) in projects" :key="index">
        <div class="col-md-5">
          <img
            :src="project.image_cover"
            :alt="project.title"
            class="project-cover"
          />
        </div>
        <div class="col-md-5">
          <h2 class="mt-3" style="text-align: left;">
            {{ project.title }}
            <hr class="dope" />
          </h2>
          <b-card class="mt-3 mb-3 text-left text-dark">
            <p>{{ project.description }}</p>
            <hr />
            <b-link :href="project.github_url"
              >View source code <GithubIcon style="color: #000;"
            /></b-link>
          </b-card>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import LinkIcon from "vue-ionicons/dist/md-link.vue";
import GithubIcon from "vue-ionicons/dist/logo-github.vue";

export default {
  components: {
    GithubIcon,
    LinkIcon
  },
  data() {
    return {
      projects: [
        {
          title: "Palhost",
          tag: "Palworld Client Server",
          description:
            "Web for Palworld Client Server hosting and configurations.",
          image_cover: require("@/assets/palhost_1.png"),
          github_url: "https://github.com/upeel/palhost/",
        },
        {
          title: "SSL Certificate",
          tag: "Manage domains",
          description:
            "A Web for managing DNS, domains, and SSL Certificate",
          image_cover: require("@/assets/xxl.png"),
          github_url: "https://github.com/upeel/ssl-cert/",
        },
        {
          title: "Retail Order",
          tag: "Online ordering web",
          description:
            "Order your favorite stuff in your favorite outlets",
          image_cover: require("@/assets/antarinbarang.png"),
          github_url: "https://github.com/upeel/retail",
        },
        {
          title: "Backoffice",
          tag: "Backoffice for Point of Sales",
          description:
            "It's easier to manage your Business in beautiful backoffice UI",
          image_cover: require("@/assets/olsera.png"),
          github_url: "https://github.com/upeel/frontend-olseraV2-issue-935",
        }
      ],
    };
  },
  methods: {
    isEven(n) {
      if (n % 2 == 0) {
        return true;
      } else {
        return false;
      }
    }
  },
  head: {
    title: "Recent Projects 💻 - Muh Wildan",
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          "View all the recents open-sourced projects built with ♥ by Muh Wildan, open-sourced means this project source code are publicly available for everyone to use or modify."
      },
      {
        hid: "og:title",
        name: "og:title",
        content: "Recent Projects 💻 - Muh Wildan"
      },
      {
        property: "og:description",
        content:
          "View all the recents open-sourced projects built with ♥ by Muh Wildan, open-sourced means this project source code are publicly available for everyone to use or modify."
      },
      {
        hid: "og:image",
        name: "og:image",
        content: require("@/assets/man-computer.png")
      }
    ]
  }
};
</script>
<style scoped>
.row {
  margin-top: 70px;
}
.project-cover {
  width: inherit;
  border-radius: 3px;
}
hr.dope {
  border: 0;
  width: 90px;
  border-top: 2px solid #dc3545;
  text-align: left;
  margin: initial;
  margin-top: 7px;
  margin-left: 5px;
}
</style>
