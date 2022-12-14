<script>
	import { createEventDispatcher } from "svelte";
	import { slide } from "svelte/transition";

	const dispatch = createEventDispatcher();
</script>

<div class="modal" in:slide out:slide>
	<a href="#proc-my" class="nav-menu-item">Proč my</a>
	<a href="#o-systemu" class="nav-menu-item">O systému</a>
	<a href="#cenik" class="nav-menu-item">Ceník</a>
	<a href="#kontakt" class="nav-menu-item">Kontakt</a>
	<div class="space" />
</div>

<style lang="scss">
	@import "../styles/vars.scss";
	.modal {
		height: calc(100vh - 100px);
		width: 100vw;
		// padding: 0rem $padding-basic;
		background-color: #ffffff;
		z-index: 998;
		position: fixed;
		display: flex;
		flex-direction: column;
		gap: 1.5rem;
		justify-content: center;
		align-items: center;
		overflow-y: hidden;
		> a {
			font-size: 2rem;
			font-weight: 600;
			letter-spacing: 0.2rem;
			text-decoration: none;
			transition: 0.25s ease;
			&:hover {
				transform: scale(1.3);
				color: $systemDark;
			}
		}
	}
	.space {
		height: 100px;
	}
	@media only screen and (min-width: 768px) {
	}
	@media only screen and (min-width: 1024px) {
		.modal {
			width: calc(100% - ($padding-1024 * 2));
			padding: 0rem $padding-1024;
		}
	}
	@media only screen and (min-width: 1280px) {
	}
	@media only screen and (min-width: 1536px) {
		.modal {
			width: calc(100% - ($padding-1536 * 2));
			padding: 0rem $padding-1536;
		}
	}
</style>
