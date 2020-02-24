<template>
  <section>
    <nav class="navbar navbar-expand-lg navbar-light bg-white shadow-sm">
      <a class="navbar-brand text-dark" href="#">Shuffle</a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ml-auto d-flex">
          <li
            v-for="(item, index) in items"
            :key="index"
            :class="{ active: item.active, dropdown: item.sub }"
            class="nav-item"
          >
            <a :href="item.src" class="nav-link">
              {{ item.text | capitalize }}
              <i v-if="item.sub" class="fa fa-chevron-down ml-1"></i>
            </a>
            <ul v-if="item.sub" class="border-0 rounded-0 shadow-sm">
              <li v-for="(sub, subIndex) in item.sub" :key="subIndex">
                <a :href="sub.src">{{ sub.text }}</a>
              </li>
            </ul>
          </li>
        </ul>
      </div>
    </nav>
  </section>
</template>

<style lang="scss" scoped>
@import "@/main.scss";

nav.navbar {

  .navbar-brand {
    font-weight: bold;
  }

  .nav-item {
    font-weight: normal;
    font-size: 12px;
    padding-left: 1rem;

    ul {
      position: absolute;
      width: max-content;
      height: auto;
      padding: 1.5rem 0;
      background: white;
      list-style-type: none;

      visibility: hidden;
      opacity: 0;

      li {
        padding: 1px 5rem 1rem 1.5rem;

        a {
          text-decoration: none;
        }
      }
    }

    .nav-link {
      transition: 0.2s;
    }

    &.active .nav-link {
      color: $primary-color;
    }

    &:hover {
      ul {
        visibility: visible;
        opacity: 1;
      }

      .nav-link {
        color: $primary-color;
      }
    }
  }
}
</style>

<script type="text/javascript">
export default {
  data() {
    const items = [
      {
        src: "#",
        text: "Home",
        active: true,
      },
      {
        src: "#",
        text: "About us",
        active: false,
      },
      {
        src: "#",
        text: "Services",
        active: false,
      },
      {
        src: "#",
        text: "Portfolio",
        active: false,
      },
      {
        src: "#",
        text: "Team",
        active: false,
      },
      {
        src: "#",
        text: "Dropdown",
        active: false,
        sub: [
          {
            src: "#",
            text: "Drop Down 1",
          },
          {
            src: "#",
            text: "Drop Down 2",
          },
          {
            src: "#",
            text: "Drop Down 3",
            sub: [
              {
                src: "#",
                text: "Sub Drop Down 1",
              },
              {
                src: "#",
                text: "Sub Drop Down 2",
              }
            ]
          }
        ]
      },
      {
        src: "#",
        text: "Contact us",
        active: false,
      }
    ];

    return {
      items
    };
  },
  filters: {
    capitalize(value) {
      if (!value) return "";
      value = value.toString();
      return value.toUpperCase();
    }
  },
};
</script>