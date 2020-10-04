<template>
  <Layout>
    <section class="section navigation">
      <div class="container sub-navigation">
        <a class="section-link" href="#what-is"><h6>What is Physiotherapy?</h6></a>
        <a class="section-link" href="#treatments"><h6>When can we help?</h6></a>
        <a class="section-link" href="#techniques"><h6>How do we help?</h6></a>
        <a class="section-link" href="#what-to-expect"><h6>What to expect?</h6></a>
      </div>
    </section>

    <section class="section what-is" id="what-is">
      <div class="container">
        <h2 class="emphasize green">What is Physiotherapy?</h2>
        <p>Physiotherapy is a medical profession which aims to speed up your recovery from injury, prevent injuries from occurring in the future and keep you healthy and fit.</p>
        <p>We at Tower Junction Physio know how the body works and our aim is to get your body to work as efficiently as it can to allow you to have a good quality of life.  This may involve teaching you about correct posture and positioning when you perform your normal daily activities, work tasks or sporting endeavours.</p>
        <p>Treatment is tailored specifically for each individual which is dependent on what the problem is.  We will get you to tell us about your injury and show us what movements hurt.  In addition we will ask you to perform a range of other movements too before we come to a conclusion and discuss a plan of how to fix the problem.</p>
        <p><strong>One important thing to note is that getting an injury or pain assessed early often results in a faster recovery.</strong></p>
        <p>Unfortunately sometimes injuries may be very severe and we may need to send you for X-rays, scans or to other Medical Specialists to help with your recovery.</p>
      </div>
    </section>

    <section class="section treatments" id="treatments">
      <div class="container">
        <h2 class="emphasize green">When can we help?</h2>
        <p>At Tower Junction Physio we specialise in:</p>
        <div class="card-grid">
          <div class="category-card">
            <Doctor size="43" class="treatment-icon" />
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
            <EmoticonHappyOutline size="43" class="treatment-icon" />
            <h4>Relieving pain</h4>
            <ul>
              <li>Back pain</li>
              <li>Neck pain</li>
              <li>Headaches</li>
            </ul>
          </div>
          <div class="category-card">
            <WeightLifter size="43" class="treatment-icon" />
            <h4>Correction</h4>
            <ul>
              <li>Muscle imbalance</li>
              <li>Soft tissue management</li>
              <li>Manual lifting techniques</li>
              <li>Correction of movement patterns</li>
              <li>Core strength and gluteal activation</li>
              <li>Exercise prescription for strength and endurance</li>
            </ul>
          </div>
          <div class="category-card">
          <ClipboardAccountOutline size="43" class="treatment-icon" />

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

    <section class="section techniques" id="techniques">
      <div class="container">
        <h2 class="emphasize green">How can we help?</h2>
        <div class="technique-grid">
          <p v-for="(technique, index) in techniques" class="button" :key="technique.technique" :class="techniqueIndex==index?'active':''" @click="techniqueIndex = index">
            {{technique.technique}}
          </p>
        </div>
        <div class="technique-description">
              <transition name="faderesize" mode="out-in">
              <h6 :key="techniques[techniqueIndex].technique">{{techniques[techniqueIndex].technique}}</h6>
              </transition>
              <transition name="faderesize" mode="out-in">
              <p :key="techniques[techniqueIndex].description">{{techniques[techniqueIndex].description}}</p>
          </transition>
        </div>
        <div class="technique-accordion">
          <div v-for="(technique, index) in techniques" class="accordion-container" :key="technique.technique" >
            <div class="accordion-button" :class="techniqueIndex == index?'active':''"
            @click="setTechniqueShown(index)">
            {{technique.technique}} <ChevronDown class="chevron" />
            </div>
            <div class="accordion-card" :class="techniqueIndex == index?'active':''" >
              <div class="content">
              <p>{{techniques[techniqueIndex].description}}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section what-to-expect" id="what-to-expect">
      <div class="container">
        <h2 class="emphasize green">What to expect?</h2>
        <p>We offer individual personalised care in a comfortable and relaxing environment. All treatments are carried out in individual rooms and all our staff share a commitment to provide patients with the highest possible standard of treatments and service.</p>
        <p>As a Tower Junction Physio patient, we want you to progress as rapidly as possible and we are committed to helping you.  We offer a follow up service between appointments if necessary, and also encourage self-help; the more you can do at home the better.</p>
        <p>We work closely with General Practitioners as well as Sports Medicine, Musculoskeletal and Orthopaedic Specialists.  We can refer directly to the appropriate specialist as well as arrange for you to have X-Rays or Ultrasound Scans as necessary.</p>
        <p>We understand that your time is valuable.  We try to adhere strictly to appointment times, and as we do not overload our appointment schedule you know you will receive our full attention throughout your visit.</p>
      </div>
    </section>

  </Layout>
</template>

<script>
import WeightLifter from "mdi-vue/WeightLifter.vue";
import Doctor from "mdi-vue/Doctor.vue";
import ClipboardAccountOutline from "mdi-vue/ClipboardAccountOutline.vue";
import EmoticonHappyOutline from "mdi-vue/EmoticonHappyOutline.vue";
import ChevronDown from "mdi-vue/ChevronDown.vue";

export default {
  metaInfo: {
    title: 'About us'
  },
  data() {
    return {
      techniqueIndex: 0,
      techniques: [{
        technique: 'Education',
        description: 'Education is where we provide you with an understanding of what you have injured, why it is injured, how to fix the injury and how to stop it from happening again. If you understand all these aspects it gives you the ability to control your life better and in a safer way.'},
        {technique: 'Manipulation',
        description: 'Manipulation means moving joints and the soft tissues such as ligaments and muscles around joints. Techincally manipulation means moving joints in a specific safe way to make them "click" which reduces tension and increases flexibility around those joints.  This technique is often performed in the back and neck. We only use manipulation when necessary and appropriate and we will discuss this option with you first. We mainly utilise joint mobilisation in our treatments which is similar to manipulation but more gentle. Mobilisation is also very effective in reducing tension and increasing flexibility around joints.'},
        {technique: 'Strengthening',
        description: 'Strengthening is where we will direct you to perform an activity or exercise to increase specific muscle strength.  These exercises may be aimed at getting individual muscles stronger to correct posture or rehabilitate muscles that have been damaged or become weak from an injury or lack of use. The exercise may involve using rubber bands, weights like at a gym, using your body weight or using equipment such as swiss ball.'},
        {technique: 'Stretching',
        description: "Stretching describes techniques where we try to create better flexibility. Being inflexible does not mean you are unfit.  Over time your body adapts to the activities you do.  If you use your muscles lots in the same way but don't stretch you may become tight in certain muscles and this may lead to muscle imbalance which can lead to injuries. Stretching muscles involves holding postures or positions for half a minute or so, to put the tissues on 'stretch'.  Stretching or lengthening muscles however takes time.  The 'stretch' provides the signal to your body to grow more length in that particular muscle.  So the stretch has to be performed frequently to tell your muscle it needs to grow. Like muscles, nerves too can become tight- again we may specify nerve stretches similar to muscle stretches to get you to grow longer nerves in order to correct your injury and/or reduce your pain and symptoms."},
        {technique: 'Muscle Balance',
        description: 'Muscle balance involves correcting strength and flexibility of muscles that either work together or against each other.  Correcting muscle balance helps correct posture and can reduce the chance of further injury. The main principal of correct muscle balance is to make your body mechanically efficient and to reduce stress on your soft tissues and joints.'},
        {technique: 'Acupuncture',
        description: 'What is Acupuncture and how does it work? Acupuncture is a treatment devised by the Ancient Chinese to cure disease and injury. It involves inserting extremely fine needles into areas of the body. Acupuncture has been used in Asia for 5000 years, and now it is being widely used in western medicine. Western medicine research has shown that acupuncture alters body functions acting through the nervous system. This leads to the release of substances which promote healing, restore balance in body systems and relieve pain. What does Acupuncture treatment feel like? Acupuncture is not like getting an injection. The extremely fine needles used are often hardly felt while being inserted. However, you may feel a small prick sensation on insertion of the needle, and get a deep or dull ache around the needle. There is a chance you may get a twitch of the muscle the needle is inserted into. Most people experience no side effects at all, however, you may feel tired or sleepy after treatment, and there is a slight possibility of having a small bruise in the area where the needle was inserted. A small number of people do not respond significantly to acupuncture, but the majority will get some relief. Acupuncture is safe and natural, but if you are pregnant, or are a haemophiliac, have hepatitis or are H.I.V. positive please let us know. What is the procedure for Acupuncture? A number of sterile single use needles (usually around 4 to 8) will be inserted into your skin at various places. Sometimes a needle may be inserted well away from the pain, or even in your ear. The needles may be stimulated by twisting them but often they are left alone. The needles are left in place for a length of time that may vary from less than a minute, up to 30 minutes, depending on the effect that is sought. The needles are then removed and disposed of in a special container, which will be incinerated.'},
        {technique: 'Strapping tape',
        description: "Why use Tape? Rigid tape is used to support a joints or muscles, or to restrict movement and provide feedback to the patient regarding their body position/posture. Flexible tape may also be used to assist in educating the muscles to work correctly to stabilise joints or assist in taking pressure off joints or muscles and allow normal posture and function. Things to be aware of when using tape. You will be asked if you know of any allergy to tape e.g. reaction to sticking plasters. If you report such allergies in the past, then tape will probably not be used on you. If tape is used and you are unhappy with it in any way e.g. itching or burning, please remove the tape. To remove the tape you can try soaking it first e.g. in a shower, and to peel it off slowly with the tape parallel to the skin (not 90 degrees) to prevent tearing of the skin. If you have a mild reaction to the tape it is best to wash the area with water only, not soap as this may increase the reaction."},
        {technique: 'Ultrasound',
        description: " What is Ultrasound? Ultrasound transmits ultrasonic waves or sound waves. These travel poorly through the air and skin, so a gel is added to increase their absorption, this is placed on the surface of your skin. Ultrasound may be ‘continuous’, resulting in an uninterrupted flow of energy/sound waves, or ‘pulsed’, intermittent interruption of the sound waves. If the ultrasound head is placed in water we can see ripples produced in the water. Most people have heard of diagnostic ultrasound such as that used in pregnancy scans.  This is a similar machine to ours but it has a lower ultrasound intensity and it records the sound waves that bounce back off tissues to create pictures inside the body.  Our machines are some of the newest available on the market.What does Ultrasound do? Ultrasound effects the cells and tissues lying under the skin. The sound waves stimulate the cells, which increases their activity rate. Therefore it ‘kick starts’ the body into healing quicker. It does this through increasing local blood flow, increased cell activity, increased extensibility (the ‘stretchiness’) of tissue, reduced pain, and massaging the tissues under the skin. What you should feel: Generally you will just feel the ultrasound head being massaged across your skin surface. You may feel local warmness under the ultrasound head. Please inform the Physiotherapist if you feel anything other than this i.e. uncomfortable heat, burning pain."},
        {technique: 'Cryotherapy (ice)',
        description: 'What does Ice do?: Application of ice results in changes in the skin, subcutaneous, intramuscular and joint temperature. A decrease in tissue temperature causes a constriction/closing of local blood vessels. This can cause a reduction in swelling that is associated with inflammation and bleeding, thus it can cause a reduction in pain and muscle spasm. Ice should be applied for 15-20 minutes every 1-2 hours following a soft tissue injury. What you should feel: It will feel cold and slightly achy until it goes numb. If it becomes too cold or painful it may cause an ice burn to the skin so care must be taken to avoid this.'},
        {technique: 'Superficial heat (hot pack)',
        description: "Heat is used for pain reduction and promotion of healing. The increased temperature results in an increased blood supply and therefore enhances healing. It may also increase nerve conduction speed, reduce pain, reduce muscle spasm and increase extensibility of tissue (the ability of the tissue to stretch). Make sure you don't burn yourself at home."},
        {technique: 'EMG Biofeedback',
        description: " What is EMG Biofeedback? EMG stands for electromyography, this means the measurement of electrical activity coming from muscles that are working. This device detects and amplifies the electric signal given off from a contracting muscle. These signals are very small and so this machine is very sensitive. When you do a particular task the machine will then tell us which muscles are working, how much they are working and when they are working.The machine can have either one or two recording electrodes. What you will feel: You will feel nothing abnormal when using this machine, as it only records what your muscles are already doing. The recording electrodes may have gel on them and then they may have to be taped onto the skin to maintain a good electrical contact"},
      ]
    }
  },
  components: {
    WeightLifter,
    Doctor,
    ClipboardAccountOutline,
    EmoticonHappyOutline,
    ChevronDown
  },
  methods: {
    setTechniqueShown(techniqueId) {
      if (this.techniqueIndex == techniqueId) {
        console.log("write code to close the accordion")
      } else {
        this.techniqueIndex = techniqueId
      }
    }
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
.sub-navigation {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  flex-wrap: wrap;
  column-gap: 16px;
  h6 {
    border-bottom: 4px solid #99cc00;
    padding-bottom: 4px;
    cursor: pointer;
    font-size: 16px;
    line-height: 33px;
    color:  #1e2e4d;
    font-weight: 600;
    margin: 0;
  }
  .section-link {
    text-decoration: none;
    margin: 16px 0;
  }
}
.section {
  margin-bottom: 64px;
}
.card-grid {
  display: flex;
  flex-flow: wrap;
  column-gap: 8px;
  row-gap: 32px;
  justify-content: space-between;

}
.category-card {
  width: 22%;
  height: auto;
  box-sizing: border-box;
  background-color: white;
  padding: 16px 12px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  border: 1px solid #1e2e4d1a;
  h4 {
    font-family: "Open Sans", Helvetica, sans-serif;
    color: #99cc00;
    margin: 24px 0;
  }
  ul {
    text-align: center;
    margin: 0;
    padding-inline-start: 0;
  }
  li {
    font-size: 14px;
    list-style-type: none;
    line-height: 30px;
  }
  .treatment-icon {
    color: #1e2e4d;
    margin-top: 24px;
  }
  @media screen and(max-width:1024px) {
    width: 45%;
  }
}
.technique-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
  column-gap: 16px;
  max-width: 80%;
  margin: 0 auto;
   @media screen and(max-width: 911px) {
     column-gap: 8px;
     max-width: 80%;
   }
   @media screen and(max-width: 890px) {
     display: none;
   }
}
.button {
  display: inline-block;
  border: 1px solid #1e2e4d1a;
  padding: 12px 32px;
  margin-right: 20px;
  cursor: pointer;
  transition: background-color 0.3s ease;
  &.active {
    background-color:#99cc00;
    color: white;
    border-color:#99cc00;
  }
}
.technique-description {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px 0;
  h6 {
    color: #99cc00;
    font-size: 20px;
    line-height: 32px;
    margin: 0;
  }
  @media screen and(max-width: 890px) {
     display: none;
   }
}
.technique-accordion {
  display: none;
  .accordion-button {
    width: 100%;
    background-color: white;
    padding: 8px;
    border: 1px solid #1e2e4d1a;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    transition: all 0.2s ease-out;
    &:hover {
      font-weight: 600;
      color: #99cc00;
    }
    &.active {
      color: #99cc00;
      font-weight: 600;
      .chevron {
        transform: rotate(180deg);
      }
    }
    .chevron {
      display: inline-block;
      transition: all 0.3s ease-in-out;
    }
  }
  .accordion-card {
    height: 0;
    overflow: hidden;
    visibility: hidden;
    transition: all 0.4s ease-in-out;
    &.active {
      visibility: visible;
      height: auto;
      .content {
        display: block;
      }
    }
    .content {
      display: none;
      padding: 8px;
    }
  }
  @media screen and(max-width: 890px) {
     display: block;
   }
}

.faderesize-enter-active {
  transition: all 0.3s ease;
}
.faderesize-leave-active {
  transition: all 0.15s ease-in;
}

.faderesize-enter, .faderesize-leave-to {
  opacity: 0;
  height: auto;
}

</style>
