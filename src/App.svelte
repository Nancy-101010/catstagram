<script>
    import {onMount} from "svelte";
	import TimeLine from './Components/TimeLine.svelte';
	import Sidebar from './Components/Sidebar.svelte';
    import Footer from "./Components/Footer.svelte";
    import Header from "./Components/Header.svelte";
    import Main from './Components/Main.svelte';
    
    let data = {};
    const API = "https://kittygram-api.now.sh/"

    onMount (async ()=> {
        const response = await fetch(API)
        data= await response.json();
    });

</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Lato:wght@300;400&display=swap');


    :global(body){
        background-color:  antiquewhite
        color rgba(38,38,38,0.7);
        font-family:"lato", sans-serif; 
        margin: 0;
        padding: 0; 
        }   
    :global(h1,h2,h3)  {
        margin: 0;
        padding: 0;
    }  
</style>

<Header/>  
<Main>
<TimeLine posts={data.posts}/>
<Sidebar  {...data.user}/>
<Footer />
</Main>