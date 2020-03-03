<template>
    <Page actionBarHidden="true" backgroundColor="#42b883">
        <StackLayout height="60" verticalAlignment="top">
            <Button text="Aide" @tap="helpTap" android:marginTop="20" />
        </StackLayout>
    </Page>
</template>

<script>
export default {
    methods: {
        helpTap(){
            alert("Insérer aide");
        }
    }
};
</script>