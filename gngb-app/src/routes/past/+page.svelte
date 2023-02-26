<script>
	import '../../app.css';
	import AudioPlayer from './AudioPlayer.svelte';

	let page = '2016';
	let audioTracks = [
		'music/dream_2016.mp3',
		'https://sveltejs.github.io/assets/music/strauss.mp3',
		'music/dream_2016.mp3'
	];

	/**
	 * @param {number} value
	 */
	function loveProgress(value) {
		return `
		<div class="flex flex-row mt-1.5">
			<div class="text-right basis-1/12">👦🏻</div>
			<div class="basis-10/12">
				<div class="flex flex-row">
					<div class="text-right basis-1/12">💓</div>
					<div class="basis-11/12">
						<progress class="progress progress-accent" value="10" max="100" />
					</div>
				</div>
			</div>
			<div class="text-left basis-1/12">👩🏻</div>
		</div>
        `;
	}
</script>

<div class="stats shadow">
	<div class="stat">
		<div class="stat-title">우리가 결혼하는 건에 대하여</div>
		<div class="stat-value">과거의 우리</div>
		<div class="stat-desc">2016 ~ 2022</div>
	</div>
</div>
<progress class="progress progress-accent" />

<select class="select select-primary w-full" bind:value={page}>
	<option value="default">어느 시점으로 되돌아 가보고 싶어?</option>
	<option value="2016">2016</option>
	<option value="2017">2017</option>
	<option value="2018">2018</option>
	<option value="2019">2019</option>
	<option value="2020">2020</option>
	<option value="2021">2021</option>
	<option value="2022">2022</option>
</select>

{#if page === 'default'}
	<progress class="progress progress-accent" value="0" max="100" />
{:else if page === '2016'}
	{@html loveProgress(10)}

	<article class="prose mx-2 mt-2">
		<h3>함께한 음악</h3>
		<div class="mx-1 mt-2">
			<AudioPlayer src={audioTracks[0]} />
		</div>
		<p>프로포즈를 준비하면서 2016년도에 가장 많이 들었던 노래가 무엇일까 많이 생각해봤습니다.</p>
	</article>

	<article class="prose mx-2 mt-2">
		<h3>함께한 순간</h3>
		<div class="carousel carousel-center w-full p-4 space-x-4 bg-neutral rounded-box">
			<div class="carousel-item">
				<div class="w-48 rounded-full focus:w-80">
					<img src="sanga_main.jpeg" alt="sanga_main" />
				</div>
			</div>
			<div class="carousel-item">
				<div class="w-48 rounded-full">
					<img src="sanga_main.jpeg" alt="sanga_main" />
				</div>
			</div>
			<div class="carousel-item">
				<div class="w-48 rounded-full">
					<img src="sanga_main.jpeg" alt="sanga_main" />
				</div>
			</div>
		</div>
		<p>프로포즈를 준비하면서 2016년도에 가장 많이 들었던 노래가 무엇일까 많이 생각해봤습니다.</p>
	</article>
{:else if page === '2017'}
	<progress class="progress progress-accent" value="20" max="100" />
{:else if page === '2018'}
	<progress class="progress progress-accent" value="30" max="100" />
{:else if page === '2019'}
	<progress class="progress progress-accent" value="40" max="100" />
{:else if page === '2020'}
	<progress class="progress progress-accent" value="50" max="100" />
{:else if page === '2021'}
	<progress class="progress progress-accent" value="60" max="100" />
{:else if page === '2022'}
	<progress class="progress progress-accent" value="70" max="100" />
{/if}

<footer class="footer items-center p-4 bg-neutral text-neutral-content">
	<div class="items-center grid-flow-col">
		<svg
			width="36"
			height="20"
			viewBox="0 0 24 24"
			xmlns="http://www.w3.org/2000/svg"
			fill-rule="evenodd"
			clip-rule="evenodd"
			class="fill-current"
			><path
				d="M22.672 15.226l-2.432.811.841 2.515c.33 1.019-.209 2.127-1.23 2.456-1.15.325-2.148-.321-2.463-1.226l-.84-2.518-5.013 1.677.84 2.517c.391 1.203-.434 2.542-1.831 2.542-.88 0-1.601-.564-1.86-1.314l-.842-2.516-2.431.809c-1.135.328-2.145-.317-2.463-1.229-.329-1.018.211-2.127 1.231-2.456l2.432-.809-1.621-4.823-2.432.808c-1.355.384-2.558-.59-2.558-1.839 0-.817.509-1.582 1.327-1.846l2.433-.809-.842-2.515c-.33-1.02.211-2.129 1.232-2.458 1.02-.329 2.13.209 2.461 1.229l.842 2.515 5.011-1.677-.839-2.517c-.403-1.238.484-2.553 1.843-2.553.819 0 1.585.509 1.85 1.326l.841 2.517 2.431-.81c1.02-.33 2.131.211 2.461 1.229.332 1.018-.21 2.126-1.23 2.456l-2.433.809 1.622 4.823 2.433-.809c1.242-.401 2.557.484 2.557 1.838 0 .819-.51 1.583-1.328 1.847m-8.992-6.428l-5.01 1.675 1.619 4.828 5.011-1.674-1.62-4.829z"
			/></svg
		>
		<p>Copyright © 2023 - All right reserved</p>
	</div>
</footer>
