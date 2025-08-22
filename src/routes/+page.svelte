<script>
    import data from '$lib/data.js';
    import { Tween } from 'svelte/motion';
    import BotaoAzul from './botao_azul.svelte';

    let page_pin = true
    let index = $state(0);
    function set_index(new_index) {
        index = new_index;
    }

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
        background-image: url('/images/UI/left_button.png');
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
        z-index: 1;
    }
    .back-btn {
        background-image: url('/images/UI/right_button.png');
        background-repeat: no-repeat;
        background-position: center;
        background-size: 57.2px 91.4px;
        width: 57.2px;
        height: 91.4px;
        padding: 0;
        z-index: 1;
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
    <img class='header-left' src="/images/UI/Header_left.png" alt="header"/><img class='header-right' src="/images/UI/Header_right.png" alt="header"/>
</div>
<div style="position: relative;">
    <div class="flex-container">
        <button class="front-btn" onclick={decreaseIndex} aria-label="front"></button>
        <div style="float: left; position: relative; height: 230px; width: 208px;
            display: flex;
            justify-content: center;
            align-items: center;">
            <img 
            src='images/UI/screen.png' alt='Container' 
            style="position: absolute; z-index: 5; top: 0px; right: 0px; height: 230px;"/>
            <img 
            src={data[index].gifs} alt={data[index].name} 
            style="height: 89px; z-index: 10; position: relative; left: 5px;"
            />
        </div>
        <button class="back-btn" onclick={increaseIndex} aria-label="back"></button>
    </div>
    <div class="info" >
        <h2 style="margin: 16px;">{data[index].name}</h2>
        <div style="display: flex; flex-direction: row;">
            <div style="display: flex; flex-direction: column; margin:16px">
                <p>Init: {data[index].iniciative}</p>
                <p>Mov: {data[index].movement}</p>
            </div>
            <div style="display: flex; flex-direction: column; margin:16px">
                <p>Atk: {data[index].attack}</p>
                <p>Def: {data[index].defense}</p>
            </div>
        </div>
    </div>
</div>    

<div 
    style="display: flex; flex-direction: row; justify-content: center; 
    margin-left: 10%;
    margin-right: 10%;
    width: 80%;
    height-max: 30%; margin-bottom: 16px;"
    
    >
<BotaoAzul variable={() => set_index(7)} name={'   Tinkaton'}/>
<BotaoAzul variable={() => set_index(13)} name={'   Galvantula'}/>
<BotaoAzul variable={() => set_index(30)} name={'   Heracross'}/>
<BotaoAzul variable={() => set_index(31)} name={'   Spoink'}/>

</div>
