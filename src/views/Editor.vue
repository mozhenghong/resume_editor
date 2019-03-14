<template>
  <div id="Editor">
    <nav>
      <ol>
        <li v-for="i in [0,1,2,3,4,5]"  v-bind:class="{active:currentTag===i}" v-on:click="currentTag=i" >
          <svg class="icon" aria-hidden="true">
            <use v-bind:xlink:href="`#icon-${icons[i]}`"></use>
          </svg>
        </li>
      </ol>
    </nav>
    <ol class="list">
      <li v-for="i in [0, 1, 2, 3, 4, 5]" v-bind:class="{active:currentTag===i}"> tab{{i+1}}</li>
    </ol>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentTag: 0,
      icons: ['credentials_icon', 'WORK', 'xuexi', 'xiangmu', 'jineng', 'dianhua' ]
    }
  }
};
</script>

<style lang="scss">
#Editor {
    display: flex;
    background: #fff;
    nav{
        background: #254665;
        ol{
            margin: 16px 0;
            li{
                padding: 16px;
                .icon{
                    width: 35px;
                    height: 35px;
                    fill: #fff;
                }
            }
            li.active{
                background: #fff;
                .icon{
                    fill: #254665;
                }
            }
        }
    }
    ol.list{
        flex-grow: 1.0;
        li{
          display: none;
        }
        li.active{
          display: block;
        }
    }
}
</style>


