<script>
import TACanvas from '@/components/molecuels/TACanvas.vue';
import TAPageBase from '@/components/templates/TAPageBase.vue';
import DekanjiForm from '@/components/organisms/DekanjiForm.vue';

export default {
	name: 'App',
	components: {
    TACanvas,
    TAPageBase,
    DekanjiForm
},
	data:() => ({
		title: 'TA道具箱',
		menu: [
			'TA道具箱',
			{
				title: 'ホーム',
				icon: 'mdi-home',
				href: './',
				active: true
			},
			'ツール一覧',
			{
				title: 'デ漢字',
				icon: 'mdi-ideogram-cjk',
				href: 'dekanji/'
			},
			{
				title: '貨幣カウンター 汎用カウンター',
				icon: 'mdi-counter'
			},
			{
				title: 'URL一括修正ツール',
				icon: 'mdi-xml'
			},
			{
				title: 'Mastodon/Misskey 投稿埋め込み ウィジェット',
				icon: 'mdi-account-multiple'
			},
			'ソースコード',
			{
				title: 'GitHub リポジトリ',
				icon: 'mdi-xml',
				href: "https://github.com/t-asa2000/vue-practice-npm",
				newTab: true
			},
			'開発者 (t-asa2000)',
			{
				title: '個人サイト',
				icon: 'mdi-account-circle',
				href: "https://t-asa2000.net/",
				newTab: true
			},
			{
				title: 'GitHub',
				icon: 'mdi-link-variant',
				href: "https://github.com/t-asa2000/",
				newTab: true
			},
			{
				title: 'Misskey',
				icon: 'mdi-link-variant',
				href: "https://misskey.io/@asata",
				newTab: true
			},
			{
				title: 'Fedibird (Mastodon)',
				icon: 'mdi-link-variant',
				href: "https://fedibird.com/@asata",
				newTab: true
			}
		],
		buttons: []
	}),
	methods: {
		buttonClicked(button) {
			console.log('次のボタンが押されました:' + button);
		}
	}
}
</script>

<template>
	<TAPageBase :title="title" :menu="menu" :buttons="buttons">
		<DekanjiForm class="my-3"/>
		<h1 class="px-2 py-3">このサイトについて</h1>
		<TACanvas class="mb-3">
			<p>個人的に「あったらいいな」と思ったツールを自作して公開しているサイトです。</p>
			<p>このサイトをスマートフォンのホーム画面に追加すると、様々なツールに素早くアクセスすることができます。</p>
		</TACanvas>
	</TAPageBase>
</template>