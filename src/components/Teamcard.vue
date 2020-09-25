<template>
    <div class="team-member" :class="even(index)? '':'reverse'">
        <g-image src="~/assets/placeholderphoto.png" class="team-profile-photo" width="240"/>
        <div class="team-profile-text">
            <h4>{{name}}</h4>
            <p class="subtitle">{{degree}}</p>
            <h5>{{title}}</h5>
            <p class="team-member-bio">{{bio}}</p>
        </div>
    </div>

</template>

<script>
import Teamcard from "~/components/Teamcard.vue"

export default {
  metaInfo: {
    title: 'About us'
  },
  data() {
    return {
      showFront: true,
    }
  },
  props: {
        index: Number,
        name: String,
        title: String,
        degree: String,
        bio: String,
        photo: Object
  },
  methods: {
      even(i) {
          console.log('hello', i, i%2 == 0);
          return i%2 == 0;

      }
  }
}
</script>

<style lang="scss">

.team-member {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    border-bottom: 4px solid #1e2e4d;
    padding: 32px 0;
    &.reverse {
        flex-direction: row-reverse;
        .team-profile-text {
            text-align: right;
        }
        .team-profile-photo {
            margin-inline-start: 28px;
        }
    }
    .team-profile-photo {
        border-radius: 50%;
        margin-inline-end: 28px;
        }
    .team-profile-text {
        max-width: 60%;
        h4 {
            font-size: 18px;
            line-height: 26px;
            margin-bottom: 4px;
            font-family: "Open Sans", sans-serif;
        }
        .subtitle {
            margin: 0;
            font-size: 13px;
            color: #4d4d4d;
            line-height: 13px;
        }
        h5 {
            font-size: 16px;
            font-family: "Hind";
        }
    }
    .team-member-bio {

    }
}
.team-member:last-child {
    border-bottom: none;
}
</style>
