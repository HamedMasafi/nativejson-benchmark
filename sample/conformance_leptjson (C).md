# Conformance of leptjson (C)

## 1. Parse Validation


Summary: 34 of 34 are correct.

## 2. Parse Double


Summary: 66 of 66 are correct.

## 3. Parse String

* `["\"\\/\b\f\n\r\t"]`
  * expect: `""\/
	"` (length: 8)
  * actual: `"///
	"` (length: 8)


Summary: 8 of 9 are correct.

## 4. Roundtrip

* Fail:
~~~js
[-1234567890123456789]
~~~

~~~js
[-1.2345678901234568e+18]
~~~

* Fail:
~~~js
[-9223372036854775808]
~~~

~~~js
[-9.2233720368547758e+18]
~~~

* Fail:
~~~js
[1234567890123456789]
~~~

~~~js
[1.2345678901234568e+18]
~~~

* Fail:
~~~js
[9223372036854775807]
~~~

~~~js
[9.2233720368547758e+18]
~~~

* Fail:
~~~js
[0.0]
~~~

~~~js
[0]
~~~

* Fail:
~~~js
[-0.0]
~~~

~~~js
[-0]
~~~

* Fail:
~~~js
[1.2345]
~~~

~~~js
[1.2344999999999999]
~~~

* Fail:
~~~js
[-1.2345]
~~~

~~~js
[-1.2344999999999999]
~~~

* Fail:
~~~js
[5e-324]
~~~

~~~js
[4.9406564584124654e-324]
~~~

* Fail:
~~~js
[2.225073858507201e-308]
~~~

~~~js
[2.2250738585072009e-308]
~~~

* Fail:
~~~js
[1.7976931348623157e308]
~~~

~~~js
[1.7976931348623157e+308]
~~~


Summary: 16 of 27 are correct.

