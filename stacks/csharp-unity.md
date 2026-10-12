# Stack: C# / Unity

For games modded in C# on Unity, such as Subnautica. Games using another language or engine need their own stack file with an equivalent table.

## Capability check (rule 5.6)

Search the repository for these terms, or ask your AI tool to list every use of them and explain each one. A hit is not proof of a problem. It is a prompt to explain, remove, or disclose. The list is a starting point, not exhaustive.

| **Capability**          | **Search the code for**                                      | **Why it matters**                                                |
| ----------------------- | ------------------------------------------------------------ | ----------------------------------------------------------------- |
| Network access          | System.Net, HttpClient, WebClient, Socket, UnityWebRequest   | Data leaving the machine, or code arriving                        |
| Launching programs      | Process.Start, System.Diagnostics, cmd, powershell           | Can run anything on the machine                                   |
| File access             | System.IO, File., Directory.                                 | Expect hits. Check paths stay in the mod, config and save folders |
| Loading code at runtime | Assembly.Load, LoadFrom, Reflection.Emit, CSharpCodeProvider | Code that isn't in the repo can run                               |
| Native interop          | DllImport, Marshal                                           | Bypasses the game's managed environment                           |
| System information      | Registry, GetEnvironmentVariable, GetFolderPath              | Reads data unrelated to the game                                  |
| Hidden payloads         | FromBase64String, long encoded strings                       | Common way to conceal code                                        |
