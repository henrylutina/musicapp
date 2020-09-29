<template>
  <div id="app">
    <div class="row justify-content-md-center sharing-area text-center my-5 py-4">
      <div class="text-center col-md-12 col-lg-8 text-muted">
          <h3>Contact us!</h3>
      </div>
      <div class="text-center col-md-12 col-lg-8">
          <a href="#pablo" class="btn btn-twitter-bg twitter-sharrre btn-round text-muted" rel="tooltip" title="Tweet!">
              <i class="fa fa-twitter"></i> Twitter
          </a>
          <a href="#pablo" class="btn btn-google-bg linkedin-sharrre btn-round text-muted" rel="tooltip" title="Share!">
              <i class="fa fa-google-plus"></i> Google
          </a>
          <a href="#pablo" class="btn btn-facebook-bg facebook-sharrre btn-round text-muted" rel="tooltip" title="Share!">
              <i class="fa fa-facebook-square"></i> Facebook
          </a>
      </div>
    </div>
    <hr>
    <footer class="footer">
        <div class="container">
            <div class="row">
                <nav class="m-auto">
                    <ul class="navbar-nav text-muted">
                      <li class="">
                        <router-link  to="/" class="text-muted" >Home <span class="sr-only">(current)</span></router-link>
                        <router-link  to="/app" class="mx-4 text-muted">Player</router-link>
                        <!-- <router-link  to="/" class="text-muted">Our Team</router-link>  -->
                      </li>
                    </ul>      
                </nav>
                <div class="credits my-4 text-muted mx-auto">
                    <span class="copyright">
                        © 2020, made from the <i class="fa fa-heart heart"></i> by Team Erica
                    </span>
                </div>
            </div>
        </div>
    </footer>
  </div>
</template>

<script>

export default {
  name: '',
  components: {

  }
}
</script>

<style>

</style>