<script>
	import { themes, changeTheme } from './themes';

	import { Palette } from 'lucide-svelte';
</script>

<div class="dropdown dropdown-bottom dropdown-end btn-primary">
	<div title="Themes" role="button" tabindex="0" class="btn">
		<Palette /> Theme 
	</div>

	<!-- Themes -->
	<div
		class="dropdown-content  z-10 mt-2 flex h-72 w-64 flex-col gap-2 overflow-y-scroll rounded-box bg-base-200 p-4 shadow-2xl"
	>
		{#each themes as theme}
			<button
				data-theme={theme}
				data-set-theme={theme}
				class="btn btn-sm flex justify-between bg-base-100"
				onclick={() => changeTheme(theme)}
			>
				<span>{theme}</span>

				<div class="flex items-center gap-2">
					{#each ['bg-primary', 'bg-secondary', 'bg-accent', 'bg-neutral'] as bg}
						<span class="{bg} h-4 w-2 rounded-box"></span>
					{/each}
				</div>
			</button>
		{/each}
	</div>
</div>
