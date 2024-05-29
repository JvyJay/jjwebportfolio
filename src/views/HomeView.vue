<template>
  <div>
    <!-- HERO AREA -->
    <!-- DESKTOP VISIBILITY -->
    <section data-aos="zoom-in" class="my-5 d-none d-xl-block d-lg-block d-md-block d-md-block d-sm-none">
      <div class="d-flex flex-column align-items-center justify-content-center">
        <div class="d-flex flex-column align-items-xxl-start align-items-center text-xxl-start text-center w-25">
            <span class="span-color mb-2">Jadon Guzman - Web Developer/Designer</span>
            <div class="d-flex flex-row position-relative">
              <h1 class="fw-bold text-index">Tech Dabbler; Passion For The Arts<img width="15%" :src=code alt="Code Icon" /></h1>
              <img class="position-absolute top-100 bottom-0 start-0 translate-middle banner-index" width="120px" :src=designbanner alt="Design Banner" />
            </div>
        </div>
        <div class="d-flex flex-column align-items-xxl-end justify-content-xxl-end align-items-center text-xxl-end text-center text-justify right-aligned w-25">
          <p class="grey-text text-index text-xxl-end text-center">If you consider me I'll teach you Muay Thai, & will make you an album; please I'm starving in this economy. Is an appeal to help a bad strategy? Who knows, but I bet you slightly exhaled out of your nose reading this &#x1F609;</p>
          <button class="primary-button fw-medium" @click="sendEmail">
            <img width="10%" :src=mail alt="Mail Icon" />
            Contact
          </button>
        </div>
      </div>
    </section>
    <!-- TABLET/ MOBILE VISIBILITY -->
    <section data-aos="zoom-in" class="my-5 container d-xl-none d-lg-none d-md-none w-100">
      <div class="d-flex flex-column justify-content-center align-items-center text-center">
        <span class="span-color mb-2">Jadon Guzman - Web Developer/Designer</span>
          <h2 class="fw-bold mobile-friendly">Tech Dabbler; Passion For The Arts</h2>
          <button class="primary-button fw-medium" @click="sendEmail">
            <img width="10%" :src=mail alt="Mail Icon" />
            Contact
          </button>
        </div>
    </section>
    <!-- HERO AREA END -->

    <!-- PROJECT SHOWCASE -->
    <!-- DESKTOP VISIBILITY -->
    <section class="container d-flex justify-content-center align-items-center mt-5 mx-5 flex-column d-none d-xl-block">
      <h1 data-aos="fade-right"><span class="outline-text">Project Showcase </span></h1>
      <!-- TOP SECTION/GRID -->
      <div class="project-container">
         <ProjectCard
         data-aos="flip-down"
         v-for="project in projects"
         :key="project.id"
         :title="project.title"
         :image="project.image"
         :desc="project.desc"
         :link="project.link"
         />
      </div>
      <!-- BOTTOM SECTION -->
      <div class="d-flex flex-row justify-content-center align-items-start bottom-container ">
        <img data-aos="fade-right" class="mb-5" width="15%" :src=friendspicks alt="Friends Picks Badge" />
        <ProjectCard
        data-aos="flip-up"
        :key="bottomProject.id"
        :title="bottomProject.title"
        :image="bottomProject.image"
        :desc="bottomProject.desc"
        :link="bottomProject.link"
        />
      </div>
    </section>
    <!-- TABLET - PHONE VISIBILITY -->
    <section class="container d-flex justify-content-center align-items-center flex-column mx-auto d-xl-none">
      <h2 data-aos="fade-right"><span class="outline-text">Project Showcase </span></h2>
      <!-- TOP SECTION/GRID -->
      <div class="container d-flex justify-content-center align-items-center flex-row flex-wrap mt-5 mx-auto">
         <ProjectCard
         data-aos="flip-down"
         v-for="project in projects"
         :key="project.id"
         :title="project.title"
         :image="project.image"
         :desc="project.desc"
         :link="project.link"
         />
      </div>
      <!-- BOTTOM SECTION -->
      <div class="d-flex flex-row justify-content-center align-items-start">
        <img data-aos="fade-right" class="mb-5 d-none d-lg-block d-xl-none img-fluid" width="50%" :src=friendspicks alt="Friends Picks Badge" />
        <ProjectCard
        data-aos="flip-up"
        :key="bottomProject.id"
        :title="bottomProject.title"
        :image="bottomProject.image"
        :desc="bottomProject.desc"
        :link="bottomProject.link"
        />
      </div>
    </section>
    <!-- PROJECT SHOWCASE END -->

    <!-- CONTACT & SERVICES SECTION -->
    <section class="container my-5">
      <h2 data-aos="fade-right" class="text-lg-start text-center"><span class="outline-text">Contact & Services</span></h2>
      <div class="d-flex flex-lg-row justify-content-lg-start align-items-lg-center flex-column justify-content-center align-items-center">
        <div data-aos="fade-up-left" class="d-flex flex-column justify-content-lg-start align-items-lg-start justify-content-center align-items-center text-lg-start text-center colored-card m-5 p-4">
          <h4 class="text-dark">I`m Building UI Layouts & Functional Interfaces </h4>
          <p class="text-dark fw-normal">Focused on functional, but fluid UI/UX experiences for startups to thriving businesses</p>
          <hr class="text-dark" width="100%">
          <button class='primary-button fw-medium'>About</button>
        </div>
        <div data-aos="fade-up-right" class="w-50 d-flex flex-column justify-content-lg-start align-items-lg-start justify-content-center align-items-center text-lg-start text-center">
          <span class="span-color">Contact</span>
          <h2>Want To Learn More? Let`s Get Started</h2>
          <p>feel free to reach out on Linkedin, or via Email!</p>
          <button class="primary-button fw-medium" @click="sendEmail">
            <img width="10%" :src=mail alt="Mail Icon" />
            Contact
          </button>
        </div>
      </div>
    </section>
    <!-- CONTACT & SERVICES SECTION END -->
    
    <!-- FOOTER -->
    <FooterNav />
  </div>
</template>

<script>
// IMAGES
import project1 from '../assets/project1.png';
import project2 from '../assets/project2.png';
import project3 from '../assets/project3.png';
import project4 from '../assets/project4.png';
import code from '../assets/Code.svg';
import mail from '../assets/mail.svg';
import designbanner from '../assets/design-banner.svg';
import friendspicks from '../assets/FriendsPicks.svg';
// COMPONENTS
import ProjectCard from '../components/Project-Card.vue';
import FooterNav from '../components/FooterNav.vue';

export default {
  name: "HomeView",
  components: {
    ProjectCard,
    FooterNav
  },
  data() {
    return {
      // IMAGE DATA
      code: code,
      mail: mail,
      designbanner: designbanner,
      friendspicks: friendspicks,

      // PROJECT DATA
      projects: [
        {
          id: 1,
          title: 'Web Agency',
          image: project1,
          desc: 'Personal Project: Local Seattle agency inspired me, so I felt like doing a redesign of their website.',
          link: 'https://web-agency-vs7d.vercel.app/'
        },
        {
          id: 2,
          title: 'Achilles Collective',
          image: project2,
          desc: `Personal Project: A meetup group, passion project--that's one of a couple reasons why I'm trying so hard to get into the I.T industry at the moment; still in the works, but I plan on investing more into this project as a whole once I'm more settled into my career (please hire me; I'll train you for free!)`,
          link: 'https://achilles-collective.vercel.app/'
        },
        {
          id: 3,
          title: 'jjvy Artist Website',
          image: project3,
          desc: 'Personal Project: My other passion! Feel free to checkout my music!',
          link: 'https://jjvy.netlify.app/#/'
        }
      ],
      bottomProject: {
          id: 4,
          title: '33 Strategies',
          image: project4,
          desc: 'Personal Project: I read Robert Greene; felt like making a summarized website of the strategies; this is the result.',
          link: 'https://33-strategies-of-war.now.sh/'
        },
    }
  },
  methods: {
    sendEmail() {
      window.location.href = 'mailto:jadonbguzman@tutanota.com';
    }
  }
};
</script>

<style scoped>
/* HERO AREA TEXT */
.right-aligned {
  text-align: right !important;
}

.text-index {
  z-index: 1;
}

.banner-index {
  z-index: 0;
}

.mobile-friendly {
  font-size: 2rem !important;
}

/* PROJECT CONTAINER */
.project-container {
  justify-content: center;
  align-items: center;
  display: grid;
  column-gap: 50px;
  row-gap: 50px;
  justify-content: center;
}
.project-container div:nth-child(1) {
  /* width: 70%; */
  grid-column-start: 1;
  grid-column-end: 2;
  grid-row-start: 1;
  grid-row-end: 1;
}

.project-container div:nth-child(2) {
  /* width: 80%; */
  grid-column-start: 2;
  grid-column-end: 2;
  grid-row-start: 1;
  grid-row-end: 2;
}

.project-container div:nth-child(3) {
  width: 50%;
  grid-column-start: 1;
  grid-column-end: 3;
  grid-row-start: 2;
  grid-row-end: 2;
  place-self: center;
}

.project-container div:nth-child(4) {
  /* width: 30%; */
  grid-column-start: 1;
  grid-column-end: 2;
  grid-row-start: 3;
  grid-row-end: 3;
}

/* BOTTOM PROJECT CONTAINER */
.bottom-container {
  margin-top: 50px;
  margin-bottom: 50px;
}
.bottom-container div {
  width: 40%;
}
</style>
