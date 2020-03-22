<script>
import EntertainmentEn from './content/EntertainmentEn.md';
import EntertainmentRu from './content/EntertainmentRu.md';

export let currentLanguage = "English";

</script>

{#if currentLanguage === "English"}
	<EntertainmentEn />
{/if}

{#if currentLanguage === "Russian"}
	<EntertainmentRu />
{/if}




