<script>
    let data = [
        {
            name: 'Pikachu',
            pinned: false,
            icon: 'src/images/pikachu.png',
            gif: 'src/images/pikachu.gif',
            iniciative: 5,
            iniciative_c: 7,
            movement: 2,
            movement_c: 4,
            attack: 6,
            attack_c: 8,
            defense: 5,
            defense_c: 7
        },
    ];
    let page_pin = true
</script>


<div class="card">
    <img src={data[0].gif} alt={data[0].name} class="icon" />
    <h2>{data[0].name}</h2>
    <p>Iniciativa: {data[0].iniciative}</p>
    <p>Movimento: {data[0].movement}</p>
    <p>Ataque: {data[0].attack}</p>
    <p>Defesa: {data[0].defense}</p>
</div>
