<script lang="ts">
    import ItemLivro from "./ItemLivro.svelte";

    export let serie: any = null;
</script>

{#if serie}
    <div class="flex flex-col gap-5">
        <div class="flex flex-col gap-1">
            <h1 class="text-3xl font-black">{serie.titulo}</h1>
            <a href="/autores/{serie.autor.id}" class="text-sm text-zinc-400">{serie.autor.nome}</a>
        </div>
        <img src={serie.imagem} alt="Imagem da Série" class="h96 object-cover">
        <p class="text-lg text-zinc-400 text-justify">{serie.descricao}</p>

        <h2>Lista de Livros</h2>
        <div class="grid grid-cols-3 gap-5">
            {#each serie.livros as livro}
                <ItemLivro {livro} />
            {/each}
        </div>        
    </div>
{/if}

