<script>
	import Header from './components/Header.svelte';
	import Education from './components/Education.svelte';
	import Entertainment from './components/Entertainment.svelte';
	import EntertainmentEn from './components/content/EducationEn.md';
	
let currentLanguage = "Russian";

function handleLanguageChange() {
		if (currentLanguage == "English") {
            currentLanguage = "Russian"
            } else { 
            currentLanguage = "English"
};
    }
$: console.log(`Language value ${currentLanguage}`)

</script>

<style>
	h1 {
		color: #e4652b;
		font-size: 1.5rem;
		font-weight: 400;
		text-transform: uppercase;
		text-align: center;
		width: 90%;
		margin: auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>

<Header {currentLanguage} on:buttonClick={handleLanguageChange}/>
<main>

{#if currentLanguage === "English"}
	 <h1>List of free sources collected manually, that won't let you get boring during home stay.</h1>
{/if}

{#if currentLanguage === "Russian"}
	 <h1>Список бережно собранных бесплатных ресурсов, которые помогут провести время в изоляции с пользой</h1>
{/if}

<Education {currentLanguage}/>
<Entertainment {currentLanguage}/>

</main>
