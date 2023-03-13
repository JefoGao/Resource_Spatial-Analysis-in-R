# Spatial Objects in package sf

A new standard way to use spatial data in R is provided by the sf package. The package can be used for most of sp package functionality, but is more intuitive, flexible and provides a standardized way to encode and work with spatial vector data.

The packages stores spatial objects as data frames with a special column that contains information about geometry features. That special column is a list with the same length as the number of rows in the data frame. Features describe where spatial objects are located on the Earth. There are also additional attributes, which describe other properties of spatial objects. For example, the geometry of a city can be a point indicating its centre. Its attributes may include its diameter, population, etc.
