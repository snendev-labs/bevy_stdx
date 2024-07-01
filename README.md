# bevy_stdx

`bevy_stdx` is a collection of tiny crates that are commonly useful when using Bevy.

# Crates

- `bevy_anyhow_alert`: A high-level plugin for error management. Call `my_system.anyhow_alert` when registering systems to adapt any `fn my_system(...) -> anyhow::Result<T>` (or `Result<T, Vec<anyhow::Error>>`) so that the errors are raised to the screen as UI "alert" elements.
- `bevy_assert_plugin`: An extension trait for `App` that checks if a dependency plugin has been attached and provides a default if not.
- `bevy_ui_mod_alerts`: A plugin that handles spawning UI elements when Alert entities are spawned.
- `bevy_mod_try_system`: An extension trait for `IntoSystem<Out = Result<Val, Error>>` for some `Val`, `Error` types. It provides a `fn pipe_err(other_system: IntoSystem<In = Error>)` method to users which is how `bevy_anyhow_alert` is built.
