
<script>

import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();
  
  let username = '';

  const getUsers = async () => {
    try {
      const res = await fetch(`https://api.github.com/users/${username}`);
      const data = await res.json();

      const isValidData = Object.keys(data).length > 0;

      if (isValidData) {
        const user = {
          avatar_url: data.avatar_url || "/image-user-placeholder.png",
          name: data.name || 'Name',
          login: data.login || 'username',
          bio: data.bio || 'Bio',
          public_repos: data.public_repos || 0,
          followers: data.followers || 0,
          following: data.following || 0,
          location: data.location || 'unknown',
          twitter_username: data.twitter_username || '@twitter',
          organization_url: data.organization_url || 'Link',
          created_at: formatDate(data.created_at) || 'Joined'
        };

        dispatch('dataReceived', user);
      } else {
        console.error('Error');
      }

    } catch (error) {
      console.error('Error al obtener los datos del usuario:', error);
    }
  };

  const formatDate = (dateString) => {
    const date = new Date(dateString);
    const options = { day: 'numeric', month: 'long', year: 'numeric' };
    const formattedDate = date.toLocaleDateString('en-US', options);
    return `Joined at ${formattedDate}`;
  };
  
</script>



<form class="search-container" >
  <img src="/icon-search.svg" class="search-icon" alt="Search icon" />
  <input bind:value={username}
    type="text" class="search-input"  placeholder="Username..."   id="github-username"/>
  <button on:click={getUsers} class="btn-search" type="submit">Search</button>
</form>


<style>


.search-container {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 36px 0 24px 0;
    box-shadow: 0 16px 30px -10px rgba(70, 96, 187, 0.2);
    border-radius: 15px;
    padding: 10px;
    width: 100%;
  }
  
  :global(body.dark-theme .search-container) {
    box-shadow: none;
  }
  
  .search-icon {
    margin: 0 24px 0 22px;
  }
  .btn-search {
  align-items: center;
  appearance: none;
  background-color: #3EB2FD;
  background-image: linear-gradient(1deg, #4F58FD, #149BF3 99%);
  background-size: calc(100% + 20px) calc(100% + 20px);
  border-radius: 100px;
  border-width: 0;
  box-shadow: none;
  box-sizing: border-box;
  color: #FFFFFF;
  cursor: pointer;
  display: inline-flex;
  font-family: CircularStd,sans-serif;
  font-size: 1rem;
  height: auto;
  justify-content: center;
  line-height: 1.5;
  padding: 6px 20px;
  position: relative;
  text-align: center;
  text-decoration: none;
  transition: background-color .2s,background-position .2s;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  vertical-align: top;
  white-space: nowrap;
}

  
  .search-input {
   
    font-size: 1.125rem;
    line-height: 25px;
    padding: 6px 0;
    margin-right: 20px;
    flex-grow: 1;
    min-width: 0;
    color:black;
  }
  
</style>