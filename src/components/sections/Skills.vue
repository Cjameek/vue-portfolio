<template>
  <div class="skills__container">
    <h2 class="skills__subtitle">This should be fun</h2>
    <ul class="skills__list">
      <li
        v-for="(skill, index) in skills"
        class="skills__list-item"
        :key="createSkillsIcons(skill.name)"
        :data-index="index"
      >
        <div class="skills__list-item--inner">
          <span class="skills__list-item--description">{{ skill.name }}</span>
          <i
            :class="
              `skills__list-item--icon icon-${createSkillsIcons(skill.name)}`
            "
            aria-hidden="true"
          ></i>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Skills",
  data() {
    return {
      skills: [
        {
          name: "Adobe XD"
        },
        {
          name: "Adobe Photoshop"
        },
        {
          name: "Adobe Illustrator"
        },
        {
          name: "mySQL"
        },
        {
          name: "Wordpress"
        },
        {
          name: "PHP"
        },
        {
          name: "React"
        },
        {
          name: "Vue"
        },
        {
          name: "JavaScript"
        },
        {
          name: "CSS"
        },
        {
          name: "HTML5"
        }
      ]
    };
  },
  methods: {
    createSkillsIcons: function(name) {
      return name.replace(/\s/g, "").toLowerCase();
    },
    createRing: function() {
      const items = document.querySelectorAll(".skills__list-item");
      items.forEach((item, index) => {
        return (item.style.transform = `rotate(${(360 / this.skills.length) *
          index}deg) translate(-250px)`);
      });
    },
    reverseInsideRing: function() {
      const items = document.querySelectorAll(".skills__list-item");
      const reverseItems = Object.assign([], items).reverse();
      reverseItems.forEach((item, index) => {
        const innerWrap = item.querySelector(".skills__list-item--inner");

        return (innerWrap.style.transform = `rotate(${(360 /
          this.skills.length) *
          index}deg)`);
      });
    },
    rotateRing: function() {
      const ring = document.querySelector(".skills__list");
      return (ring.style.transform = `rotate(${360 / this.skills.length}deg)`);
    },
    cssRingVars: function() {
      let root = document.documentElement;

      for (var i = 0; i < this.skills.length; i++) {
        root.style.setProperty(
          `--ring-pos-${i}`,
          `${(360 / this.skills.length) * i}`
        );
      }
    }
  },
  mounted() {
    this.createRing();
    this.reverseInsideRing();
    this.rotateRing();
    this.cssRingVars();
  }
};
</script>

<style lang="scss">
.skills {
  &__container {
    display: flex;
    flex-direction: column;
  }

  &__list {
    position: relative;
    width: 600px;
    height: 600px;

    &-item {
      position: absolute;
      top: 50%;
      left: 50%;

      &--inner {
        position: relative;
        background-color: #fff;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100px;
        height: 100px;
        font-size: 50px;
        text-align: center;

        &:after {
          content: "";
          display: block;
          position: absolute;
          top: 0;
          left: 0;
          width: 100%;
          height: 100%;
          box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
          transform: scale(1);
          opacity: 0.6;
          transition: transform 350ms cubic-bezier(0.175, 0.885, 0.32, 1.275),
            opacity 350ms cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        &:hover:after {
          opacity: 1;
          transform: scale(1.1);
        }
      }

      &--description {
        position: absolute;
        z-index: -1;
        width: 1px;
        height: 1px;
        visibility: hidden;
        overflow: hidden;
        pointer-events: none;
      }
    }
  }
}
</style>
