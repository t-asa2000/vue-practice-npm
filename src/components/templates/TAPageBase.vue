<script>
	import TAHeader from '../organisms/TAHeader.vue';
	import TACanvas from '../molecuels/TACanvas.vue';

	export default {
		name: "TAPageBase",
		components: {
    TAHeader,
    TACanvas
},
		props: {
			title: {
				type: String,
				default: '',
				required: false
			},
			buttons: {
				type: Array,
				default: () => { return [] },
				required: false
			},
			menu: {
				type: Array,
				default: () => { return [] },
				required: false
			}
		}
	}
</script>

<template>
	<v-layout>
		<!-- ヘッダー -->
		<TAHeader :title="title" :menu="menu" :buttons="buttons" />

		<!-- メイン -->
		<v-main class="mx-auto mt-3">
			<TACanvas title="サイト移転のお知らせ" icon="mdi-web" class="my-3 pt-2 pb-4">
				<p>『TA道具箱』は以下のURLに移転しました。今後は新しいサイトでご利用ください。</p>
				<p><a href="https://toolbox.t-asa2000.net/" target="_blank" rel="noopener noreferrer">https://toolbox.t-asa2000.net/</a></p>
			</TACanvas>
			<slot></slot>
		</v-main>
	</v-layout>
</template>

<style>
	body
	{
		color: rgb(var(--v-theme-on-background));
		background-color:rgb(var(--v-theme-surface-light));
	}
	.v-main
	{
		max-width: min(1080px, calc(100% - 20px));
	}
</style>