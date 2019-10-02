# Gentle mockery

This week we're going to write a basic mocking framework. It's a good way to demystify how they work, and will exercise
things like delayed evaluation, generics.

- Given a trait, return a mock instance of that trait
- Make the mock throw if any of the methods are called
- Given a mock, provide a way to set an expectation on a method to be called with specific parameters
- The mock should not explode if that method is called
- Given a mock, return a value if a specific method is called

If you're feeling enthusiastic then you can add more elaborate features from other mocking frameworks (e.g., verifying
calls, allowing any number of invocations of a method, sequencing of calls).

Bonus points for giving your framework a cute name.
