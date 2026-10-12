**Subnautica Modding**

AI Code of Conduct

# Purpose

AI coding tools have made it much easier to build mods, and the number of AI-generated mods is growing. That is not a problem in itself. The problems are mods that misrepresent how they were made, mods nobody can inspect, and mods that were never properly tested.

This Code of Conduct is a community-written standard for authors who use AI to make mods. It asks for three things: **honesty** about how a mod was made, **accountability** for what it does, and **verifiability**, so anyone can check both. Authors who follow it can display a compliance seal ([Part 2](SEAL.md)).

The Code is split into game-neutral core rules (Part 1), the seal process ([Part 2](SEAL.md)), and short game and stack files that adapt it to a specific game, so it can be extended to other games.

## How to read the rules

**Must** Required for the seal.

**Should** Recommended. Not required, but its absence may be noted in a review.

**Platform** means any site hosting the mod. **AI** means generative AI tools, including coding assistants, image, audio and voice generators, and chat assistants used to write content.

# Part 1 — Core Rules

## 1\. Transparency

**1.1 Tag accurately. (Must)** Apply the platform's AI disclosure tags that fit the mod, and use the most specific tag that applies. If two tags could fit, use the one that discloses more. If the platform has no equivalent tags, disclose using the reference tags defined at the end of this section.

**1.2 Say it in plain words. (Must)** The mod page must state in a sentence or two what AI was used for. Example: "Code written with Claude Code and reviewed by me. Icons drawn by hand."

**1.3 Earn the lighter tag. (Must)** The "AI Assisted" tag is for developer-led work with limited AI involvement. An author using it carries the burden of showing that, and must be able to provide:

(a) development history, such as commit history or project file history, showing human-led design; and

(b) real understanding of the code, shown by explaining how it works if a reviewer or moderator asks.

**1.4 Disclose everywhere. (Must)** The same disclosure applies on every platform where the mod is posted.

**1.5 Leave the trail intact. (Should)** Do not strip AI co-author notes or tool attributions from commit history.

### Disclosure tags (reference standard: Nexus Mods)

Nexus Mods currently offers three AI-related tags, and this Code uses them as its reference standard. Mods following this Code must follow the platform's rules for them. Check the platform for the current names and definitions, as these may change. Platforms that do not yet offer AI disclosure tags are encouraged to adopt equivalents of these three, so that authors and users get the same style of disclosure everywhere.

| **Tag**                  | **Use for**                                                                                                                                                     | **Notes**                                                                                                                               |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| **AI-Generated Content** | AI-generated code, user interface elements, voices, dialogue, translations, music, and in-game AI-generated assets.                                             | Applies to most mods built mainly with coding assistants.                                                                               |
| **AI Media**             | AI promotional art, thumbnails, videos, mod page descriptions, or media outside the in-game content.                                                            | Platform definition. Under this Code, descriptions are author-led and LLM proofreading or formatting does not need this tag (rule 7.3). |
| **AI Assisted**          | Developer-led code, content, or assets with limited AI involvement, including AI texture or audio upscaling and cleaning, and concept art not in the final mod. | Requires evidence of development and real understanding (rule 1.3).                                                                     |

## 2\. Verifiability

**2.1 Publish the source. (Must)** The mod's full source must be in a public repository, linked from the mod page. Open permissions are not required, and you may choose any license.

**2.2 Releases match the repo. (Must)** Each published download must be built from a tagged commit in that repository, so users and reviewers can confirm the download matches the source.

**2.3 Keep real history. (Must)** Work is committed to version control as it is developed. A single commit containing the finished mod does not count as history.

**2.4 State a license. (Should)** A repository with no license is all-rights-reserved by default. Say what others may do with your work.

## 3\. Accountability

**3.1 You own every line. (Must)** The author is responsible for the mod's behavior regardless of who or what wrote the code.

**3.2 Understand what it does. (Must)** The author must understand the mod's behavior, meaning what it changes in the game, what it touches on the user's machine, and what could go wrong, and must be able to explain that in plain language. Fluency in the programming language is not required. Fixing problems with the help of AI tools or other people is fine.

**3.3 Support it or say you won't. (Must)** Respond to bug reports in reasonable time, or clearly mark the mod as unsupported on its page.

## 4\. Testing

**4.1 Test before you publish. (Must)** Test on the actual game versions the mod claims to support. Do not assume that working on Subnautica means working on Below Zero, or the reverse.

**4.2 Report your testing. (Must)** The mod page must include a short testing statement covering the items in the Author Checklist ([COC-CHECKLIST.md](COC-CHECKLIST.md)).

**4.3 No more, no less. (Must)** The mod must do what its page says. Features that are undocumented, left over from debugging or unintended are defects.

**4.4 Cost the user as little as possible. (Must)** In practice:

(a) no noticeable performance loss;

(b) no save-breaking changes without a clear warning. If the mod adds anything that ends up in save files, state whether removing it mid-save is safe;

(c) no log spam; and

(d) clean removal where feasible. If removal is not clean, say so prominently.

## 5\. Security and Safety

Mods are code that runs with the user's full permissions. AI-generated code deserves at least the same scrutiny as any other code a user would install.

**5.1 No hidden network activity. (Must)** The mod must not make network connections unless that is its disclosed purpose, and then only to the endpoints it names.

**5.2 No hidden data collection. (Must)** No telemetry, analytics or data gathering that is not disclosed on the mod page.

**5.3 No obfuscation. (Must)** Source and builds must be readable and reviewable.

**5.4 Stay in your lane. (Must)** Only read or write files the mod owns, such as its own folder, config and save data, plus game files the mod patches as disclosed.

**5.5 Vet dependencies. (Must)** Declare every dependency. Verify that every package an AI tool suggests actually exists and is the legitimate one. Assistants sometimes invent package names, and attackers register those names.

**5.6 Run a capability check. (Must)** Before publishing, check the code for the high-risk capabilities listed in the capability table for your game's stack (for C# and Unity games, [stacks/csharp-unity.md](stacks/csharp-unity.md)): network access, launching programs, file access outside the mod's folders, loading code at runtime, and native interop. You do not need to read the language to do this. Search the repository for the listed terms, or ask your AI tool to list every place the code does any of these and explain each one. Every hit must be removed, or kept and disclosed on the mod page with its purpose.

**5.7 Get a second opinion. (Should)** Have a separate AI session, with no memory of the first, review the code with a security-focused prompt, and keep the result in the repository. Where practical, automate that search so it runs on every commit.

## 6\. Provenance and Licensing

**6.1 Act in good faith on originality. (Must)** Checking a mod against every other mod is impossible, so the standard is good faith, not proof. Do not knowingly copy another mod's code, and do not prompt your AI tool to reproduce a specific existing mod. If you know code came from elsewhere, or the output carries a license header or attribution, follow that license and credit the source.

**6.2 Fix it when told. (Must)** If someone credibly shows that your mod copies theirs, respond promptly and credit, fix, or remove the code.

**6.3 Use the filters you have. (Should)** If your AI tool offers a setting that blocks or flags output matching public code, turn it on.

**6.4 Don't redistribute game assets. (Must)** Do not ship the game's own assets, code or audio in your download unless the publisher's modding terms allow it.

**6.5 No cloning without consent. (Must)** Do not clone or imitate a real person's voice or likeness, including voice actors from the game, without their permission.

**6.6 Credit upstream. (Should)** Credit the frameworks and mods your work builds on.

## 7\. Media

**7.1 Real screenshots. (Must)** Mod thumbnails and screenshots must be rooted in actual gameplay with the mod installed. Routine edits (cropping, color, cleanup) may be AI-assisted but should be largely user-driven.

**7.2 Show real behavior. (Must)** Images and videos must show what the mod actually does, not mockups of it.

**7.3 Author-led descriptions. (Must)** The mod page description must be written by the author. Proofreading and formatting help from an LLM is permitted and does not require the "AI Media" tag under this Code. AI-generated promotional art, thumbnails and videos still fall under "AI Media." Authors following this Code should rarely need the tag. Platform rules still apply if a platform's moderators read the tag differently.

**7.4 Descriptions must be accurate. (Must)** Whatever help is used, the author must check that every claim on the page is true.

## 8\. Respect

Modding communities run on trust between authors and users. The rules below protect it.

Picture a potluck. You spend hours making a pie from scratch. Another guest arrives with a frozen pie, heated up on the way, and tells everyone it is homemade. The frozen pie is not the problem. The lie is. Everyone deserves to know what they are being served and to decide for themselves.

**8.1 Don't misrepresent. (Must)** Never present AI-generated work as hand-made, or the reverse.

**8.2 Keep it civil. (Must)** Do not disparage authors for using AI or for not using it. Disagreements about AI are legitimate. Hostility is not.

**8.3 Let users choose. (Must)** Accurate tagging lets users filter in or out the mods they want. Do not make that harder.

**8.4 Handle disputes in good faith. (Must)** If a tag or claim is challenged, respond with evidence and accept the outcome of any review.
