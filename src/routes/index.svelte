<script lang="ts">
	import LayoutGridComponentDev, {Cell, InnerGrid} from "@smui/layout-grid/dist";
	import SortedTable from "$lib/SortedTable.svelte";


</script>


<LayoutGridComponentDev>
	<Cell span={12} class="left-cell">
		<SortedTable />
	</Cell>
</LayoutGridComponentDev>


