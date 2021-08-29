<template>
  <div class="card mb-3">
    <div class="row no-gutters">
      <div class="col-md-4">
        <img :src="profile.image" width="300px" height="300px" />
      </div>
      <div class="col-md-8">
        <div class="card-body">
          <h5 class="card-title">{{ profile.name }}</h5>
          <p class="card-text">
            {{ profile.email }}
          </p>
          <ul class="list-unstyled list-inline">
            <li>
              <strong>{{ profile.commentsLength }}</strong> 已評論餐廳
            </li>
            <li>
              <strong>{{ profile.favoritedRestaurantsLength }}</strong>
              收藏的餐廳
            </li>
            <li>
              <strong>{{ profile.followingsLength }}</strong> followings
              (追蹤者)
            </li>
            <li>
              <strong>{{ profile.followersLength }}</strong> followers (追隨者)
            </li>
          </ul>
          <p>
            <router-link
              v-if="profile.isAdmin"
              :to="{ name: 'user-edit', params: { id: profile.id } }"
              ><button type="submit" class="btn btn-primary">
                edit
              </button></router-link
            >
            <button
              v-else-if="isFollowed"
              type="submit"
              class="btn btn-danger"
              @click.stop.prevent="deleteFollowing"
            >
              取消追蹤
            </button>
            <button
              v-else
              type="submit"
              class="btn btn-primary"
              @click.stop.prevent="addFollowing"
            >
              追蹤
            </button>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    profile: {
      type: Object,
      required: true,
    },
    initialIsFollowed: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      isFollowed: this.initialIsFollowed,
    }
  },
  methods: {
    addFollowing() {
      this.isFollowed = true
    },
    deleteFollowing() {
      this.isFollowed = false
    },
  },
}
</script>
