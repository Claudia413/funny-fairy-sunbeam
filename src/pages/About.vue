<template>
  <Layout>
    <!-- <section class="container location">
      <h2 class="emphasize green">Our location</h2> -->
    <!-- <div class="hours">
        <strong><p>Opening hours</p></strong>
        <p>Monday: 7am -8pm</p>
        <p>Tuesdag: 7am -8pm</p>
        <p>Wednesday: 7am -8pm</p>
        <p>Thursday: 7am -8pm</p>
        <p>Friday: 7am -8pm</p>
        <p>Saturday: closed</p>
        <p>Sunday: closed</p>
      </div> -->
    <!-- <div class="route">
        <g-image src="~/assets/map.jpg" alt="map of the crossing of Blenheim Road and Clarence street marking the location of the practise" class="map-image" width="400" />
        <g-image src="~/assets/towerjunctionphysiopractise.jpg" alt="map of the crossing of Blenheim Road and Clarence street marking the location of the practise" class="map-image" width="400" />
      </div> -->
    <!-- </section> -->

    <section class="mission">
      <div class="container">
        <h2 class="emphasize white">Our mission</h2>
        <p>
          Our mission is to provide patients seeking physiotherapy treatment in a professional, yet personal manner, and
          to provide the best available treatment utilising up to date physiotherapy practices.
        </p>
      </div>
    </section>

    <section class="history">
      <div class="container">
        <h2 class="emphasize green">History</h2>
        <div class="timeline">
          <TimelineEvent
            v-for="(event, index) in history"
            :key="event.index"
            :index="index"
            class="timeline-event"
            :year="event.year"
            :description="event.description"
          >
          </TimelineEvent>
        </div>
      </div>
    </section>
  </Layout>
</template>

<script>
import TimelineEvent from "~/components/TimelineEvent.vue";

export default {
  metaInfo: {
    title: "About us",
  },
  data() {
    return {};
  },
  components: {
    TimelineEvent,
  },
};
</script>

<style lang="scss">
h2 {
  color: #333333;
  &.emphasize {
    &:after {
      content: "";
      display: block;
      width: 40px;
      height: 4px;
      animation: show 0.4s ease forwards;
    }
    &.green {
      &:after {
        background-color: #99cc00;
      }
    }
    &.white {
      &:after {
        background-color: white;
      }
    }
    @keyframes show {
      from {
        width: 0px;
      }
      to {
        width: 40px;
      }
    }
  }
}
.grid-team {
  display: flex;
  flex-direction: column;
}
.mission {
  background-color: #add145;
  color: #4d4d4d;
  h2 {
    color: #1e2e4d;
  }
}
.team,
.mission,
.history {
  padding: 20px 0;
}
.timeline {
  margin-bottom: 40px;
}
</style>
