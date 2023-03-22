<script lang="ts">
	import { draw } from "svelte/transition";
	import { Titlebar } from "$lib";

	let selectedTab = 0;
</script>

<div class="tabs-showcase">
	<div class="showcase-panel">
		<Titlebar>Files</Titlebar>
	</div>
	<div class="showcase-panel">
		<Titlebar>Files</Titlebar>
	</div>
	<div class="tabs-anchor">
		<div class="tab-row">
			<div class="tab"
			     class:selected={selectedTab === 0} on:click={() => selectedTab = 0}
			>
				<img src="/ui/icons/documents.png" alt="Documents folder icon" width="16" height="16">
				Documents
			</div>
			<div class="tab"
			     class:selected={selectedTab === 1} on:click={() => selectedTab = 1}
			>
				<img src="/ui/icons/desktop.png" alt="Desktop folder icon" width="16" height="16">
				Desktop
			</div>
			<div class="tab"
			     class:selected={selectedTab === 2} on:click={() => selectedTab = 2}
			>
				<img src="/ui/icons/pictures.png" alt="Pictures folder icon" width="16" height="16">
				Pictures
			</div>
		</div>
		<div class="showcase-panel">
			<Titlebar>Files</Titlebar>
			<div class="files-grid">
				{#each Array(12) as _, i}
					<div style="--file-index: {i};" class="placeholder-file"></div>
				{/each}
			</div>
		</div>
	</div>
</div>

<style lang="scss">
	@use "./TabsShowcase";
</style>