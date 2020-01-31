## ARD-BOOST

This is a mini port of [Boost](https://www.boost.org) library, version 1.72.0 (latest on time of writing). Boost is a set of C++ libraries that provide support for tasks and structures such as linear algebra, pseudorandom number generation, multithreading, image processing, regular expressions, unit testing and many more. It contains 160 individual libraries.

Not all libraries are included in this port. Some libraries, such as threading and filesystem, makes no sence on Arduino hardware. Others are already in the standard, like chrono and array, and can be included in Arduino application. But there are many libraries that are not yet in standard or require C++17 or just great parts of Boost that ported here, in this library.

So far it includes only sub libraries I was able to compile for Arduino. My intention is to add more sub libraries as needed. Requests are welcome.

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
* [mpl](https://www.boost.org/doc/libs/1_72_0/libs/mpl/)
* [optional](https://www.boost.org/doc/libs/1_72_0/libs/optional/)
* [preprocessor](https://www.boost.org/doc/libs/1_72_0/libs/preprocessor/)
* [range](https://www.boost.org/doc/libs/1_72_0/libs/range/)
* [static assert](https://www.boost.org/doc/libs/1_72_0/libs/static_assert/)
* [string_view / string_ref](https://www.boost.org/doc/libs/1_72_0/libs/utility/doc/html/string_ref.html)
* [type index](https://www.boost.org/doc/libs/1_72_0/libs/type_index/)
* [type traits](https://www.boost.org/doc/libs/1_72_0/libs/type_traits/)
* [utility](https://www.boost.org/doc/libs/1_72_0/libs/utility/utility.htm)
* [variant](https://www.boost.org/doc/libs/1_72_0/libs/variant/)
* [variant2](https://www.boost.org/doc/libs/1_72_0/libs/variant2/)

### Get started

### Exception handling

As you may know, exceptions are disabled on Arduino. To catch exceptions from Boost override `boost::throw_exception`. By default, in case of an exception, device will be rebooted.
