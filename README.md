# Dbus Binding

Sample binding for interfacing DBUS.

## Dependencies

This binding uses afb-binding, libjson-c and libsystemd

## Compiling

Example:

```
mkdir build
cd build
cmake ..
make
```

It produces the binding `dbus-binding.so`.

## API

The binding v1 offers 5 verbs: `version`, `call`, `signal`, `subscribe`, `unsubscribe`.

### version

Takes no arguments.

Returns the STRINGZ representing is version.

### call

### signal

### subscribe

### unsubscribe

## Examples


```
dbus version

dbus call {"bus":"user", "destination":"org.freedesktop.DBus", "path":"/org/freedesktop/DBus", "interface": "org.freedesktop.DBus", "member": "RequestName", "signature": "su", "data": [ "bzh.iot.dbus.binding", 0 ] }

dbus call {"bus":"user", "destination":"org.freedesktop.DBus", "path":"/org/freedesktop/DBus", "interface": "org.freedesktop.DBus", "member": "ListNames", "signature": "", "data": null }

dbus call {"bus":"system", "destination":"org.freedesktop.DBus", "path":"/org/freedesktop/DBus", "interface": "org.freedesktop.DBus", "member": "ListNames", "signature": "", "data": null }

dbus subscribe {"bus": "system", "match": "type=signal,sender=org.freedesktop.NetworkManager", "event":"nme"}
```


