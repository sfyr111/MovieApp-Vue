<template lang="jade">
  div(:class="['star', size]")
    div.gray
      i.ui-icon-star(v-for="n of 5")
    div.ligh(:style="{width: (score * 10) + '%'}")
      i.ui-icon-star(v-for="n of 5")
    div.score {{ score }}
</template>

<script>
  export default {
    name: 'Star',
    props: {
      score: Number,
      size: String
    }
  }
</script>

<style lang="sass" scope>
	.star {
		position: relative;
		height: 20px;
		line-height: 20px;
		width: 100px;

		&.large {
			transform: scale(1.2);
			transform-origin: left center;
		}

		.gray, .ligh {
			position: absolute;
			top: -13px;
			left: -8px;
			width: 100px;
			overflow: hidden;
		}

		.gray {
			.ui-icon-star {
				color: #ccc;
			}
		}

		.ligh {
			.ui-icon-star {
				color: #f3e319;
			}
		}

		.ui-icon-star {
			display: inline-block;
			width: 18px;
			height: 20px;
		}

		.score {
			padding-left: 100px;
		}
	}
</style>
