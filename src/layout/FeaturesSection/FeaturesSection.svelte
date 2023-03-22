<script lang="ts">
	import { onMount } from "svelte";
	import { dev } from "$app/environment";
	import { _ } from "svelte-i18n";

	import {
		entries,
		FeatureCard,
		HeaderChip,
		keys,
		PageSection,
		type Prettify
	} from "$lib";
	import type { FeatureCardData } from "$data/features";

	import TagsShowcase from "./tags/TagsShowcase.svelte";
	import PreviewShowcase from "./preview/PreviewShowcase.svelte";
	import TabsShowcase from "./tabs/TabsShowcase.svelte";
	import CloudShowcase from "./cloud/CloudShowcase.svelte";
	import ColumnsShowcase from "./columns/ColumnsShowcase.svelte";
	import ArchivesShowcase from "./archives/ArchivesShowcase.svelte";

	import Cloud from "@fluentui/svg-icons/icons/cloud_24_regular.svg?raw";
	import TabDesktop from "@fluentui/svg-icons/icons/tab_desktop_20_regular.svg?raw";
	import EyeVisible from "@fluentui/svg-icons/icons/eye_20_regular.svg?raw";
	import Tag from "@fluentui/svg-icons/icons/tag_24_regular.svg?raw";
	import Columns from "@fluentui/svg-icons/icons/panel_left_28_regular.svg?raw";
	import Archive from "@fluentui/svg-icons/icons/folder_zip_24_regular.svg?raw";
	import { Flyout, Tooltip } from "fluent-svelte";

	let cardPaginationInterval = 16;

	export const featureCards = {
		tabs: {
			title: $_("home.features.tabs.title"),
			description: $_("home.features.tabs.description"),
			icon: TabDesktop,
			preview: TabsShowcase
		},
		columns: {
			title: $_("home.features.columns.title"),
			description: $_("home.features.columns.description"),
			icon: Columns,
			preview: ColumnsShowcase
		},
		archives: {
			title: $_("home.features.archives.title"),
			description: $_("home.features.archives.description"),
			icon: Archive,
			preview: ArchivesShowcase
		},
		cloud: {
			title: $_("home.features.cloud.title"),
			description: $_("home.features.cloud.description"),
			icon: Cloud,
			preview: CloudShowcase
		},
		preview: {
			title: $_("home.features.preview.title"),
			description: $_("home.features.preview.description"),
			icon: EyeVisible,
			preview: PreviewShowcase
		},
		tags: {
			title: $_("home.features.tags.title"),
			description: $_("home.features.tags.description"),
			icon: Tag,
			preview: TagsShowcase
		}
	} as const satisfies { [name: string]: FeatureCardData };

	let currentFeature: keyof typeof featureCards = "tabs";
</script>

<PageSection id="features-section">
	<div class="features-section-right">
		<HeaderChip>{$_("home.features.chip")}</HeaderChip>
		<h2>{$_("home.features.title")}</h2>
		<p>{$_("home.features.description")}</p>

		<div class="feature-cards-container">
			{#each entries(featureCards) as [id, feature]}
				<FeatureCard
					on:click={() => {
						currentFeature = id;
						cardPaginationInterval = 24;
					}}
					clickable
					selected={currentFeature === id}
					description={feature.description}
					icon={feature.icon}
				>
					{feature.title}
				</FeatureCard>

				<!-- <svelte:component this={feature.preview} /> -->
			{/each}
		</div>
	</div>
</PageSection>

<style lang="scss">
	@use "FeaturesSection";
</style>
