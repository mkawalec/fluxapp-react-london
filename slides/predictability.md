##  Predictability

- State in stores in one well defined place (`.state`)
- State is immutable (!)
- Actions have `:failed`, `:before` and `:after` modifiers
- Actions are executed sequentially to limit effects of concurrency
- Components can only listen to __special__ actions, so `:failed`,
  `:before` and `:after`
