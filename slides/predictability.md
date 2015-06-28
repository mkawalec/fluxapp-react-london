##  Predictability

- State in stores always in the same place (`.state`)
- State is immutable (!)
- Actions have `:failed` modifiers (and `before`/`after` if async)
- Actions are executed sequentially to limit effects of concurrency
- Components can only listen to __special__ actions, so `:failed`,
  `:before` and `:after`
