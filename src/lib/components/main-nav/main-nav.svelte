<script lang="ts">
	import { cn } from "$lib/utils";
	import { page } from "$app/stores";

	let className: string | undefined | null = undefined;
	export { className as class };

	$: isActive = (href: string) => $page.url.pathname === href;
</script>

<nav class={cn("flex items-center space-x-4 lg:space-x-6", className)}>
	<a
		href="/"
		class:text-primary={isActive('/')}
		class="text-sm font-medium transition-colors hover:text-primary {isActive('/') ? '' : 'text-muted-foreground'}"
	>
		Home
	</a>

	<a  href="/observable"
		class:text-primary={isActive('/')}
		class="text-sm font-medium transition-colors hover:text-primary {isActive('/observable') ? '' : 'text-muted-foreground'}"
	>
	Observable
	</a>

	<a  href="/echarts"
		class:text-primary={isActive('/')}
		class="text-sm font-medium transition-colors hover:text-primary {isActive('/echarts') ? '' : 'text-muted-foreground'}"
	>
	eCharts
	</a>


</nav>
