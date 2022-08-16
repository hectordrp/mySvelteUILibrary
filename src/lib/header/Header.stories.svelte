<script lang="ts">
	import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
	import Header from './header.svelte';
    import SvelteImg from '../../assets/1200px-Svelte_Logo.svg.png';
    import AvatarImg from '../../assets/avatar2.svg';


</script>

<Meta
	title="Components/Header"
	component={Header}

/>

<Template let:args>
    <main>
        <Header>
            <div slot="header-nav" class="header-nav">
                <div style="display: flex; align-items: center;"> <img class="logoImg" src={SvelteImg} alt=""> MyAwesomeCompany</div>
                <div style="text-align: center;"><img class="logoImg" src={AvatarImg} alt=""></div>
                <div style="text-align: right;">LogOut -></div>
            </div>
        </Header>
    </main>
</Template>

<Story 
    name="default" 
/>

<style>

main {
    background: #FAFAFA;;
    height: 60vh;
}

.header-nav {
    color: #4A4A4A;
    font-weight: 600;
    font-size: 1rem;
}

.header-nav div{
    flex: 1;
}

.logoImg {
    height: 40px;
    padding: 0 5px;
}


</style>