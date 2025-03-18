<p> Greeting: {hello}</p>

<script lang="ts">

    import axios from "axios";
    import {onMount} from "svelte";

    interface HelloWorld {
        greeting: string,
        name: string,
    }

    let hello: undefined | string;

    onMount(() => {
        axios.get<HelloWorld>("http://localhost:8080/api/hello")
            .then(value => hello = `${value.data.greeting}, ${value.data.name}!!`)
    })

</script>

<style>

</style>