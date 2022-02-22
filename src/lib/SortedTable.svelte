<DataTable
        sortable
        bind:sort
        bind:sortDirection
        on:SMUIDataTable:sorted={handleSort}
        table$aria-label="Journal list"
        style="width: 100%;"
>
    <Head>
        <Row>
            <!--
              Note: whatever you supply to "columnId" is
              appended with "-status-label" and used as an ID
              for the hidden label that describes the sort
              status to screen readers.

              You can localize those labels with the
              "sortAscendingAriaLabel" and
              "sortDescendingAriaLabel" props on the DataTable.
            -->
<!--            <Cell numeric columnId="id">-->
<!--                &lt;!&ndash; For numeric columns, icon comes first. &ndash;&gt;-->
<!--                <IconButton class="material-icons">arrow_upward</IconButton>-->
<!--                <Label>ID</Label>-->
<!--            </Cell>-->
            <Cell columnId="name">
                <Label>Name</Label>
                <!-- For non-numeric columns, icon comes second. -->
                <IconButton class="material-icons">arrow_upward</IconButton>
            </Cell>
            <Cell numeric columnId="JCI">
                <IconButton class="material-icons">arrow_upward</IconButton>
                <Label>JCI</Label>
            </Cell>
            <Cell numeric columnId="year">
                <IconButton class="material-icons">arrow_upward</IconButton>
                <Label>Year</Label>
            </Cell>
            <Cell columnId="category">
                <Label>Category</Label>
                <IconButton class="material-icons">arrow_upward</IconButton>
            </Cell>
            <Cell columnId="publisher">
                <Label>Publisher</Label>
                <IconButton class="material-icons">arrow_upward</IconButton>
            </Cell>
<!--            <Cell columnID="website" sortable={false}>-->
<!--                <Label>Website</Label>-->
<!--            </Cell>-->
        </Row>
    </Head>
    <Body>
    {#each items as item (item.id)}
        <Row>
<!--            <Cell numeric>{item.id}</Cell>-->
            <Cell>{item.name}</Cell>
            <Cell>{item.JCI}</Cell>
            <Cell>{item.year}</Cell>
            <Cell>{item.category}</Cell>
            <Cell>{item.publisher}</Cell>
        </Row>
    {/each}
    </Body>
</DataTable>

<script lang="ts">
    import DataTable, {
        Head,
        Body,
        Row,
        Cell,
        Label,
        SortValue,
    } from '@smui/data-table';
    import IconButton from '@smui/icon-button';
    import { data } from '$lib/jdata.js';

    type Journal = {
        id: number;
        name: string;
        JCI: number;
        year: number;
        category: string;
        publisher: string;
    };
    let items: Journal[] = data;
    let sort: keyof Journal = 'id';
    let sortDirection: Lowercase<keyof typeof SortValue> = 'ascending';

    // if (typeof fetch !== 'undefined') {
    //     fetch(
    //         'https://raw.githubusercontent.com/schudelg/schudelg.github.io/main/journals.json'
    //     )
    //         .then((response) => response.json())
    //         .then((json) => (items = json));
    // }

    function handleSort() {
        items.sort((a, b) => {
            const [aVal, bVal] = [a[sort], b[sort]][
                sortDirection === 'ascending' ? 'slice' : 'reverse'
                ]();
            if (typeof aVal === 'string' && typeof bVal === 'string') {
                return aVal.localeCompare(bVal);
            }
            return Number(aVal) - Number(bVal);
        });
        items = items;
    }
</script>
