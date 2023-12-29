<script lang="ts">
	let roll = (_player: Player) => {
        console.log('ran')
        _player.dice = Math.floor(Math.random() * 12);
        //  console.log(_player.dice)
	};

    let check = () => {
        console.log(playerList[0].dice)
        console.log(playerList[1].dice)
    }

	let playerList: Player[] = [ 
		{
			dice: 0,
			id: 0,
			name: 'Jeff'
		},

		{
			dice: 0,
			id: 1,
			name: 'Billiam'
		}
    ]

	interface Player {
		dice: number;
		id: number;
		name: string;
	}
</script>

<button on:click={ () => roll(playerList[0]) }>roll</button>
<button on:click={ () => roll(playerList[1]) }>roll</button>
<button on:click={check}>Check</button>
<div>{playerList[1].dice}</div>
<div>{playerList[1].name}</div>

<div>{playerList[0].dice}</div>
<div>{playerList[0].name}</div>
<input bind:value={playerList[0].name} type="text">
<input bind:value={playerList[1].name} type="text">

<style>
	* {
		color: red;
	}
</style>
