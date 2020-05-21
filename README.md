# Spreadsheet importer ( Excel, CSV )
## Description
Component that allows you to import spreadsheet file into web. You can map data by use labels.
Based on Vue!

## File Data

  Name | Age
  --- | --- 
  Rick | 64
  Morty | 13

## Example in use

```
  <CsvImport v-model="val"  :labels="['name', 'surname']" :separators="[',']" />
```

## Output
```
  data() {
    return {
      val:[
        {
          name: "Srele",
          surname: "12"
        }
        ...
      ],
    };
  }
```

## Props

Name | Description | Type
--- | --- | ---
labels | Assign content to variable | Array
separators | Separators used in file extension | Array
parse | If want to parse from JSON | Boolean
