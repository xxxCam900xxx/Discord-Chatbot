![](./_images/Combinationmark%20White%20Border.svg)

---

### Wie erstellt man seinen eigenen ersten Discord Bot mit C# .NET
In dieser Anleitung erfahrst du alles was du Wissen musst, um einen eigenen Discord Bot zu bauen und wirst Schritt für Schritt durchgeführt.

- [Step 01 - Einrichtung deines Bots](./Guide/Step01/README.md)
- [Step 02 - Solution und erste Verbindung](/Guide/Step02/README.md)
- [Step 03 - TO BE CONTINUE]()

---

# Notizen

### Type Task is the Key
> Ereignisse in Discord.Net werden ähnlich wie in der Standardkonvention verwendet, mit der Ausnahme, dass jedes Ereignis vom Typ „**Task“** sein muss und dass die Parameter des Ereignisses anstelle der Verwendung von „Event Args“ direkt an den Handler übergeben werden.

> Dadurch können Ereignisse direkt in einem asynchronen Kontext behandelt werden, anstatt sich darauf zu verlassen **async void.**

### Unterschiede bei Discord

> **Discord.Net.Corebietet** eine Reihe von Schnittstellen, die die API von Discord modellieren. Diese Schnittstellen sind in allen Implementierungen von Discord.Net konsistent, und wenn Sie eine implementierungsunabhängige Bibliothek oder ein Add-on schreiben, können Sie sich auf die Kernschnittstellen verlassen, um sicherzustellen, dass Ihr Add-on auf allen Plattformen läuft.

> **Discord.Net.Reststellt** eine Reihe konkreter Klassen bereit, die ausschließlich mit dem REST-Teil der API von Discord verwendet werden dürfen. Entitäten in dieser Implementierung haben das Präfix Rest(z. B. RestChannel).

> **Discord.Net.WebSocketbietet** eine Reihe konkreter Klassen, die hauptsächlich mit Discords WebSocket-API oder Entitäten verwendet werden, die im Cache gespeichert sind. Beim Entwickeln von Bots verwenden Sie diese Implementierung. Alle Entitäten haben das Präfix Socket(z. B. SocketChannel).

### Structure
> It is important to know that the recommended design pattern of bots should be to separate...
>
> 1. ***the program*** (initialization and command handler)
> 2. ***the modules*** (handle commands)
> 3. ***the services*** (persistent storage, pure functions, data manipulation)

### GET DATA
```C#
public static SocketChannel GetChannel(ulong channelId)
{
    var channel = _client.GetChannel(channelId) as SocketTextChannel;
    Console.WriteLine(channel);
    return channel;
}

public static SocketGuildUser GetGuildOwner(SocketChannel channel)
{
    var guild = (channel as SocketGuildChannel)?.Guild;
    return guild?.Owner;
}
```