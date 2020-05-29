```c#
import models.BaseModel;

struct User: BaseModel {
  ID int; // inherits from base properties. Can't overwrite 
  Username string;
  private myPrivThing string;
  protected myProtectedThing string;

  // take note of &. Passes self as reference
  public doSomething(&self) {

  }

  // passes self as copy
  public doSomethingElse(self) {

  }
}

interface IRun {
  doRun() bool
}

// apply interface to Use
extend User: IRun {
  doRun() { return true; }
}

// Create trait with interface contract
trait Run : IRun {
  doRun() { return true; }
}

// Apply trait to User (like apply interface, but with less code)
extend User: Run {
  // Can overwrite or overload methods
}

// add methods to Struct directly
extend User {
	myFun () {
	}
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTc4Mjg4MjM4LC0xMzM5NjgwMDUwXX0=
-->