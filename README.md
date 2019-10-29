# mrio_common_metadata

`mrio_common_metadata` provides three things:

* A guide on how the [Data Package](https://frictionlessdata.io/specs/data-package/) and [Table Schema](https://frictionlessdata.io/specs/table-schema/) specifications can be used to make MRIO table more consistently formatted and easier to use.
* Translations of some common MRIO tables to this format
* Utility code to help make the previous two objectives possible

# Separating data and metadata

MRIO tables are often given with weird offsets, and multiple or mixed column/row labels, e.g.

![Worksheet with column labels as rows](docs/images/worksheet-1.png)

![Worksheet with multiple column and row labels](docs/images/worksheet-2.png)

Working with this type of data requires writing custom code each time. It's a pain. The biggest problem is the mixing of two data types: The metdata on what each row and column represent, and the numerical table that forms the main body of the worksheet. `mrio_common_metadata` takes the position that these two data streams should be stored separately. It also requires that data be stored in common formats (compressed CSV) with metadata that meets the `Data Package` specification.
