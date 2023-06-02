<script>
    import pumba from './assets/caracal.jpg'
    import lole from './assets/lole.jpg'
    import poobie from './assets/poobie.jpg'
    import boyfriends from './assets/boyfriends.jpg'
    import { scale } from 'svelte/transition'
    import { reveal } from 'svelte-reveal';
    import { onMount } from "svelte";

    let show = false;
    onMount(()=>{
    requestAnimationFrame(()=>{
        setTimeout(()=>{
            show = true
        }, 0)
    })
})
</script>

<main>
    {#if show}
    <div id="top-container">
        <div id="top-content">
            <div id="top-image">
            <img 
                in:scale={{
                    duration: 500
                }}
                src={pumba}
                alt="meow"
            />
            </div>
            <h2 in:scale={{
                delay: 500
            }}>yack</h2>
        </div>
    </div>
    <div id="cats-container">
        <div id="cats-content">
            <div id="cats-image">
            <img use:reveal={{ transition: "spin"}}
                src={lole}
                alt="meow"
            >
            <img use:reveal={{ delay: 500, transition: "spin"}}
                src={poobie}
                alt="meow"
            >
            </div>
            <h3 use:reveal={{ delay: 600, transition: "fly"}}>
                lole y poobie
            </h3>
            <h4 use:reveal={{delay: 600, transition: "fly"}}>
                two pretty boyfriends, two pretty cats    
            </h4>
        </div>  
    </div>
    <div id="boyfriends-container">
        <div id="boyfriends-content">
            <div id="boyfriends-image">
                <img use:reveal={{transition: "fly"}} src={boyfriends} alt="mow">
            </div>
            <h3 use:reveal={{delay: 100, transition: "blur"}}>I love you so much jax!!</h3>
            <h5 use:reveal={{delay: 175, transition: "fade"}}>
                You are the world to me. You fill my life with joy. 
                I feel so lucky to have you in my life, with me in every moment. 
                I have never in my life felt as understood as I have with you. 
                Thank you so much for being so good to me. I love you with all my heart Jax.
            </h5>
        </div>
    </div>
    {/if}
</main>

<style>

    #top-container {
        height: 100vh;
        display: flex;
        justify-content: center;
    }

    #top-content {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    #top-image {
        width: 45%;
        display:  flex;
        align-items: center;
        justify-content: center;
    }

    #boyfriends-container {
        height: 100vh;
        display: flex;
        justify-content: center;
    }

    #boyfriends-content {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    #boyfriends-image {
        width: 45%;
        display:  flex;
        align-items: center;
        justify-content: center;
    }

    #cats-container {
        height: 100vh;
        display: flex;
        justify-content: center;
    }

    #cats-content {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    #cats-image {
        width: 45%;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
    }
    
    h3 {
        margin-bottom: 5px;
    }
    
    h4 {
        margin-top: 0px;
    }

    img {
        width: 100%;
        padding: 5px;
        object-fit: contain;
    }
</style>