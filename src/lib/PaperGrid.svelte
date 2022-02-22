<script>
    import { data } from '$lib/jdata.js'
    import {Cell, InnerGrid} from "@smui/layout-grid/dist";
    import Paper, {Content, Title} from "@smui/paper";
</script>

<InnerGrid>
    {#each data as d}
        <Cell>
            <Paper color="secondary">
                <Title>{d.name}</Title>
                <Content>{d.category}</Content>
            </Paper>
        </Cell>
    {/each}
</InnerGrid>