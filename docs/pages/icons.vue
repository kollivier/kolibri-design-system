<template>

  <DocsPageTemplate>

    <DocsPageSection title="Overview" anchor="#overview">
      <p>
        Kolibri products use a large number of icons that have a special meaning within our ecosystem. They generally draw from <DocsExternalLink text="Material Icons" href="https://material.io/resources/icons/" />, but may also include custom icons.
      </p>
      <p>
        Importantly, we reference icons by a token specific to the Kolibri Design System rather than Material's names, in order to make token references more meaningful to designers and developers.
      </p>
    </DocsPageSection>

    <DocsPageSection title="Size and text" anchor="#size-text">
      <p>
        Icons should be scaled relative to their surrounding text size. Use the <code>KLabeledIcon</code> component to automatically set a consistent sizing and spacing with associated text:
      </p>
      <DocsShow>
        <h3>
          <KLabeledIcon icon="lesson" label="Header 3" />
        </h3>
        <h4>
          <KLabeledIcon icon="lesson" label="Header 4" />
        </h4>
        <h5>
          <KLabeledIcon icon="lesson" label="Header 5" />
        </h5>
      </DocsShow>

    </DocsPageSection>

    <DocsPageSection title="Color" anchor="#color">
      <p>
        Many of these icons also are used with <DocsInternalLink href="colors" text="conventional colors" /> in the design system. For example, the <DocsInternalLink href="#tokens-coachContent" text="coachContent" code /> icon is often shown using the <DocsInternalLink href="/colors#tokens-coachContent" text="coachContent" code /> color, e.g. <KIcon icon="coachContent" />. Icons often have a default color associated with them, and this can be overridden as needed.
      </p>
      <p>
        When inline with text, icons should usually be the same color as the text:
      </p>
      <DocsDoNot>
        <template v-slot:do>
          <h4>
            <KLabeledIcon icon="video" label="Awesome video" />
          </h4>
        </template>
        <template v-slot:not>
          <h4>
            <KLabeledIcon icon="video" color="green" label="Awesome video" class="wrong-colors" />
          </h4>
        </template>
      </DocsDoNot>
      <p>
        There are exceptions to this pattern, however. For example in the columns of coach reports, most text is dark gray for readibility color while the icons for Mastered, In-progress, etc are colored.
      </p>
    </DocsPageSection>

    <DocsPageSection title="Internationalization" anchor="#i18n">
      <p>
        Avoid using icons that are culture- or context-specific.
      </p>
      <p>
        Icons which in some sense relate to the passage of time must be mirrored when viewed in a right-to-left language. Read more about <DocsExternalLink href="https://material.io/design/usability/bidirectionality.html#mirroring-elements" text="icon bidirectionality" /> from the Material design guidelines.
      </p>
      <p>
        When used with the <code>KIcon</code> component, icons will be automatically flipped when appropriate.
      </p>
    </DocsPageSection>

    <DocsPageSection title="Accessibility" anchor="#a11y">
      <p>
        If it is not purely decorative, ensure that the icon or its parent component has associated text that can be read by a screen reader.
      </p>
    </DocsPageSection>

    <DocsPageSection title="Tokens" anchor="#tokens">
      <h3>UI</h3>
      <DocsIconBlock
        v-for="(name, index) in ui"
        :key="index"
        :name="name"
        definition
        class="icon-block"
      />

      <h3>Features and links</h3>
      <DocsIconBlock
        v-for="(name, index) in features"
        :key="index"
        :name="name"
        definition
        class="icon-block"
      />

      <h3>Users</h3>
      <DocsIconBlock
        v-for="(name, index) in users"
        :key="index"
        :name="name"
        definition
        class="icon-block"
      />

      <h3>Content</h3>
      <DocsIconBlock
        v-for="(name, index) in content"
        :key="index"
        :name="name"
        definition
        class="icon-block"
      />

      <h3>Progress tracking</h3>
      <DocsIconBlock
        v-for="(name, index) in progressTracking"
        :key="index"
        :name="name"
        definition
        class="icon-block"
      />

      <h3>Coaching</h3>
      <DocsIconBlock
        v-for="(name, index) in coaching"
        :key="index"
        :name="name"
        definition
        class="icon-block"
      />

    </DocsPageSection>

  </DocsPageTemplate>

</template>


<script>

  import DocsIconBlock from '~/common/DocsIconBlock';

  export default {
    components: {
      DocsIconBlock,
    },
    computed: {
      ui() {
        return [
          'back',
          'forward',
          'clear',
          'dropdown',
          'language',
          'menu',
          'search',
          'dot',
          'error',
          'done',
        ];
      },
      features() {
        return ['learn', 'device', 'profile', 'login', 'logout', 'coach', 'facility'];
      },
      progressTracking() {
        return [
          'correct',
          'incorrect',
          'helpNeeded',
          'hint',
          'mastered',
          'rectified',
          'inProgress',
          'notStarted',
        ];
      },
      coaching() {
        return ['lesson', 'question', 'quiz'];
      },
      content() {
        return [
          'app',
          'audio',
          'channel',
          'document',
          'exercise',
          'topic',
          'video',
          'html5',
          'slideshow',
          'unlistedchannel',
          'coachContent',
        ];
      },
      users() {
        return ['classroom', 'group', 'people', 'permission', 'person'];
      },
    },
  };

</script>


<style lang="scss" scoped>

  .icon-block {
    display: inline-block;
    width: 250px;
  }

  // hack to simulate bad behavior
  /deep/ .wrong-colors svg {
    fill: blue !important;
  }

</style>
