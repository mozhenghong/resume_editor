<template>
  <div id="Editor">
    <nav>
      <ol>
        <li class="active">
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-credentials_icon"></use>
          </svg>
        </li>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-WORK"></use>
          </svg>
        </li>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-xuexi"></use>
          </svg>
        </li>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-xiangmu"></use>
          </svg>
        </li>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-jineng"></use>
          </svg>
        </li>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-dianhua"></use>
          </svg>
        </li>
      </ol>
    </nav>
    <ol></ol>
  </div>
</template>

<script>
export default {};
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
    ol{
        flex-grow: 1.0;
    }
}
</style>


