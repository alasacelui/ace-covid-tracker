<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
            <div class="container">
              <router-link class="navbar-brand text-info" :to="{name:'Home'}">Covid Tracker <i class="fas fa-virus"></i></router-link>
                <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
                  <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarNavDropdown">
                      <!-- Left Side Of Navbar -->
                      <ul class="navbar-nav mx-auto">
                        <li class="nav-item">
                          <router-link class="nav-link" :to="{name:'Home'}">Home</router-link>
                        </li>

                        <li class="nav-item">
                          <router-link class="nav-link" :to="{name:'Tracker'}">Tracker</router-link>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="javascript:void(0)">Contact</a>
                        </li>

                        <li class="nav-item">
                            <router-link class="nav-link" :to="{name:'News'}">News</router-link>
                        </li>
                      
                        <li class="nav-item">
                            <a class="nav-link" href="#">FAQ</a>
                        </li>
                     
                      </ul>
    
                    <!-- Right Side Of Navbar -->
                    <ul class="navbar-nav ml-auto">
                    </ul>
                </div>
            </div>
          </nav>

  <router-view/>
</template>



