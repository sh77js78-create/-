# 활성특별시

**A dedicated desktop launcher for 활성특별시**  
*An independent Minecraft: Java Edition roleplay server project*

> **NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.**

## Overview

**활성특별시** is an independent desktop application being developed for **활성특별시y** a Korean-language Minecraft: Java Edition roleplay community. It aims to give players one place to sign in with their own Microsoft account, install the required game environment, keep approved server content up to date, and join the community server.

The launcher does **not** provide a copy of Minecraft or grant game licenses. Players must own a valid license for Minecraft: Java Edition and authenticate before gameplay or server connection.

## Features

The current development project includes:

- **Custom desktop interface:** React and TypeScript frontend in a Tauri v2 application.
- **Microsoft sign-in integration:** OAuth 2.0 Authorization Code Flow with PKCE, using a system-browser sign-in and local loopback redirect.
- **Minecraft authentication integration:** Xbox Live, XSTS, and Minecraft Services token exchange, with ownership/profile verification as a required step before gameplay.
- **Managed installation:** Minecraft: Java Edition **1.21.7**, **Fabric**, and a **Java 21** runtime check.
- **Content management:** Manifest-driven installation and updates for server-required mods and resource packs.
- **Quick Play:** Launching Minecraft with a preconfigured multiplayer server destination after required checks succeed.
- **Diagnostics:** Game process monitoring and log collection for troubleshooting.

## 활성특별시 and license protection

활성특별시 is designed to use the following authentication sequence:

1. The player signs in through Microsoft's official authorization page using OAuth 2.0 with PKCE.
2. The launcher exchanges the authorized credentials through Xbox Live and XSTS.
3. The launcher requests a Minecraft Services access token.
4. The launcher checks the player's Minecraft entitlement and profile.
5. **Only after successful authentication and ownership verification** may the launcher start the game and connect to the server.

The launcher is **not intended to support cracked accounts, offline-mode authentication bypasses, shared credentials, or any mechanism that circumvents license or security checks**. Microsoft passwords are not collected through a custom login form. The project includes OS-backed secure token storage.

**Current limitation:** End-to-end sign-in and game-launch verification is pending review of the application's own Microsoft Entra Application (Client) ID. The Minecraft Services token exchange currently returns `HTTP 403: Invalid app registration`. The application will not treat that failure as successful authentication or bypass the ownership checks.

## Project status

**Status: Development / pre-release — not yet publicly distributed.**

| Area | Status |
| --- | --- |
| Desktop UI and Tauri integration | Implemented; local development build tested |
| macOS application and DMG bundle | Build generated |
| Windows installer | CI build configuration prepared; Windows build and device testing pending |
| Microsoft OAuth / Minecraft Services | Integration implemented; Minecraft App ID approval pending |
| Full authenticated launch and server join | End-to-end verification pending |
| Production server endpoint and content manifest | Configuration pending |

The project uses **Tauri v2, Rust, React, TypeScript, and Vite**. This public repository may contain project information only; the application source code and production infrastructure are not necessarily published here.

## Minecraft App ID review

We are requesting authorization for **ActiveLauncher's own Microsoft Entra application ID** to access the Minecraft Services authentication APIs. This is necessary to authenticate players, verify their ownership of Minecraft: Java Edition, obtain the corresponding player profile, and enable legitimate game launch and server access.

We do not use another launcher's application ID and do not attempt to bypass Minecraft authentication or licensing requirements.

## Legal and brand notice

ActiveLauncher and Active Special City are independent community projects. They are **not affiliated with, endorsed by, sponsored by, or officially connected to Mojang Studios or Microsoft**.

Minecraft and related marks belong to their respective owners. The launcher is intended to comply with the [Minecraft EULA](https://www.minecraft.net/en-us/eula) and [Minecraft Usage Guidelines](https://www.minecraft.net/en-us/usage-guidelines). Community content must be distributed only with appropriate permissions.

## Contact

**Project operator contact:** `human.190234@gmail.com`  
*Replace this placeholder with a working contact email address before making this README public. The same address should be supplied in the Minecraft App ID review form and kept consistent with your Azure registration contact details.*
