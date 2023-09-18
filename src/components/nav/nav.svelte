<script>
    import { page, navigating } from "$app/stores";

    let items = [
        { title: "Home", link: "/" },
        { title: "Mule Initializr", link: "/mule-initializr" },
        { title: "Test Data", link: "/test-data" },
        { title: "PS Chat", link: "/ps-chat" },
        { title: "Settings", link: "/settings" },
    ];
</script>

<nav>
    {#each items as item}
        <a href={item?.link} aria-current={$page.url.pathname === item?.link}
            >{item?.title}</a
        >
    {/each}
</nav>
