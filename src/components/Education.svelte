<script>
import EducationEn from './content/EducationEn.md';
import EducationRu from './content/EducationRu.md';

export let currentLanguage = "English";

</script>


{#if currentLanguage == "English"}
	<EducationEn />
{/if}

{#if currentLanguage == "Russian"}
	<EducationRu />
{/if}




