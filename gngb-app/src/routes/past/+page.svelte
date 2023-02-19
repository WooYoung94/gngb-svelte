<script>
	import '../../app.css';

	let page = 'default';
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
	<progress class="progress progress-accent" value="10" max="100" />
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
