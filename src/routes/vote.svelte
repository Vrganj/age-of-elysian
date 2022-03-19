<script>
	const sites = [
		['CraftList', 'https://bit.ly/2QCOrzS', 'craftlist.png'],
		['TopG', 'https://bit.ly/3aaI7rl', 'topg.png'],
		['Minecraft-MP', 'https://bit.ly/2J42gTS', 'minecraft_multiplayer.png'],
		['MinecraftServers', 'https://bit.ly/2UFYfKX', 'mcs.png'],
		['Minecraft-List', 'https://bit.ly/39f0Dx7', 'mclist.png'],
		['Planet Minecraft', 'https://bit.ly/33NVLON', 'planet_minecraft.png'],
		['TOPMC Servers', 'https://bit.ly/2J73FsS', 'tms.png']
	];
</script>

<div class="row">
	<div class="col-12 col-md-8 mb-4">
		<h1 class="text-center mb-3">Why vote for us?</h1>
		<p style="text-align: justify">
			Voting for the server helps us out and for voting you will receive a monetary reward in-game.
			It might not seem like much, but voting is really important for servers. It is the best way
			for new players to find their way onto the server and it would be great if you could take the
			time in your day to vote every now and then. We'll make sure to give you something nice in
			return. Vote daily to become the top voter and receive special perks! Here you can find all
			the voting links in one place.
		</p>
	</div>
	<div class="col-12 col-md-4 mb-4">
		<div class="card" style="background-color: #1d1d1d">
			<div class="card-body">
				<ul>
					{#each sites as site, i}
						<li>
							<a
								href={site[1]}
								target="_blank"
								on:click={() => (localStorage[site[0]] = new Date().getTime())}>{site[0]}</a
							>
						</li>
					{/each}
				</ul>
			</div>
		</div>
	</div>
</div>
