<template>
  <div class="layout">
    <header>
      <div class="container header">
      <g-image src="~/assets/tjplogo.png" width="240" />
      <nav class="nav">
        <g-link class="nav__link" to="/">Home</g-link>
        <g-link class="nav__link" to="/about/">About</g-link>
        <g-link class="nav__link" to="/treatments">Treatments</g-link>
      </nav>
      </div>
    </header>
    <slot/>
    <footer>
      <div class="container footer">
        <section class="hours">
          <p>Opening hours</p>
          <p>Monday: 7am -8pm</p>
          <p>Monday: 7am -8pm</p>
          <p>Monday: 7am -8pm</p>
          <p>Monday: 7am -8pm</p>
          <p>Monday: 7am -8pm</p>
          <p>Weekend: closed</p>
        </section>
        <section class="contact">
          <p>phone number and </p>
          <p>address</p>
        </section>
        <section class="location">
          <p>map picture with link to google</p>
        </section>
      </div>
    </footer>
  </div>
</template>

<style lang="scss">
body {
  font-family: "Open Sans", sans-serif;
  margin:0;
  padding:0;
  line-height: 1.5;
}

.layout {
  width: 100%;
  margin: 0;
  box-sizing: border-box;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

header {
    background-color: #3e5c9a;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 8px;
  margin-bottom: 20px;
  height: 80px;
}

.nav__link {
  margin-left: 20px;
  color: white;
  cursor: pointer;
  text-decoration: none;
}

footer {
    background-color: #2d426c;
}

.footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px;
  color: white;
  font-size: 13px;
  section {
    margin: 8px;
  }
  .hours {
    line-height: 1;
  }
}
</style>
