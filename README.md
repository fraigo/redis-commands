# redis-commands
A list of useful Redis commands 


## SET : Store values (with optional expiration)

`SET keyname value [expiration EX seconds|PX milliseconds] [NX|XX]`

Store a string

`SET app:name MyApp`

Store a number

`SET user:sessions 1`

With 60 seconds of expiration

`SET app:sessionid RdDdreDD324Dd4AAdw EX 600`

## GET : Retrieve stored values

`GET keyname`

Get an existent value

`GET app:name`

## INCR : Increment numeric value

`INCR keyname increment`

Counter example (starts at 1 if key not exists)

`INCR counter`

## DEL : Delete a stored value

`DEL keyname`

Delete the counter

`DEL counter`

## EXPIRE : Set expiration time for a stored value

`EXPIRE keyname ttl`

Example (overwrite original TTL during `SET`)

`EXPIRE app:sessionid 30`

## TTL : Check how long a key will exist 

`TTL keyname`

Example

`TTL app:sessionid` 

* When the value is expired, TTL returns -2
* When the value never expires, TTL return -1


