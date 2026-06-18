# ft_irc

A lightweight IRC (Internet Relay Chat) server implementation written in C++98.

## Description

ft_irc is a fully functional IRC server that allows multiple clients to connect, communicate, and manage channels. It implements core IRC protocol features including user authentication, channel management, messaging, and operator commands.

## Features

- **Client Management**: Handle multiple concurrent client connections
- **Channel Operations**: Create, join, and manage channels
- **User Authentication**: Password-protected server access
- **Messaging**: Private messages and channel communication
- **Operator Commands**: Channel operators can manage permissions and modes
- **Mode System**: Flexible mode handling for users and channels

## Requirements

- C++98 compatible compiler (g++, clang++)
- POSIX-compliant system (Linux, macOS, etc.)
- Make build tool

## Compilation

```bash
make        # Build the executable
make clean  # Remove object files
make fclean # Remove all generated files
make re     # Rebuild from scratch
```

## Usage

```bash
./ircserv <port> <password>
```

### Arguments

- `<port>`: Port number (1-65535) on which the server will listen
- `<password>`: Server connection password

### Example

```bash
./ircserv 6667 mypassword
```

Then connect with an IRC client:

```bash
irc-client localhost 6667
```

## Project Structure

```
include/           # Header files
  ├── Client.hpp
  ├── Server.hpp
  ├── Channel.hpp
  ├── Replies.hpp
  └── irc.hpp

src/               # Source files
  ├── main.cpp     # Entry point
  ├── server/      # Server socket management
  ├── client/      # Client handling
  ├── channel/     # Channel operations
  └── command/     # IRC command implementations
```

## Implementation Notes

- Written in C++98 standard for maximum compatibility
- Uses socket programming for network communication
- Implements RFC 1459 IRC protocol
- Signal handlers for graceful shutdown
- Non-blocking I/O for concurrent client handling
