# Step 02 - Making Your First Bot Solution

Dies ist eine Schritt-für-Schritt Anleitung um einen eigenen Discord Bot mit C# zu bauen. **Wichtiger Hinweis:** Es werden nur die Grundlagen erklärt um einen funktionierenden Bot zu bauen.

---

### Schritt 01
Gehe zu Visual Studio und erstelle eine **"Console App"**.
**Wichtig:** Um diese Lösung zu erstellen benötigt man min. **.NET 5.0**
Erstelle nun die Solution.

---

### Schritt 02
Klicken Sie mit der rechten Maustaste auf die Lösung und suchen Sie nach **"Manage NuGet Packages..."**.

![](./_images/Step01_ManageNuget.png)

Dann klicke auf Browse und suche nach Discord.net.

![](./_images/Step02_InstallDiscordNet.png)

Anschliessend Discord.net installieren.

---

### Schritt 03 - Die erste Connection
Das Discord.net Paket bietet uns viele neue Dinge, die wir nutzen können. Für weitere Informationen [**Klick hier**](https://docs.discordnet.dev/api/index.html).

Auf der **Program.cs** werden folgende **Usings** benötigt:
```C#
using Discord;
using Discord.WebSocket;

namespace myBot 
{
    public class Program
    {
        public static Main() {
            Console.WriteLine("Hello World!");
        }
    }
}
```

Um eine Verbindung zum Discord Bot herzustellen, benötigen wir einen Client.
Der **DiscordSocketCLient** hilft uns dabei. Wir müssen nun auch unseren Main Asynchron bauen. 

**Hinweis:** Der Discord Client arbeitet mit **Type Task** deswegen werden auch die nachkommenden **Methods** als Task angegeben.

```C#
public class Program 
{

    private static DiscordSocketClient _client;

    public static async Task Main() {
        _client = new DiscordSocketClient();
    }

}
```

TO BE CONTINUE