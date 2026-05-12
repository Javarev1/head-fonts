# head-fonts

Displays player skin heads in chat, join/leave, and death messages using a custom font resource pack.

## Setup

1. Drop the jar into your `plugins` folder
2. Start the server — the resource pack is sent to players automatically

## Displaying Heads (API)

```java
BaseComponent[] head = ChatHeadAPI.getInstance().getHead(player);
player.spigot().sendMessage(head);
```

You can also get the head as a string or Adventure component:

```java
String legacy = ChatHeadAPI.getInstance().getHeadAsString(player);
Component component = ChatHeadAPI.getInstance().getHeadAsComponent(uuid, true, ChatHeadAPI.defaultSource);
```

## Config

```yaml
# Show a notification when a new version is available
check-for-updates: true

# Where to fetch player skins: MOJANG, CRAFATAR, MINOTAR, MCHEADS
skin-source: MOJANG

# Automatically send the resource pack to joining players
auto-download-pack: true

# Apply the outer skin layer on heads
enable-skin-overlay: true

# Toggle individual message types
enable-join-messages: true
enable-leave-messages: true
enable-chat-messages: true
enable-death-messages: true

# Seconds to wait before showing the join message (gives the pack time to load)
join-messages-delay-seconds: 3

# How long a player's head is cached before being re-fetched (seconds)
head-cache-entry-lifetime-seconds: 300
```
