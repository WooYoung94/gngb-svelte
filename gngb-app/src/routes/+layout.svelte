<script>
	import '../app.css';
</script>

<div class="custom-nav">
	<div class="navbar bg-primary">
		<div class="navbar-start">
			<div class="dropdown">
				<!-- svelte-ignore a11y-no-noninteractive-tabindex -->
				<!-- svelte-ignore a11y-label-has-associated-control -->
				<label tabindex="0" class="btn btn-ghost btn-circle">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="h-5 w-5"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
						><path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M4 6h16M4 12h16M4 18h7"
						/></svg
					>
				</label>
				<!-- svelte-ignore a11y-no-noninteractive-tabindex -->
				<ul
					tabindex="0"
					class="menu menu-compact dropdown-content mt-3 p-2 shadow bg-secondary rounded-box w-52"
				>
					<li><a href="/past">과거의 우리</a></li>
					<li><a href="/contact">현재의 우리</a></li>
					<li><a href="/story">미래의 우리</a></li>
					<li><a href="/about">재롱 잔치</a></li>
				</ul>
			</div>
		</div>
		<div class="navbar-center">
			<a class="btn btn-ghost normal-case text-2xl" href="/">🤵🏻 💍 👰🏻</a>
		</div>
		<div class="navbar-end">
			<button class="btn btn-ghost btn-circle">
				<div class="indicator">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="h-5 w-5"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
						><path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"
						/></svg
					>
					<div
						class="badge badge-xs badge-primary bg-primary text-secondary-content indicator-item"
					>
						<a href="/notification">999</a>
					</div>
				</div>
			</button>
		</div>
	</div>
</div>

<slot />
