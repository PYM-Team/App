<template>
    <Page actionBarHidden="true">
        <GridLayout>

            <Frame id="home-page">
                <LobbyPage />
            </Frame>

            <Frame @loaded="actionFrameLoaded">
                <ActionPage />
            </Frame>

        </GridLayout>
    </Page>
</template>

<script>
import LobbyPage from './LobbyPage';
import ActionPage from './ActionPage';
import {screen} from 'tns-core-modules/platform'

export default {
    components: {
        LobbyPage,
        ActionPage
    },
    methods: {
        actionFrameLoaded(args) {
            const frame = args.object;

            //move this frame down

            frame.translateY = screen.mainScreen.heightDIPs - 80;
        }
    }
};
</script>