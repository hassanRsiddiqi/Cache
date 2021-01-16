# Cache

**Cache Module in OTP Elixir**
This is a practice exercise at the end of Chapter 4 of book `The Little Elixir & OTP Guidebook`

### Exercise

```
Write a GenServer that can store any valid Elixir term, given a key. Here are a few
operations to get you started:

- Cache.write(:stooges, ["Larry", "Curly", "Moe"])
- Cache.read(:stooges)
- Cache.delete(:stooges)
- Cache.clear
- Cache.exist?(:stooges)

Structure your program similar to how you did in this chapter. In particular, pay attention to which of these operations should be handle_calls or handle_cast.
```

## Usage

Start Generic Server
```
Cache.start
# {:ok, #PID<0.155.0>}
```

write countries & cities lists in state

```
Cache.write :cities, ["Multan", "Lahore", "Karachi"]
# :ok

Cache.write :countries, ["Pakistan", "Iran", "Turkey", "China"]
# :ok
```

fetch cities from state
```
Cache.read :cities
# {:ok, ["Multan", "Lahore", "Karachi"]}
```

delete cities from state
```
Cache.delete :cities
# :ok
```
check is country key exists?
```
Cache.exists :countries 
# true
```
clear all states
```
Cache.clear 
# :ok
```
now, after clearing state county key is reset.
```
 Cache.exists :countries
 # false
 ```
