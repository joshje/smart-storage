SmartStorage Light
==================

This is a lightweight version of ahume's HTML5 localStorage wrapper. It supports `get` and `set`, including expiry dates and json objects.

Examples
--------

    var store = new SmartStorage("my_store");

    // Store string
    store.set("key", "value");
    store.get("key");
    >> "value"

### Expiry

Store object/hash with expiry time of 2 minutes.

    store.set("my_object", {"key1": "value1", "key2": "value2"}, 120 * 1000); // Expires in 120*1000 = 2 minutes.
    store.get("my_object").key2;
    >> "value2"

    store.set("my_int", 10);
    store.incr("my_int");
    >> 11
    store.incr("my_int");
    >> 12

Methods
-------

* `set(key, val, [expiry])` - Set key to the value. Optional expiry time in milliseconds. Overrides anything that is already set.

* `get(key)` - Get value for passed in key. Returns null if it doesn't exist.