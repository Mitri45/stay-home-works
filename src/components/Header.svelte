<script>
import { createEventDispatcher } from 'svelte';

export let currentLanguage = '';

const dispatch = createEventDispatcher();
const buttonClick = () => dispatch('buttonClick');

</script>

<style>

header {
    width: 100%;
    max-height: 12rem;
    background-color: #e4652b;
    
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    padding-bottom: 0.5rem;
    
}

@media only screen and (min-width: 600px) {
   header {
    justify-content: space-between;
} 
}

img {
    height: 100%;
}

.languageButton {
    align-self: flex-end;
    background-color: white;
    border: none;
    margin: 1em 1rem 1rem 0;
    border-radius: 10px;
    padding: 0.45rem; 
    box-shadow: 0 5px 10px rgba(0,0,0,0.1), 0 3px 3px rgba(0,0,0,0.23);
}

.languageButton:hover {
    box-shadow: none;
    cursor: pointer;

}

.languageButton-on {
    font-weight: bold; 
    font-size: 1.2em;
 text-decoration-line: underline;
}

.languageButton-off {
    font-weight: normal;
    font-size: 1em; 
    text-decoration-line: none;
}
</style>

<header>
<img  src="./images/title.png" alt="Stay home works!">

{#if currentLanguage == "English"}
	<button class="languageButton" on:click={buttonClick}>
		<span class="languageButton-off"> Русский <span>
        <span> || </span> 
        <span class="languageButton-on"> English </span>
	</button>
{:else}
	<button class="languageButton" on:click={buttonClick}>
		<span class="languageButton-on"> Русский </span>
        <span> || </span>
        <span class="languageButton-off"> English </span>
	</button>
{/if}

<!-- <button on:click={buttonClick}>{
    (currentLanguage == "English"){
        ?"Русский |":" English"
    }
    }</button>  -->
</header>
