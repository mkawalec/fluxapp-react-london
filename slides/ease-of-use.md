##  Ease of use

- Concerns are separated between action creators and stores, no soup-like
  structures for stores
- Context is available *implicitly* in stores, actions and components in
  with the same API (in components achieved with higher order cpts)
- Dispatcher is modified, so that it's possible to fire an action from
  the dispatch phase
- We've created an instantly pluggable context aware fetcher
  (transparently supports cookies on server side requests) and router
