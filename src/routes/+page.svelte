<script lang="ts">
	import { browser } from '$app/environment';
	import { lang } from '$lib/stores/lang'; // Adjust the import path to match your i18n setup

	let board = [];
	let darkMode = false;

	$: if (browser) {
		document.documentElement.classList.toggle('dark', darkMode);
	}
</script>

<button
	class:dark-btn={darkMode}
	class:light-btn={!darkMode}
	on:click={() => (darkMode = !darkMode)}
>
	{darkMode ? 'Light mode' : 'Dark mode'}
</button>
<button on:click={() => lang.set('da')}>Dansk</button>
<button on:click={() => lang.set('en')}>Engelsk</button>
<button on:click={() => lang.set('th')}>Thai</button>
