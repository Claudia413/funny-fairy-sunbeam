<template>
  <Layout>

<section class="container whatis">
      <h2 class="emphasize green">What is Physiotherapy?</h2>
      <p>Physiotherapy is a medical profession which aims to speed up your recovery from injury, prevent injuries from occurring in the future and keep you healthy and fit.</p>
      <p>We at Tower Junction Physio know how the body works and our aim is to get your body to work as efficiently as it can to allow you to have a good quality of life.  This may involve teaching you about correct posture and positioning when you perform your normal daily activities, work tasks or sporting endeavours.</p>
      <p>Treatment is tailored specifically for each individual which is dependent on what the problem is.  We will get you to tell us about your injury and show us what movements hurt.  In addition we will ask you to perform a range of other movements too before we come to a conclusion and discuss a plan of how to fix the problem.</p>
      <p><strong>One important thing to note is that getting an injury or pain assessed early often results in a faster recovery.</strong></p>
      <p>Unfortunately sometimes injuries may be very severe and we may need to send you for X-rays, scans or to other Medical Specialists to help with your recovery.</p>
    </section>

    <section class="what-to-expect">
      <div class="container">
        <h2 class="emphasize green">What to expect?</h2>
        <p>We offer individual personalised care in a comfortable and relaxing environment. All treatments are carried out in individual rooms and all our staff share a commitment to provide patients with the highest possible standard of treatments and service.</p>
        <p>As a Tower Junction Physio patient, we want you to progress as rapidly as possible and we are committed to helping you.  We offer a follow up service between appointments if necessary, and also encourage self-help; the more you can do at home the better.</p>
        <p>We work closely with General Practitioners as well as Sports Medicine, Musculoskeletal and Orthopaedic Specialists.  We can refer directly to the appropriate specialist as well as arrange for you to have X-Rays or Ultrasound Scans as necessary.</p>
        <p>We understand that your time is valuable.  We try to adhere strictly to appointment times, and as we do not overload our appointment schedule you know you will receive our full attention throughout your visit.</p>
      </div>
    </section>

    <section class="treatments">
      <div class="container">
        <h2 class="emphasize green">When can we help?</h2>
        <p>At Tower Junction Physio we specialise in:</p>
        <div class="card-grid">
          <div class="category-card">
            <h4>Injuries</h4>
            <ul>
              <li>Sports injuries</li>
              <li>General injuries from accidents</li>
              <li>Gradual Process injuries</li>
              <li>Work injuries</li>
              <li>Muscle and joint injuries</li>
            </ul>
          </div>
          <div class="category-card">
            <h4>Relieving pain</h4>
            <ul>
              <li>Back pain</li>
              <li>Neck pain</li>
              <li>Headaches</li>
            </ul>
          </div>
          <div class="category-card">
            <h4>Correction</h4>
            <ul>
              <li>Exercise prescription for strength and endurance</li>
              <li>Muscle imbalance</li>
              <li>Soft tissue management</li>
              <li>Manual lifting techniques</li>
              <li>Correction of movement patterns</li>
              <li>Core strength and gluteal activation</li>
            </ul>
          </div>
          <div class="category-card">
            <h4>Assessments</h4>
            <ul>
              <li>Correctly diagnosing your injury or pain</li>
              <li>Workplace assessments</li>
              <li>Ergonomic assessments</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <section class="techniques">
      <div class="container">
        <h2 class="emphasize green">How can we help?</h2>
        <div class="technique-grid">
          <p class="button active">Education</p>
          <p class="button">Strengthening</p>
          <p class="button">Stretching</p>
          <p class="button">Muscle balance</p>
          <p class="button">Manipulation</p>
          <p class="button">Ultrasound</p>
          <p class="button">Hot pack</p>
          <p class="button">Ice</p>
          <p class="button">EMG Biofeedback</p>
          <p class="button">Acupuncture</p>
          <p class="button">Strapping tape</p>
        </div>
      </div>
    </section>
  </Layout>
</template>

<script>
import Teamcard from "~/components/Teamcard.vue"
import TimelineEvent from "~/components/TimelineEvent.vue"

export default {
  metaInfo: {
    title: 'About us'
  },
  data() {
    return {
      technique: 'Education'
    }
  },
  components: {
    Teamcard,
    TimelineEvent
  }
}
</script>

<style lang="scss">
h2 {
  color:#333333;
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
    from {width: 0px;}
    to {width: 40px;}
    }
  }
}
.card-grid {
  display: flex;
  flex-flow: wrap;
  row-gap: 24px;
  column-gap: 24px;
}
.category-card {
  width: 45%;
  max-width: 50%;
  background-color: white;
  padding: 16px 20px;
  border: 1px solid #1e2e4d1a;
  h4 {
    font-family: "Open Sans", Helvetica, sans-serif;
    color: #99cc00;
    font-size: 16px;
  }
  li {
    font-size: 14px;
  }
}
.technique-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
  column-gap: 20px;
  max-width: 80%;
  margin: 0 auto;
}
.button {
  display: inline-block;
  border: 1px solid #1e2e4d1a;
  padding: 12px 32px;
  margin-right: 24px;
  cursor: pointer;
  transition: background-color 0.3s ease;
  &.active {
    background-color:#99cc00;
    color: white;
  }
}
</style>
