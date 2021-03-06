# FckinEquatable
***A new way to deal with Equatable***.

Provide a new protocol name **FckinEquatable**. 

This is also an example for overloading operator in Swift. You can easily create your own operator.

````
protocol FckinEqualtable {
    func equalToAll(_ array: [Self]) -> Bool
    func equalToOne(_ array: [Self]) -> Bool
}
````
With default implementation (protocol extension), you will have this ability for free with just doing something like below:
````
extension String: FckinEqualtable { }
````
Provide 2 default operators:
````
infix operator =&=
infix operator =|=
````
You can custom your own

`equalToAll` is equivalent to `=&=`

`equalToOne` is equivalent to `=|=`

## Example ##

````
if str != "string1" && str != "string2" && str != "string3" {
  // Do something
}
````
With **FckinEquatable**
````
let array = ["string1", "string2", "string3"]
if !str.equalToOne(array) {
  // Do something
}
````
OR 
```
if !(str =|= array) {
  // Do something
}
```
