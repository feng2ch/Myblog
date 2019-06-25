<template>
  <div class ="wrap posts animated fadeIn" v-if="showSearch">	
    <input v-focus class="search" placeholder="请输入搜索内容"
      v-model="key"
      @keyup.enter="search({key:key})"
    
      />	
	</div>
</template>
<script type="text/javascript">
import { mapState, mapMutations, mapActions} from 'vuex'
  export default {
    data() {
      return {
          key: ''
      }
    },
	  computed: {
	    ...mapState(['showSearch'])
    },
    
    directives: {
      focus: {
        inserted: function (el) {
          el.focus()
        }
      }
    },

    methods: {
      ...mapActions(["searchArticles"]),
      ...mapMutations(['set_search']),
      search(params) {                   
        this.$router.push({ path: '/articles', query: params}); 
        this.searchArticles(params)
        this.set_search(false);
        this.key = ''
      }
    }
  }
</script>
<style lang="scss" type="stylesheel/scss" scoped>
    .wrap{
    z-index:38;
    position:fixed;
    top:0px;
    left:0px;
    width:100%;
    height:100%;
    background-color: rgba(0, 0, 0, 0.6);
    display: flex;
    justify-content: center;
    align-items: center;
        .search{
            position:fixed;
           
            width: 15.0rem;
            height:3.0rem;
            background-color: transparent;
            color: #fff;
            text-align: center;
            font-size: 1.7rem;
            padding: 10px;
            border: 1px solid #fff;
            font-weight: bold;
            border-radius:15px;
        }
        input::-webkit-input-placeholder {
        color:#fff;
        font-weight:normal;
        }
    }

  @media screen and (max-width: 750px){
      .search{
        width: 80% !important;
        font-size: 0.5rem !important;
      }
  }
</style>