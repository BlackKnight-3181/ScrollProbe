# ScrollProbe

Smooth scrolling for mice with a physical scroll wheel on macOS.

ScrollProbe runs in the background and reconstructs scroll events from conventional mice. It automatically recognizes sequences produced by detented and free-spinning wheels. Scrolling behavior may vary depending on the mouse and application.

This repository provides information about the application and installers in **Releases**. The application's source code is not published in this repository.

## Requirements

- macOS 13 or later, on an Apple Silicon or Intel Mac.
- Administrator authorization to install the shared system components.
- Input Monitoring and Accessibility permissions granted to the service by each user who wants to use it.

## Installation

1. Download the DMG from **Releases** and open it.
2. Run **Instalar ScrollProbe.pkg** (Install ScrollProbe) and follow the macOS Installer.
3. In **System Settings → Privacy & Security**, allow ScrollProbe Service under **Input Monitoring** and **Accessibility**.
4. If you need to locate the application when granting access, use:

   `/Library/Application Support/ScrollProbe/ScrollProbeService.app`

5. Open Terminal and start the service:

   ```sh
   "/Library/Application Support/ScrollProbe/scrollprobectl" start
   ```

If an older installation for an individual user is running, stop it before installing the shared version to avoid two services processing the same scroll events:

```sh
"$HOME/Library/Application Support/ScrollProbe/scrollprobectl" stop
```

The files and installer license inside the current 0.6.7 DMG are in Portuguese. English license terms are available in this repository's **LICENSE** file.

## Controls

Stop:

```sh
"/Library/Application Support/ScrollProbe/scrollprobectl" stop
```

Start:

```sh
"/Library/Application Support/ScrollProbe/scrollprobectl" start
```

Check the service status and permissions:

```sh
"/Library/Application Support/ScrollProbe/scrollprobectl" status
"/Library/Application Support/ScrollProbe/scrollprobectl" doctor
```

The service remembers each user's last choice after a restart or login. Installation is shared across the Mac; permissions and the enabled or disabled state are individual to each user.

## Uninstallation

Run **Desinstalar ScrollProbe.pkg** (Uninstall ScrollProbe), included in the DMG. It removes the shared components. Each user's settings, logs, and sessions remain in `~/Library/Application Support/ScrollProbe`.

## Reporting issues

Open an **Issue** with the application version, macOS version, mouse model, and a description of the behavior. Review any logs or screenshots before attaching them.

## Creator and license

Created and directed by **BlackKnight-3181**. The initial implementation was produced with generative artificial intelligence assistance under his direction.

Copyright © 2026 BlackKnight-3181. Distribution 0.6.7 is available free of charge for personal or internal use under the terms in **LICENSE**. Modification and redistribution require prior written authorization, subject to mandatory legal exceptions. To recommend the application, share the official download page. License grants for earlier versions remain in effect.
