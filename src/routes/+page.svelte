<script>


import Header from "./header.svelte";

import Search from "./search.svelte";

import Display from "./Display.svelte";



export let user = {
      avatar_url: "/image-user-placeholder.png",
      name: 'Name',
      login: 'username',
      bio: 'Bio',
      public_repos: 0,
      followers: 0,
      following: 0,
      location: 'Unknown',
      twitter_username: '@twitter',
      organization_url: 'Link',
      created_at: 'Joined'
    };


  function handleData(e) {
   
    user = e.detail;
  }


</script>

<main>
  
  <Header />
  <Search on:dataReceived={handleData} />
  <Display {user} />


</main>

<style>
:global(body) {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: white;
	font-family: 'Space Mono', monospace;
    min-height: 100vh;
    padding: 75px 96px;
    
  }

  :global(.dark-mode)  {
    background-color: #141d2f; 
    color: #eee; 
     }


  :global(.dark-mode form ){

    background-color: #25375a;
    color: #eee
  }
  
  :global(.dark-mode .header-logo) {
	color: #eee; 
  }
  
  :global(.dark-mode .header-theme-switch-btn) {
    color: #ddd; 
  }

  :global(.dark-mode .user-stats) {

	background-color: #25375a;
    color: #eee
	 }

  :global(.dark-mode #theme-switch-text) {
    color: #ddd; 
  }

  :global(.dark-mode main .user-section) {
    background-color:#25375a;
    color:#eee;
    
  }

  :global(.dark-mode .user-stats)
 {
    background-color: #141d2f;
    color: #141d2f;

 }
 :global(.dark-mode #image) {
    content: url('/icon-sun.svg'); 
}


  

</style>