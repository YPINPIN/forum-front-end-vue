<template>
  <div class="album py-5 bg-light">
    <div class="container">
      <!-- UserProfileCard -->
      <UserProfileCard />

      <div class="row">
        <div class="col-md-4">
          <!-- UserFollowingsCard -->
          <UserFollowingsCard />
          <br />
          <!-- UserFollowersCard -->
          <UserFollowersCard />
        </div>

        <div class="col-md-8">
          <!-- UserCommentsCard -->
          <UserCommentsCard />
          <br />
          <!-- UserFavoritedRestaurantsCard -->
          <UserFavoritedRestaurantsCard />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import UserProfileCard from './../components/UserProfileCard'
import UserFollowingsCard from './../components/UserFollowingsCard'
import UserFollowersCard from './../components/UserFollowersCard'
import UserCommentsCard from './../components/UserCommentsCard'
import UserFavoritedRestaurantsCard from './../components/UserFavoritedRestaurantsCard'

export default {
  components: {
    UserProfileCard,
    UserFollowingsCard,
    UserFollowersCard,
    UserCommentsCard,
    UserFavoritedRestaurantsCard,
  },
}
</script>
