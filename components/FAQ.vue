<template>
  <b-container
    id="gettingStarted"
    style="min-height: 60vh"
    class="d-flex flex-column justify-content-center align-items-center mt-5 mb-5"
  >
    <h1 class="display-4 text-center">FAQ.</h1>

    <b-container class="d-flex align-items-center">
      <VueFaqAccordion :items="myItems" />
    </b-container>
    <p class="text-center">
      Please consider leaving us <a href="feedback">feedback</a>.
    </p>
  </b-container>
</template>

<script>
import VueFaqAccordion from 'vue-faq-accordion'

export default {
  components: {
    VueFaqAccordion,
  },
  data() {
    return {
      myItems: [
        {
          title: 'How do I start a party?',
          value:
            'After you have installed the Jelly-Party extension, you will see a little Jellyfish in the top right corner of your browser. Simply click the jellyfish and select "Start a new party".<br/><br/>Your party will now be accessible through the magic link, that you will see in the top. Click the "Copy"-button, to copy the magic link to your clipboard and and share it with your peers. When they open the link, they will automatically join your party.',
          category: 'Start a party',
        },
        {
          title: 'Do only I have the controls when I start a party?',
          value:
            'No. Everybody has controls. So if anybody plays/pauses/jumps in the video, it will be synchronized across all party peers. Power to the people!',
          category: 'Start a party',
        },
        {
          title: 'How do I join a party using a magic link?',
          value:
            'The magic link is a convenient way to invite people to your party. You simply share the magic link, and people can join your party using it. Your peers have to open the magic link in a Chrome browser <b>with Jelly-Party already installed.</b> They will then be taken to the video the party was last watching, and automatically join the party.<br/><br/><b>In most cases, you will want to use the magic link!</b>',
          category: 'Join a party',
        },
        {
          title: 'How do I join a party by Id?',
          value:
            'If you prefer to share only the party Id (e.g. when you\'re in a call), you can also join a party by Id.<br/><br/><b>Note, however, that you are in charge of navigating to the correct video in this case</b>. Jelly-Party will <b>not</b> automatically take you to the correct video (for more information, check out the "General"-tab).',
          category: 'Join a party',
        },
        {
          title:
            "Help! I joined the party, but we're not seeing the same video!",
          value:
            "If you join through a magic link, you will be redirected to the video of the party initiator.<br/><br/>If you join a party by Id, however, Jelly-Party <b>won't redirect you to the video you want to watch.</b> In this case, you must make sure that you are watching the same video as the party, yourself.",
          category: 'Join a party',
        },
        {
          title: 'Help! I switched tabs and now Jelly-Party lost my party!',
          value:
            'Due to the nature of how Chrome extensions works, Jelly-Party lives inside your <b>tab</b>. This means that you will always see the Jelly-Party status <b>for your current tab!</b> You can be in several Jelly-Parties at the same time, in different tabs, if you wish.<br/><br/>When opening the Jelly-Party extension, make sure to check that you are in the tab where your party was last running.',
          category: 'General',
        },
        {
          title: 'What happens when I move to another website in the same tab?',
          value:
            'Jelly-Party only lives in your current <b>tab context</b>. If you navigate to another website within a tab (e.g. from netflix.com to youtube.com), Jelly-Party will unfortunately lose your session.',
          category: 'General',
        },
        {
          title:
            'When I click on another video, will all people in the party see that video, too?',
          value:
            'No. Jelly-Party does not synchronize where you currently are on a website. It synchronizes the video you are currently watching with whatever other people are currently watching — this should be the same, but you are in charge to make sure that this is the case.',
          category: 'General',
        },
        {
          title: 'What happens when I switch to another video?',
          value:
            'Jelly-Party will do its best to keep track of your current video. You are in charge, however, to ensure that everybody is watching the same video. Otherwise Jelly-Party may synchronize different videos.',
          category: 'General',
        },
        {
          title:
            'Why do you require permission to read which websites I visit?',
          value:
            "Jelly-Party needs to look at your URL to figure out if it's a magic link. No data concerning the websites you visit is shared with us, with the exeception of the magic link that we forward to your party peers.",
          category: 'General',
        },
      ],
    }
  },
}
</script>

<style>
.faq-wrapper {
  margin-left: auto !important;
  margin-right: auto !important;
  margin-top: 3em !important;
}

.faq__nav {
  border: none !important;
}

.accordion__item {
  border-bottom: none !important;
}

.accordion {
  border: none !important;
}

.faq__nav-item {
  padding: 1em !important;
}
</style>
