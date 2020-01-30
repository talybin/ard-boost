## ARD-BOOST

This is a mini port of [Boost](https://www.boost.org) library, version 1.72.0 (latest on time of writing).
Not all sub libraries are included.
Some libraries, such as threading and filesystem, makes no sence on Arduino hardware. Others are already in the standard,
like chrono and array, and can be included in Arduino application.
But there are many libraries that are not yet in standard or require C++17 or just great parts of Boost that ported
here, in this library.

So far it includes only sub libraries I was able to compile for Arduino.
My intention is to add more sub libraries as needed.
Requests are welcome.

### Currently supporting

The following is a list of libraries that included intentionally. Because many of these has dependencies to other parts of
Boost library, all dependencies was included too. It includes libraries not listed here but may, very well,
be included as well.

* [any](https://www.boost.org/doc/libs/1_72_0/libs/any/)
* [concept check](https://www.boost.org/doc/libs/1_72_0/libs/concept_check/)
* [container](https://www.boost.org/doc/libs/1_72_0/libs/container/)
* [container hash](https://www.boost.org/doc/libs/1_72_0/libs/container_hash/)
* [core](https://www.boost.org/doc/libs/1_72_0/libs/core/)
* [functional](https://www.boost.org/doc/libs/1_72_0/libs/functional/)
* [iterator](https://www.boost.org/doc/libs/1_72_0/libs/iterator/)
* [mp11](https://www.boost.org/doc/libs/1_72_0/libs/mp11/)
* [optional](https://www.boost.org/doc/libs/1_72_0/libs/optional/)
* [string_view / string_ref](https://www.boost.org/doc/libs/1_72_0/libs/utility/doc/html/string_ref.html)
* [variant](https://www.boost.org/doc/libs/1_72_0/libs/variant/)
* [variant2](https://www.boost.org/doc/libs/1_72_0/libs/variant2/)
