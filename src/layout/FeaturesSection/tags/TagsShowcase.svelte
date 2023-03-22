<script lang="ts">
	import { taggedFiles, tags } from "$data/features";
	import { ColorSwatch } from "$lib";

	let selectedTag = 0;
</script>

<div class="tags-showcase">
	<div class="showcase-panel">
		<table class="files-table">
			<tr>
				<th />
				<th>Name</th>
				<th>Tag</th>
			</tr>
			{#each taggedFiles as file, i}
				<tr
					style="--file-index: {i}"
					class:tag-selected={tags.findIndex(t => t.name === file.tag) ===
						selectedTag}
				>
					<td>
						<img
							src="/ui/icons/{file.icon}.png"
							width="24"
							height="24"
							alt={file.icon === "folder" ? `${file.icon} file` : "Folder"}
						/>
					</td>
					<td>{file.name}</td>
					<td class="tag-cell">
						<div class="tag-cell-inner">
							<svg width="16" height="16" viewBox="0 0 16 16">
								<circle
									cx="8"
									cy="8"
									r="6"
									fill={tags.find(t => t.name === file.tag)?.color}
								/>
							</svg>
							<span>{file.tag}</span>
						</div>
					</td>
				</tr>
			{/each}
		</table>
	</div>
	<div class="showcase-panel tags-picker">
		{#each tags as tag, i}
			<ColorSwatch
				bind:group={selectedTag}
				--color-index={i}
				value={i}
				type="round"
				colorName={tag}
			/>
		{/each}
	</div>
</div>

<style lang="scss">
	@use "./TagsShowcase";
</style>
