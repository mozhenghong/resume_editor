<template>
  <div id="Editor">
    <nav>
      <ol>
        <li
          v-for="i in [0,1,2,3,4,5]"
          v-bind:class="{active:currentTag===i}"
          v-on:click="currentTag=i"
        >
          <svg class="icon" aria-hidden="true">
            <use v-bind:xlink:href="`#icon-${icons[i]}`"></use>
          </svg>
        </li>
      </ol>
    </nav>
    <ol class="list">
      <li v-bind:class="{active:currentTag===0}" class="credentials">
        <credentials v-bind:credentials="resume.credentials"></credentials>
      </li>
      <li v-bind:class="{active:currentTag===1}">
        <workHistory v-bind:workHistory="resume.workHistory"></workHistory>
      </li>
      <li v-bind:class="{active:currentTag===2}">
        <educationHistory v-bind:educationHistory="resume.educationHistory"></educationHistory>
      </li>
      <li v-bind:class="{active:currentTag===3}">
         <project v-bind:project="resume.project"></project>
      </li>
      <li v-bind:class="{active:currentTag===4}"> 
        <skills v-bind:skills="resume.skills"></skills>
      </li>
      <li v-bind:class="{active:currentTag===5}"> 
        <contact v-bind:contact="resume.contact"></contact>
      </li>
    </ol>
  </div>
</template>

<script>
import credentials from './credentialsEditor.vue'
import workHistory from './WorkHistoryEditor.vue'
import educationHistory from './educationEditor.vue'
import project from './projectEditor.vue'
import skills from './skillsEditor.vue'
import contact from './contactEditor'
export default {
  props: ['resume'],
  components: {credentials, workHistory, educationHistory, project, skills, contact},
  data() {
    return {
      currentTag: 0,
      icons: [
        "credentials_icon",
        "WORK",
        "xuexi",
        "xiangmu",
        "jineng",
        "dianhua"
      ],
    }
  },
};
</script>

<style lang="scss">
#Editor {
  display: flex;
  background: #fff;
  nav {
    background: #254665;
    ol {
      margin: 16px 0;
      li {
        padding: 16px;
        .icon {
          width: 35px;
          height: 35px;
          fill: #fff;
        }
      }
      li.active {
        background: #fff;
        .icon {
          fill: #254665;
        }
      }
    }
  }
  ol.list {
    flex-grow: 1;
    overflow: auto;
    li {
      display: none;
      padding: 25px;
      .break{
      border-bottom:1px solid  #254665;
      margin-bottom: 10px;
      position: relative;
        .remove{
          position: absolute;
          right: 0;
          top: 0;
          z-index: 1;
          color: #254665;
        }
      }
    }
    li.active {
      display: block;
    }
  }
}
</style>


