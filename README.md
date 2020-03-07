# TKinter Managed Frames

Adds a Frame widget with a built in content manager.
## Installation
Download from PYPI.  
`pip install TKinterManagedFrame`  
or  
`python -m pip install TKinterManagedFrame`
## Methods
- `__init__()`

  - args
    - `master`: a tkinter widget that is capable of having children
      - this includes `Tk`, `Frame`, and `TopLevel`
    - `nameList`: A list of names that will be associated with empty `Frame` objects.
    - `initialIndex`: the first `Frame` that will be displayed.
      - if this is not present in `nameList`, a `Frame` will be created to associate with it.
    - `options`: takes any number of keyword arguments.
      - see the documentation for `tkinter.Frame` for the full list of options.
- `getCurrentFrameKey()`
  - returns the key of the currently displayed `Frame`.
- `getCurrentFrame()`
  - returns a reference to the currently displayed `Frame`
- `getFrameAtKey()`
  - args
    - `key`: the key at which the requested `Frame` is stored
  - returns a reference to the `Frame` at the given `key`.
  - `@raises` `KeyError`: if `key` is not being managed
- `addOption()`
  - args
    - `inputFrame`: the `Frame` object to be added
    - `key`: the location at which `inputFrame' will be stored in the manager.
  - `@raises KeyError`: if `key` is already being managed
    - use `updateOption()` to change an already managed frame.
- `updateOption()`
  - args
    - `inputFrame`: the frame to place at `key`
    - `key`: the location at which to place `inputFrame`
  - `@raises KeyError`: if `key` is not being managed
- `changeOption()`
  - args
    - `key`: the the key of the desired `Frame`.
  - `@raises KeyError` if `key` is not being managed.
- `setOption()`
  - args
    - `inputFrame`: the `Frame` to be added
    - `key`: the key at which to store `inputFrame`
  - `@raises KeyError` if `key` is already being managed
- `removeOption()`
  - args
    - `key`: the key value at which the `Frame` to be deleted is stored
    - `default`: (defaults to an arbitrary frame), the key value of the frame that will be displayed if `key` references the currently displayed `Frame`
  - `@raises KeyError` if either `key` or `default` are not being managed.