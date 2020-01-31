## ARD-BOOST

This is a mini port of [Boost](https://www.boost.org) library, version 1.72.0 (latest on time of writing). Boost is a set of C++ libraries that provide support for tasks and structures such as linear algebra, pseudorandom number generation, multithreading, image processing, regular expressions, unit testing and many more. It contains 160 individual libraries.

Not all libraries are included in this port. Some libraries, such as threading and filesystem, makes no sence on Arduino hardware. Others are already in the standard, like chrono and array, and can be included in Arduino application. But there are many libraries that are not yet in standard or require C++17 or just great parts of Boost. These ported here in this library.

So far it includes only libraries I was able to compile for Arduino. My intention is to add more libraries as needed. Requests are welcome.

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

Before include of any Boost library make sure to include `ard-boost.h`. This will setup exception handling and fix some compile problems. Otherwise the usage is the same as usual. Include any of supported library and you are good to go.

```cpp
#include "ard-boost.h"
#include "boost/range.hpp"

void setup()
{
    int sum = 0;
    for (int i : boost::irange(5, 10))
        sum += i;
}

void loop() { }
```

### Exception handling

As you may know, exceptions are disabled on Arduino. Instead of throwing exception, Boost will call special handler function with exception as argument. It is defined in `ard-boost.h` and by default, in case of an exception, will reboot the device.

To provide your own exception handler, make sure to define `CUSTOM_EXCEPTION_HANDLER` **before** include of `ard-boost.h` and override exception function. For example:

```cpp
#define CUSTOM_EXCEPTION_HANDLER
#include "ard-boost.h"

void boost::throw_exception(const std::exception& ex) {
    // Log exception and reboot
    Particle.publish("Error", ex.what(), PRIVATE);
    System.reset();
}

void setup { }
void loop() { }
```

**Note!** The exception handler must not return (protected by *noreturn* attribute).
