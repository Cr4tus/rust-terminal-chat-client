# Rust Terminal Chat Client

## What does the app do?
It connects to the server and lets the user send messages while receiving the ones from the other connected users

## Programming Langauges:
- Rust

## Frameworks & Libraries:
There is no need to add external crates to this program

## Implementation:
The client spawns a thread that will send the messages and display the ones received from the server.
The main thread is used to get the user input from the keyboard:
```rust
loop {
    let mut buffer = String::new();

    io::stdin().read_line(&mut buffer)
        .expect("Reading from stdin has failed.");

    let message = buffer.trim().to_string();
    if message == ":quit" || sender.send(message).is_err() {
        break;
    }
}
```