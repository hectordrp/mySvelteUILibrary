<script>
    import Header from '$lib/header/Header.svelte';
import Logo from '$lib/logo/Logo.svelte';
	import '../global.css';
</script>

<!-- <Logo /> -->
<main>
    <Header>
        <div slot="header-nav" class="header-nav">
			<div style="display: flex; align-items: center;"> <img class="logoImg" src="src/assets/1200px-Svelte_Logo.svg.png" alt=""> MyAwesomeCompany</div>
            <div style="text-align: center;"><img class="logoImg" src="src/assets/avatar2.svg" alt=""></div>
            <div style="text-align: right;">LogOut -></div>
		</div>
    </Header>
</main>

<a href="/">Home</a>
 
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
