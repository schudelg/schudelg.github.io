<script lang="ts">

    import TopAppBar, {
        Row,
        Section,
        Title,
        AutoAdjust,
        TopAppBarComponentDev
    } from '@smui/top-app-bar';
    import IconButton from "@smui/icon-button";
    import {Icon} from "@smui/button";
    import {mdiGithub, mdiWeb} from "@mdi/js";

    let topAppBar: TopAppBarComponentDev;

</script>

<!--<AutoAdjust {topAppBar} style="display: flex; justify-content: space-between;">-->
<TopAppBar bind:this={topAppBar} variant="standard">
    <Row>
        <Section>
            <Title>My App</Title>
        </Section>
        <Section align="end" toolbar>
            <IconButton aria-label="GitHub" href="https://github.com/hperrin/svelte-material-ui">
                <Icon component={Svg} viewBox="0 0 24 24">
                    <path fill="currentColor" d={mdiGithub} />
                </Icon>
            </IconButton>
            <IconButton aria-label="Demo Site" href="https://sveltematerialui.com">
                <Icon component={Svg} viewBox="0 0 24 24">
                    <path fill="currentColor" d={mdiWeb} />
                </Icon>
            </IconButton>
        </Section>
    </Row>
</TopAppBar>
<!--</AutoAdjust>-->