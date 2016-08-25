csvcard
=======

`csvcard` is a simple tool that converts contact information stored as CSV into a portable vCard understood by any contacts application. The CSV must contain a header line which names the data in each column.

## Usage

`csvcard` reads CSV data from `stdin` and outputs vCard data to `stdout`. It takes the path to a configuration file as its only argument.
For example:
```
$ cat /path/to/data.csv | go run main.go /path/to/config.json > /path/to/out.vcf
```

## Configuration

The configuration file is a JSON document which specifies the name of the column containing each piece of data. A specific attribute will only be included in each vCard if the column names for the necessary inputs have been specified. The keys for all [supported attributes](#supported-attributes) are listed below.
Example config:
```
{
  "fullName": "Full Name",
  "firstName": "First",
  "lastName": "Last",
  "email": "Email",
  "phone": "Phone Number",
}
```
More examples are provided [here](example/).

## Supported Attributes

  - Full name (`fullName`)
  - First/last name components (`firstName`, `lastName`)
  - Phone number (`phone`)
  - Email (`email`)
  - Unique identifier\* (`uid`)

**\*Note:** Some contacts apps support merging contacts if re-imported if each version of a person's contact has the same unique identifier. The field specified for the unique identifier will be converted into a UUID for each contact.

## Examples

Sample configurations and data can be found in [example/](example/).

## License

This software is released under the MIT license located in [LICENSE.md](LICENSE.md).
