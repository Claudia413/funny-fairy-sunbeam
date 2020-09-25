<template>
  <div class="layout">
    <header class="menubar">
      <div class="container header">
      <g-image src="~/assets/tjplogo.png" width="240" />
      <nav class="nav">
        <g-link class="nav__link" to="/">Home</g-link>
        <g-link class="nav__link" to="/about/">About</g-link>
        <g-link class="nav__link" to="/treatments">Treatments</g-link>
        <g-link class="nav__link" to="/news">News</g-link>
      </nav>
      </div>
    </header>
    <main>
    <slot/>
    </main>
    <footer>
      <div class="container footer">
        <section class="hours">
          <strong><p>Opening hours</p></strong>
          <p>Monday: 7am -8pm</p>
          <p>Tuesdag: 7am -8pm</p>
          <p>Wednesday: 7am -8pm</p>
          <p>Thursday: 7am -8pm</p>
          <p>Friday: 7am -8pm</p>
          <p>Saturday: closed</p>
          <p>Sunday: closed</p>
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
.layout {
  width: 100%;
  margin: 0;
  box-sizing: border-box;
}

.container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 80px;
}

.menubar {
    background-color: #3e5c9a;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 8px 80px;
  height: 80px;
}

.nav__link {
  margin-left: 20px;
  color: white;
  cursor: pointer;
  text-decoration: none;
}

footer {
    background-color: #1e2e4d;
}

.footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 80px;
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
