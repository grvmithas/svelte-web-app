<script>
    import { page, navigating } from "$app/stores";
    import { onMount } from "svelte";

    let items = [
        { title: "Home", link: "/" },
        { title: "Mule Initializr", link: "/mule-initializr" },
        { title: "Test Data", link: "/testdata" },
        { title: "PS Chat", link: "/pschat" },
        { title: "Settings", link: "/settings" },
    ];

    let currentPath = "";

  
</script>

<nav class="nav">
    <div class="nav__logo">
       
        adas das as as d asdas <br />
    </div>
    <ul>
        {#each items as item}
            <li>
                <a
                    href={item?.link}
                    aria-current={$page.url.pathname === item?.link}
                    class={`nav__link ${
                        $page.url.pathname === item?.link ? "nav__link--active" : ""
                    }`}
                >
                    <span tabindex="-1" aria-hidden="true" class="nav__style" />
                    <span class="nav__label">{item?.title}</span>
                </a>
            </li>
        {/each}
    </ul>
</nav>

<style>
    .nav {
        width: 230px;
        overflow: auto;
        height: 100vh;
        background: #0e0e23;
        padding-left: 1rem;
    }

    .nav__link {
        display: flex;
        padding: 0.75rem 0.5rem;
        text-decoration: none;
        color: #9f9f9f;
        position: relative;
    }

    .nav__link--active {
        background: #eaedf7;
        border-radius: 30px 0 0 30px;
        &::after,
        &::before {
            content: "";
            position: absolute;
            border-top-color: transparent;
            border-left-color: transparent;
            height: 30px;
            z-index: 9;
            right: 0px;
            bottom: 0;
            border-right: 20px solid #0e0e23;
        }
        &::after {
            top: 48px;
            z-index: 0;
            right: 0px;
            bottom: 0;

            border-bottom: transparent;
            border-radius: 0px 48px 0px 0px;
        }
        &::before {
            border-radius: 0px 0px 48px 0px;
            top: -30px;
        }
    }

    .nav__link--active .nav__style {
        position: absolute;
        top: -30px;
        width: 20px;
        height: 106px;
        right: 0px;
        background: #eaedf7;
    }
</style>
