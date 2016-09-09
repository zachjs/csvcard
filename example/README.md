Examples
========

## Simple example

This is a simple example with some test data, an appropriate configuration, and the output produced.

  - [data](simple_data.csv)
  - [config](simple_config.json)
  - [result](simple_out.vcf)

The result given was generated using exactly the following execution:
```
go run main.go example/simple_config.json < example/simple_data.csv > example/simple_out.vcf
```

## Config I use

This tool was developed to distribute contact data stored in Google Sheets among the members of a the [CMU chapter of Delta Tau Delta](https://www.facebook.com/cmudelt). This is the config I use to generate the vCard distributed internally.

  - [config](delt.json)

I have obviously not included the member data and resulting output.
