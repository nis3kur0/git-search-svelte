<script>

let isDarkMode = false;

  const toggleDarkMode = () => {
    isDarkMode = !isDarkMode;
    const themeSwitchText = document.getElementById('theme-switch-text');
    themeSwitchText.textContent = isDarkMode ? 'Light' : 'Dark'; 
    document.body.classList.toggle('dark-mode');
  };


</script>

<header>
  <p class="header-logo">devfinder</p> 
  <button class="header-theme-switch-btn body-s" on:click={toggleDarkMode} > 
    <span id="theme-switch-text">Dark</span>
    <img src="/icon-moon.svg" id="image" style="display: inline-block">
  </button>
</header>

<style>


  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .header-logo {
    font-size: 1.625rem;
    line-height: 38px;
	    font-weight: 700;
  }
  
  .header-theme-switch-btn {
    display: flex;
    justify-content: center;
    align-items: flex-end;
    padding: 2.5px;
  }
  
  .header-theme-switch-btn span {
    text-transform: uppercase;
    color: black;
    letter-spacing: 2.5px;
    font-weight: 700;
  }
  
  .header-theme-switch-btn:hover span{
    color: grey;
    fill: grey;
  }
  

  .header-theme-switch-btn {
    background-color: transparent;
    border: none;
    cursor: pointer;
    padding: 0.5rem 1rem;
    border-radius: 5px;
    color: #333; 
  }
  
  #theme-switch-text {
    transition: color 0.3s ease;
  }

</style>