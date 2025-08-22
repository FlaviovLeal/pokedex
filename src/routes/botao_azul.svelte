<script>
    import { Tween } from 'svelte/motion';
    let index = 0;
    let { variable, name } = $props();
    let tween = new Tween(1);
    function click_button() {
        variable();
        if (tween.current < 0){
            tween.target = 1;        
        } else {
            tween.target = -1
        };
    }

</script>

<div style="float: left; position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
            margin-left: -3.5%;
            margin-right:0px;
            z-index: {index};
            ">
    <p
        style="position: absolute; z-index: 11; top: {4.5 - (4.33 * Math.abs(tween.current))}%; left: {3.9 - (3.84 * Math.abs(tween.current))}%;
        padding: 5px"
    >{name}</p>
    <!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
    <!-- svelte-ignore a11y_click_events_have_key_events -->
    <img
        src='images/UI/Blue_top.png' alt='Top' 
        style="position: absolute; z-index: 10; top: {4.5 - (4.33 * Math.abs(tween.current))}%; left: {3.9 - (3.84 * Math.abs(tween.current))}%;"
        onclick={click_button}/>
    <img
        src='images/UI/Blue_Bottom.png' alt='Bottom' 
        style="z-index: 5; position: relative; 
        width: 100%;"
    />
</div>