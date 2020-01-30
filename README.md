## ARD-BOOST

This is a mini port of [Boost](https://www.boost.org) library, version 1.72.0 (latest on time of writing).
Not all sub libraries are included.
Some libraries, such as threading and filesystem, makes no sence on Arduino hardware.
But there are many, I find very usable, that do actually work great.

So far it includes only sub libraries I was able to compile for Arduino.
My intention is to add more sub libraries as needed.
Requests are welcome.

### Currently supporting

The following is a list of libraries that included intentionally. Because many of these has dependencies to other parts of
Boost library, all dependencies was included too. It includes libraries not listed here but may, very well,
be included as well.

* [Any](https://www.boost.org/doc/libs/1_72_0/libs/any/)
* [Concept Check](https://www.boost.org/doc/libs/1_72_0/libs/concept_check/)
* [Mp11](https://www.boost.org/doc/libs/1_72_0/libs/mp11/)
* [Optional](https://www.boost.org/doc/libs/1_72_0/libs/optional/)
* String_view/[String_ref](https://www.boost.org/doc/libs/1_72_0/libs/utility/doc/html/string_ref.html)
* [Variant](https://www.boost.org/doc/libs/1_72_0/libs/variant/)
* [Variant2](https://www.boost.org/doc/libs/1_72_0/libs/variant2/)

