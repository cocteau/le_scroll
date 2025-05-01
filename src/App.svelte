<script>
	import Scrolly from "./Scrolly.svelte";
	let value = $state(0);
</script>

<style>
	#scrolly {
		display: flex;
		flex-direction: row;
		align-items: flex-start;
	}

	.left-text {
		width: 40%;
	}

	.stage {
		width: 60%;
		position: sticky;
		top: 0;
		height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
		position: sticky;
	}

	.fade {
		opacity: 0;
		visibility: hidden;
		pointer-events: none;
		transition: opacity 0.6s ease;
		position: absolute;
		width: 100%;
	}

	.fade.active {
		opacity: 1;
		visibility: visible;
		pointer-events: auto;
		position: relative;
	}
</style>

<section id="scrolly">
	<div class="left-text">
		<Scrolly bind:value>
			<div style="height: 90vh;">Step 0: Intro</div>
			<div style="height: 90vh;">Step 1: Datawrapper embed</div>
			<div style="height: 90vh;">Step 2: More explanation</div>
			<div style="height: 90vh;">Step 3: Even more explanation</div>
			<div style="height: 90vh;">Step 4: Conclusion</div>
		</Scrolly>
	</div>

	<div class="stage">
		<div class="fade {value === 0 ? 'active' : ''}">
			<p>Put visual here for step 0</p>
		</div>
		<div class="fade {value === 1 ? 'active' : ''}">
			<iframe title="Step 1" src="https://datawrapper.dwcdn.net/E7gkq/1/" frameborder="0" scrolling="no" height="483" style="width:100%; border: none;"></iframe>
		</div>
		<div class="fade {value === 2 ? 'active' : ''}">
			<p>Put visual here for step 2</p>
		</div>
		<div class="fade {value === 3 ? 'active' : ''}">
			<iframe title="House prices in the U.K." aria-label="Multiple Lines" id="datawrapper-chart-rtCXv" src="https://datawrapper.dwcdn.net/rtCXv/4/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="493" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(a){if(void 0!==a.data["datawrapper-height"]){var e=document.querySelectorAll("iframe");for(var t in a.data["datawrapper-height"])for(var r,i=0;r=e[i];i++)if(r.contentWindow===a.source){var d=a.data["datawrapper-height"][t]+"px";r.style.height=d}}}))}();</script>
		</div>
		<div class="fade {value === 4 ? 'active' : ''}">
			<p>Put visual here for step 4</p>
		</div>
	</div>
</section>
