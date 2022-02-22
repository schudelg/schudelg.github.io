<script lang="ts">
	import LayoutGridComponentDev, {Cell, InnerGrid} from "@smui/layout-grid/dist";
	import BioCard from '$lib/BioCard.svelte';
	import NavCard from "$lib/NavCard.svelte";
	import { data } from '$lib/jdata.js';
	import SortedTable from "$lib/SortedTable.svelte";


</script>


<LayoutGridComponentDev>
	<Cell span={3} class="left-cell">
		<BioCard />
		<br />
		<NavCard />
	</Cell>

	<Cell span={9} class="right-cell">
		<SortedTable />

	</Cell>

</LayoutGridComponentDev>


