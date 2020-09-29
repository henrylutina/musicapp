<template>
	<div id="app">
		<div class="page-header my-5 py-5 text-white" data-parallax="true">
			<div class="filter"></div>
			<div class="container py-5">
				<div class="motto text-center mb-5">
					<h1 class="display-3 mt-5 py-3">Erica music app</h1>
					<h3>Do it right now through music!</h3>
					<br />
					<router-link to="/app" class="btn btn-outline-light btn-round px-5"><i class="fa fa-play mx-1"></i>Play</router-link>
				</div>
				<div class="motto text-center mb-5">
					<h1 class="mt-5"></h1>
					<h3></h3>
					<br />
					<a class="btn btn-outline-neutral btn-round"></a>
				</div>
			</div>
		</div>
		<div class="main my-5 py-5 text-muted">
			<div class="section text-center">
				<div class="container">
					<div class="row">
						<div class="col-md-8 offset-md-2">
							<h2 class="title">We play music</h2>
							<h5 class="description my-3">Erica Music player brings you closer than ever to iconic artists,
								rising stars, new discoveries, and legendary entertainers. An expertly curated,
								all-access pass to a world of music, here comes your moment be more focused than ever.
							</h5>
						</div>
					</div>
				</div>
			</div> 
		</div>
	</div>
</template>

<script>

export default {
  name: '',
  components: {

  }
}
</script>

<style scoped>
	.page-header{
		background: url('~@/assets/img/daniel-olahh.jpg')
	}
</style>