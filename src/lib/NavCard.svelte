<script>
    import Card, {ActionButtons, ActionIcons, Actions, Content, Media, PrimaryAction} from "@smui/card";
    import Button from "@smui/button";
    import {Label} from "@smui/tab";
    import IconButton, {Icon} from "@smui/icon-button";

    let clicked = 0;
</script>

<div class="card-container">
    <Card>
        <PrimaryAction on:click={() => clicked++}>
            <Media class="card-media-16x9" aspectRatio="16x9" />
            <Content class="mdc-typography--body2">
                <h2 class="mdc-typography--headline6" style="margin: 0;">
                    A card with media.
                </h2>
                <h3
                        class="mdc-typography--subtitle2"
                        style="margin: 0 0 10px; color: #888;"
                >
                    And a subtitle.
                </h3>
                It's all in this card. It's a veritable smorgasbord of card features.
            </Content>
        </PrimaryAction>
        <Actions>
            <ActionButtons>
                <Button on:click={() => clicked++}>
                    <Label>Action</Label>
                </Button>
                <Button on:click={() => clicked++}>
                    <Label>Another</Label>
                </Button>
            </ActionButtons>
            <ActionIcons>
                <IconButton
                        on:click={() => clicked++}
                        toggle
                        aria-label="Add to favorites"
                        title="Add to favorites"
                >
                    <Icon class="material-icons" on>favorite</Icon>
                    <Icon class="material-icons">favorite_border</Icon>
                </IconButton>
                <IconButton
                        class="material-icons"
                        on:click={() => clicked++}
                        title="Share">share</IconButton
                >
                <IconButton
                        class="material-icons"
                        on:click={() => clicked++}
                        title="More options">more_vert</IconButton
                >
            </ActionIcons>
        </Actions>
    </Card>
</div>