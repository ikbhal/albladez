<script>
    let count = 0;
    function handleClick(){
        count += 1;
    }
</script>
<div id="like_button">
    <p>Note: I dont know yet how to save for now Its only increment once for one URLSearchParams,
        will loss the count if user refresh
    </p>

    <button on:click={handleClick}>
        Claps {count}
        {count==1 ? 'time' : 'times'}
    </button>


</div>