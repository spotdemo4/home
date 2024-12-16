<script lang="ts">
	const columns = 16;
	const rows = 4;

	function createText() {
		const placement = Math.floor(Math.random() * 10);
		const item = Math.floor(Math.random() * 2);
        let items = ['/', '_'];
		let text = ['T', 'R', 'E', 'V', '.', 'X', 'Y', 'Z'];
        text.splice(placement, 0, items[item]);

        return text.join('');
	}
</script>

<div class="flex flex-col gap-6 p-1">
	{#each { length: rows } as _}
		<div class="flex gap-6">
			{#each { length: columns } as _}
				<h1 class="text-yellow-300 cursor-default text-6xl font-medium font-roadgeek text-nowrap">{createText()}</h1>
			{/each}
		</div>
		<div class="flex gap-4">
			{#each { length: columns } as _}
				<h1 class="text-blue-500 cursor-default text-6xl font-medium font-roadgeek text-nowrap">{createText()}</h1>
			{/each}
		</div>
		<div class="flex gap-4">
			{#each { length: columns } as _}
				<h1 class="text-orange-500 cursor-default text-6xl font-medium font-roadgeek text-nowrap">{createText()}</h1>
			{/each}
		</div>
		<div class="flex gap-4">
			{#each { length: columns } as _}
				<h1 class="text-green-500 cursor-default text-6xl font-medium font-roadgeek text-nowrap">{createText()}</h1>
			{/each}
		</div>
		<div class="flex gap-4">
			{#each { length: columns } as _}
				<h1 class="text-yellow-400 cursor-default text-6xl font-medium font-roadgeek text-nowrap">{createText()}</h1>
			{/each}
		</div>
		<div class="flex gap-4">
			{#each { length: columns } as _}
				<h1 class="text-red-500 cursor-default text-6xl font-medium font-roadgeek text-nowrap">{createText()}</h1>
			{/each}
		</div>
		<div class="flex gap-4">
			{#each { length: columns } as _}
				<h1 class="text-blue-200 cursor-default text-6xl font-medium font-roadgeek text-nowrap">{createText()}</h1>
			{/each}
		</div>
	{/each}
</div>
