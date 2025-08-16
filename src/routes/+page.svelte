<script>
    let data = [
        {
            name: 'Pikachu',
            pinned: true,
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
        {
            name: 'Charizard',
            pinned: false,
            icon: 'src/images/charizard.png',
            gif: 'src/images/charizard.gif',
            iniciative: 3,
            iniciative_c: 7,
            movement: 6,
            movement_c: 4,
            attack: 8,
            attack_c: 8,
            defense: 2,
            defense_c: 7
        }
    ];
    let page_pin = true
    let index =1

    function increaseIndex() {
        index = (index + 1) % data.length;
    }
    function decreaseIndex() {
        index = (index - 1 + data.length) % data.length;
    }
</script>
<style>

    .header-right {
        width: 100%;
        height: 100px;
        position: absolute;
        right: 0;
        top: 0;
        z-index: -1;
    }
    .header-left {
        height: 100px;
    }
    .front-btn {
        background-image: url('src/images/UI/left_button.png');
        background-repeat: no-repeat;
        background-position: center;
        background-size: 57.2px 91.4px;
        width: 57.2px;
        height: 91.4px;
        padding: 0;
        border: none;
        outline: none;
        background-color: transparent;
        cursor: pointer;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .back-btn {
        background-image: url('src/images/UI/right_button.png');
        background-repeat: no-repeat;
        background-position: center;
        background-size: 57.2px 91.4px;
        width: 57.2px;
        height: 91.4px;
        padding: 0;
        border: none;
        outline: none;
        background-color: transparent;
        cursor: pointer;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .info {
        background-color: #4caf50;
        color: white;
        border-radius: 12px;
        display: flex;
        flex-direction: column;
        outline: 2px solid black;
        width: 90%;
        margin: 5%;
        font-family: 'Lora', sans-serif;
    }
    .flex-container {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 16px;
    }
</style>
<div class="Header">
    <img class='header-left' src="src/images/UI/Header_left.png" alt="header"/><img class='header-right' src="src/images/UI/Header_right.png" alt="header"/>
</div>
<div style="position: relative; z-index: 1;">
    <div class="flex-container">
        <button class="front-btn" on:click={decreaseIndex} aria-label="front"></button>
        <div style="float: left; position: relative;">
            <img src='src/images/UI/screen.png' alt='Container' style="height: 230px;"/>
            <img 
                src={data[index].gif} alt={data[index].name} 
                style="position: absolute; top: 50px; right: 50px; height: 89px; "
            />
        </div>
        <button class="back-btn" on:click={increaseIndex} aria-label="back"></button>
    </div>
    <div class="info" >
        <h2 style="margin: 16px;">{data[index].name}</h2>
        <div style="display: flex; flex-direction: row;">
            <div style="display: flex; flex-direction: column; margin:16px">
                <p>Iniciativa: {data[index].iniciative}</p>
                <p>Movimento: {data[index].movement}</p>
            </div>
            <div style="display: flex; flex-direction: column; margin:16px">
                <p>Ataque: {data[index].attack}</p>
                <p>Defesa: {data[index].defense}</p>
            </div>
        </div>
    </div>
</div>    
