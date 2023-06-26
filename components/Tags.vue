<template>
  <span v-if="false" />
</template>
<script>
export default {
  props: {
    
    image: {
      type: String,
      default: `${process.env.BASE_URL}${require('~/assets/img/white.png')}`,
    },
    imageWidth: {
      type: Number,
      default: 200,
    },
    imageHeight: {
      type: Number,
      default: 200,
    },
  },
  head() {
    return {
      titleTemplate: this.title ? `${this.title} - %s` : '%s',
      meta: [
        {
          hid: 'twitter:card',
          property: 'twitter:card',
          content: 'summary',
        },
        {
          hid: 'twitter:title',
          property: 'twitter:title',
          content: this.documentTitle,
        },
        {
          hid: 'twitter:image',
          property: 'twitter:image',
          content: this.image,
        },
        {
          hid: 'twitter:image:alt',
          property: 'twitter:image:alt',
          content: this.documentTitle,
        },
        {
          hid: 'twitter:description',
          property: 'twitter:description',
          content: 'this.documentDynamicDescription',
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: this.documentTitle,
        },
        {
          hid: 'og:image',
          property: 'og:image',
          content: this.image,
        },
        {
          hid: 'og:image:width',
          property: 'og:image:width',
          content: this.imageWidth,
        },
        {
          hid: 'og:image:height',
          property: 'og:image:height',
          content: this.imageHeight,
        },
        {
          hid: 'og:image:secure_url',
          property: 'og:image:secure_url',
          content: this.image,
        },
        {
          hid: 'og:image:alt',
          property: 'og:image:alt',
          content: this.documentTitle,
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: 'this.documentDynamicDescription',
        },
      ],
    };
  },
  computed: {
    documentTitle() {
      return `Test title with spaces \n\n`;
    },

    // documentDynamicDescription() {
    //   const isTable = this.documentType === DocumentTypes.table ? 'Table, ' : '';
    //   const isSubTitle = this.subTitle != null ? `, ${this.subTitle}` : '';

    //   return `Ocean of Lights - ${isTable}${this.documentTitle}${isSubTitle}`;
    // },

    // documentLink() {
    //   if (this.documentType == null && this.documentName == null && this.language == null) {
    //     return `${process.env.BASE_URL}/`;
    //   } else if (
    //     this.documentType != null &&
    //     ![DocumentTypes.chapter, DocumentTypes.page, DocumentTypes.table, DocumentTypes.tablet].includes(this.documentType)
    //   ) {
    //     return `${process.env.BASE_URL}/${this.documentType}`;
    //   } else if (this.documentType === DocumentTypes.tablet) {
    //     return `${process.env.BASE_URL}/${this.documentName}-${this.language}`;
    //   } else {
    //     return `${process.env.BASE_URL}/${this.documentType}/${this.documentName}-${this.language}`;
    //   }
    // },
  },
//   mounted() {
//     document.addEventListener('copy', (event) => {
//       const additionalText = `\n\n${this.documentTitle}\n${this.documentLink}`;
//       this.$store.dispatch('global/initAdditionalInfoInCopiedText', additionalText);

//       const selection = window.getSelection();
//       const range = selection.getRangeAt(0);
//       const clonedRange = range.cloneRange();
//       const tempContainer = document.createElement('div');
//       tempContainer.appendChild(clonedRange.cloneContents());
//       tempContainer.textContent += additionalText;

//       event.clipboardData.setData('text/plain', tempContainer.textContent);

//       event.preventDefault();
//     });
//   },
};
</script>
