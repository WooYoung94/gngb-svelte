<script>
	import '../../app.css';
	import { notifications } from './notifications.js';
	import Toast from './Toast.svelte';

	let page = 1;
	let totalPage = 3;

	/**
	 * @param {number} p
	 */
	function setPage(p) {
		if (p < 1) {
			page = 1;
			notifications.warning('첫 페이지니까 그만 눌러라, \n 스탑 상아!', 1500);
		} else if (p > totalPage) {
			page = totalPage;
			notifications.warning('마지막 페이지니까 그만 눌러라, \n 스탑 상아!', 1500);
		} else {
			page = p;
		}
	}

	/**
	 * @param {string} message
	 * @param {string} day
	 */
	function sangaSend(message, day) {
		return `
        <div class="chat chat-start">
            <div class="chat-image avatar">
                <div class="w-10 rounded-full">
                    <img src="sanga_main.jpeg" alt="sanga_main" />
                </div>
            </div>
            <div class="chat-header">
                상아공주님
                <time class="text-xs opacity-50">${day} days ago</time>
            </div>
            <div class="chat-bubble chat-bubble-warning">${message}</div>
            <div class="chat-footer opacity-50">Seen</div>
        </div>
        `;
	}

	/**
	 * @param {string} message
	 */
	function wooyoungSend(message) {
		return `
        <div class="chat chat-end">
            <div class="chat-bubble chat-bubble-success">${message}</div>
            <div class="chat-footer opacity-50">Delivered</div>
        </div>
        `;
	}
</script>

{#if page === 1}
	{@html sangaSend('뚱땡맨, 프로포즈 언제할거야?', '68')}
	{@html sangaSend('가방줬다고 끝난줄 아는거야?', '68')}
	{@html sangaSend(
		'정신차리고 빨리 준비해라 진짜로 화나기전에.. 세심하고 거창하게 준비하도록!',
		'68'
	)}
	{@html wooyoungSend('(...)')}
{:else if page === 2}
	{@html wooyoungSend(
		'(더블 마일리지 때문에 디올 웨딩 슈즈를 미리 줘버렸네.. 프로포즈때 주려고 한건데..)'
	)}
	{@html wooyoungSend('(뭐를 하면 좋을까?)')}
	{@html sangaSend('잊지 마라, 세심하고 거창하게!', '32')}
	{@html wooyoungSend('(...)')}
{:else if page === 3}
	{@html wooyoungSend('컴돌이답게 Web 으로 감동을 주겠다!')}
	<div class="chat chat-end">
		<div class="chat-bubble chat-bubble-info">우리가 지난 8년간 함께했던 이야기와,</div>
	</div>
	<div class="chat chat-end">
		<div class="chat-bubble chat-bubble-warning">우리가 지금 겪고 있는 상황에 대한 이야기와,</div>
	</div>
	<div class="chat chat-end">
		<div class="chat-bubble chat-bubble-error">
			우리가 앞으로 함께할 이야기를 담아보았습니다.
		</div>
	</div>
{/if}

<div class="fixed inset-x-0 bottom-0">
	<div class="flex justify-center h-16">
		<div class="btn-group">
			<button class="btn bg-secondary" on:click={() => setPage(page - 1)}>«</button>
			<button class="btn bg-secondary">Page {page}</button>
			<button class="btn bg-secondary" on:click={() => setPage(page + 1)}>»</button>
			<Toast />
		</div>
	</div>
</div>
