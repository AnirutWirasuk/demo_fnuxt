<template>
  <div>
    <div
      class="d-flex flex-column flex-md-row align-items-center p-3 px-md-4 mb-3 bg-white border-bottom shadow-sm"
    >
      <h5 class="my-0 mr-md-auto font-weight-normal">Company name</h5>
      <nav class="my-2 my-md-0 mr-md-3">
        <nuxt-link to="/" class="p-2 text-dark">Home</nuxt-link>
        <nuxt-link to="/blog" class="p-2 text-dark">Blog</nuxt-link>
        <nuxt-link to="/member" class="p-2 text-dark">Member</nuxt-link>
        <nuxt-link to="/authen" class="p-2 text-dark">Login</nuxt-link>
      </nav>
      <nuxt-link to="/authen/regiter" class="btn btn-outline-primary">Sign up</nuxt-link>
    </div>

    <nuxt />

    <footer class="pt-4 my-md-5 pt-md-5 border-top">
      <div class="container">
        <div class="row">
          <div class="col-12 col-md">
            <img
              class="mb-2"
              src="https://getbootstrap.com/docs/4.3/assets/brand/bootstrap-solid.svg"
              alt
              width="24"
              height="24"
            />
            <small class="d-block mb-3 text-muted">© 2017-2019</small>
          </div>
          <div class="col-6 col-md">
            <h5>Features</h5>
            <ul class="list-unstyled text-small">
              <li>
                <a class="text-muted" href="#">Cool stuff</a>
              </li>
              <li>
                <a class="text-muted" href="#">Random feature</a>
              </li>
              <li>
                <a class="text-muted" href="#">Team feature</a>
              </li>
              <li>
                <a class="text-muted" href="#">Stuff for developers</a>
              </li>
              <li>
                <a class="text-muted" href="#">Another one</a>
              </li>
              <li>
                <a class="text-muted" href="#">Last time</a>
              </li>
            </ul>
          </div>
          <div class="col-6 col-md">
            <h5>Resources</h5>
            <ul class="list-unstyled text-small">
              <li>
                <a class="text-muted" href="#">Resource</a>
              </li>
              <li>
                <a class="text-muted" href="#">Resource name</a>
              </li>
              <li>
                <a class="text-muted" href="#">Another resource</a>
              </li>
              <li>
                <a class="text-muted" href="#">Final resource</a>
              </li>
            </ul>
          </div>
          <div class="col-6 col-md">
            <h5>About</h5>
            <ul class="list-unstyled text-small">
              <li>
                <a class="text-muted" href="#">Team</a>
              </li>
              <li>
                <a class="text-muted" href="#">Locations</a>
              </li>
              <li>
                <a class="text-muted" href="#">Privacy</a>
              </li>
              <li>
                <a class="text-muted" href="#">Terms</a>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
