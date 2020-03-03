<template>
  <input type="file" ref="importer" @change="handleImport"/>
</template>

<script>
export default {
  name: 'CsvImport',
  data() {
    return {
      myData: [],
    };
  },
  methods: {
    handleImport(e) {
      const reader = new FileReader();
      const csv = e.target.files[0];
      reader.readAsText(csv);
      reader.onload = (event) => {
        event.target.result
          .split('\n')
          .forEach((el) => {
            const obj = {};
            let row = el;
            if (this.othersSeparators.length) {
              this.othersSeparators.forEach((item) => {
                row = row.split(item).join(this.firstSeparator);
              });
            }
            row = row.split(this.firstSeparator);
            this.labels.forEach((label, index) => {
              if (row[index] && !this.parse) obj[label] = row[index].trim();
              else if (row[index] && this.parse) obj[label] = JSON.parse(row[index].trim());
              else obj.error = true;
            });
            if (!obj.error) this.myData.push(obj);
          });
        this.$emit('input', this.myData);
      };
    },
  },
  computed: {
    firstSeparator() {
      return this.separators[0];
    },
    othersSeparators() {
      return this.separators.slice(1);
    },
  },
  props: {
    labels: Array,
    separators: Array,
    parse: Boolean,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
