<script>


export let user = {
      avatar_url: "/image-user-placeholder.png",
      name: 'Name',
      login: 'username',
      bio: 'Bio',
      public_repos: 0,
      followers: 0,
      following: 0,
      location: 'unknown',
      twitter_username: '@twitter',
      organization_url: 'Link',
      created_at: 'Joined'
    };



  </script>

 
 <section class="user-section">
  <img src= "{user.avatar_url}" class="user-img" id="user-img" alt="profile pic" />
  <div class="user-main">
    <div class="user-top">
      <img
        src="/image-user-placeholder.png"
        class="user-img"
        id="user-img-mobile"
        alt="User profile image"
      />
      <h1 class="user-name" id="user-name" placeholder ="name" >{user.name}</h1>
      <time class="body user-joined" id="user-joined-time"> {user.created_at} </time>
      <h3 class="user-username" id="user-username">@{user.login}</h3>
    </div>
    <p class="body user-bio" id="user-bio">{user.bio}</p>
    <ul class="user-stats">
      <li>
        <h4 class="user-stat-title">Repos </h4>
        <h2 class="user-stat-value" id="user-repos"> {user.public_repos} </h2>
      </li>
      <li>
        <h4 class="user-stat-title"> Followers </h4>
        <h2 class="user-stat-value" id="user-followers"> {user.followers} </h2>
      </li>
      <li>
        <h4 class="user-stat-title"> Following </h4>
        <h2 class="user-stat-value" id="user-following"> {user.following} </h2>
      </li>
    </ul>
   <section class="user-links">
      <div class="user-link-container" id="user-location">
        <span class="body user-link"> {user.location}...</span>
      </div>
      <div class="user-link-container" id="user-twitter"> <span> </span>
        <a href="" class="body user-link" target="_blank" rel="noreferrer"> {user.twitter_username}...</a>
      </div>
      <div class="user-link-container" id="user-website">
        <a href="" class="body user-link" target="_blank" rel="noreferrer"> </a>
      </div>
      <div class="user-link-container" id="user-organization">
        <a href="" class="body user-link" target="_blank" rel="noreferrer"> {user.organization_url} </a>
      </div>

    </section>
  </div>
</section>


<style>

  
.user-section {
    display: flex;
    justify-content: center;
    align-items: flex-start;
    box-shadow: 0 16px 30px -10px rgba(70, 96, 187, 0.2);
    border-radius: 35px;
    padding: 56px;
  }

 li {

	list-style: none;
 }

  
  .user-img {
    margin-right: 36px;
    border-radius: 50%;
    height: 117px;
    width: 117px;
  }
  
  .user-main {
    flex-grow: 1;
  }
  
  .user-top {
    display: grid;
    align-items: center;
    justify-content: space-between;
    grid-template-columns: repeat(2, auto);
    grid-template-rows: repeat(2, auto);
    row-gap: 2px;
  }
  
  #user-img-mobile {
    display: none;
  }
  
  .user-name {
    color: grey;
  }
  
  .user-joined {
    color: grey;
    text-align: right;
    padding: 5px;
  }
  
  .user-username {
    color: #149BF3;
  }
  
  .user-bio {
    color: #4b6a9b;
    margin: 20px 0 32px 0;
  }
  
  .user-stats {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    padding: 16px 32px;
    border-radius: 10px;
    margin-bottom: 36px;
  }
  
  .user-stat-title {
    color: #4b6a9b;
    margin-bottom: 1;
  }
  
  .user-stat-value {
    color: grey;
  }
  
  .user-links {
    display: grid;
    justify-content: space-between;
    align-items: flex-start;
    grid-template-columns: repeat(2, auto);
    grid-template-rows: repeat(2, auto);
    column-gap: 18px;
    row-gap: 18px;
  }

  .user-link-container {
    display: flex;
    justify-content: flex-start;
    align-items: center;
  }

  
  .user-link {
    color: #4b6a9b;
    word-break: break-all;
    margin-left: 18px;
  }
  
  .user-link-container a:hover {
    text-decoration: underline;
  }

 
  @media (max-width: 650px) {
    .user-section {
      padding: 32px 24px;
    }
  
    .user-img {
      margin-right: 20px;
      height: 70px;
      width: 70px;
    }
  
    .user-bio {
      margin: 32px 0 24px 0;
    }
  
    .user-stats {
      margin-bottom: 24px;
      padding: 18px 24px;
    }
  
    .user-links {
      grid-template-columns: 1fr;
      row-gap: 16px;
    }
  }



</style>