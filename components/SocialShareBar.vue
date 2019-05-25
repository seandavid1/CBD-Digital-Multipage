<template>
    <social-sharing class="social-share" :url="url"
                        :title="title"
                        :description="description"
                        :hashtags="hashtags"
                        inline-template>
                        <div>
                            <span class="label">Share:</span>
                            <network network="facebook">
                              <i class="fa fa-facebook-square"></i>
                            </network>
                            <network network="linkedin">
                              <i class="fa fa-linkedin-square"></i>
                            </network>
                            <network network="twitter">
                              <i class="fa fa-twitter-square"></i>
                            </network>
                        </div>
    </social-sharing>
</template>

<script>
export default {
  props: ['url', 'title', 'description', 'hashtags']
}
</script>

<style scoped> 
</style>