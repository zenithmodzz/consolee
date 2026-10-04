# consolee

Private console backend + console source for HamoodMenu.

## Layout

- `Console/Console.cs` — console source (copy of `Classes/Menu/Console.cs`)
- `Console/ServerData.cs` — server data loader (copy of `Classes/Menu/ServerData.cs`)
- `Console/MenuTier.cs` — owner/user tier gate (copy of `Classes/Menu/MenuTier.cs`)
- `ServerData/serverdata.json` — live backend file the menu reads

## Setup

1. Replace every `YOUR_ID_HERE` in `ServerData/serverdata.json` with your
   PlayFab `UserId`.
2. Commit + push. Your raw link becomes:

   `https://raw.githubusercontent.com/zenithmodzz/consolee/refs/heads/main/ServerData/serverdata.json`

3. In `HamoodMenu`, point `ServerDataEndpoint` at that raw link:

   ```cs
   public static readonly string ServerDataEndpoint = "https://raw.githubusercontent.com/zenithmodzz/consolee/refs/heads/main/ServerData/serverdata.json";
   ```

4. Put the same ID in `LocalAdmins` (`ServerData.cs`) and `TrustedOwnerIDs`
   (`Console.cs`) so only that player ID can hold console.
