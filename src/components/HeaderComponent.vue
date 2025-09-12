<template>
  <nav class="navbar navbar-expand-lg custom-navbar">
    <div class="container-fluid">
      <RouterLink class="navbar-brand text-light" to="/">
        <span class="brand-text">Navigator</span>
      </RouterLink>
      <button class="navbar-toggler custom-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarScroll" aria-controls="navbarScroll" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarScroll">
        <ul class="navbar-nav me-auto my-2 my-lg-0 navbar-nav-scroll" style="--bs-scroll-height: 100px;">
          <li class="nav-item">
            <RouterLink class="nav-link" to="/">Home</RouterLink>
          </li>
          <li class="nav-item">
            <RouterLink class="nav-link" to="/about">About</RouterLink>
          </li>
          <li class="nav-item">
            <RouterLink class="nav-link" to="/pokemons">Pokemons</RouterLink>
          </li>  
        </ul>
        <form class="d-flex" role="search">
          <input class="search-input" type="search" placeholder="Search..." aria-label="Search"/>
          <button class="search-button" type="submit">Search</button>
        </form>
      </div>
    </div>
  </nav>
</template>


<style>
.custom-navbar {
  background-color: #1a1a1a;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
}

.brand-text {
  font-weight: 600;
  font-size: 1.3rem;
  background: linear-gradient(45deg, #7928CA, #FF0080);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.nav-link {
  color: #ffffff !important;
  margin: 0 10px;
  transition: color 0.3s ease;
}

.nav-link:hover {
  color: #FF0080 !important;
}
.router-link-exact-active {
  color: #FF0080 !important;
}

.search-input {
  background-color: #2d2d2d;
  border: none;
  color: white;
  padding: 8px 15px;
  border-radius: 20px;
  margin-right: 10px;
}

.search-input:focus {
  outline: none;
  box-shadow: 0 0 0 2px #FF0080;
}

.search-button {
  background: linear-gradient(45deg, #7928CA, #FF0080);
  border: none;
  color: white;
  padding: 8px 20px;
  border-radius: 20px;
  transition: transform 0.2s ease;
}

.search-button:hover {
  transform: translateY(-2px);
}

.custom-toggler {
  border-color: rgba(255, 255, 255, 0.1);
}
.custom-toggler .navbar-toggler-icon {
  background-image: url("data:image/svg+xml;charset=utf8,%3Csvg viewBox='0 0 30 30' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath stroke='rgba%28255, 255, 255, 0.7%29' stroke-width='2' stroke-linecap='round' stroke-miterlimit='10' d='M4 7h22M4 15h22M4 23h22'/%3E%3C/svg%3E");
}
</style>