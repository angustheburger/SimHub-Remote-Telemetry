SimHub Remote Telemetry Bridge

Author: Angus

Version: 1.0

A high-performance, secure networking plugin for SimHub that allows race engineers or teammates to view Dash Studio dashboards remotely without port forwarding or exposing the host's IP address.
🚀 Core Features

    Zero-Config Tunneling: Uses Cloudflare Quick Tunnels to create a secure bridge to your local SimHub web server.

    Auto-Port Discovery: Automatically detects the active SimHub Web Access port by parsing local configuration files.

    Hardened Security: * SHA-256 Checksum Verification: Validates the integrity of the tunneling binary before execution.

        Outbound-Only: No inbound firewall rules or port forwarding required.

    Preflight Diagnostics: Validates that SimHub's web server is active and responding before attempting to open the tunnel.

    One-Click Dependencies: A dedicated "Install" interface to manage external binaries like cloudflared.exe.

🛠 Installation

    Download the latest release DLL.

    Place SimHubRemoteTelemetry.dll into your SimHub installation folder (usually C:\Program Files (x86)\SimHub).

    Restart SimHub and enable the Remote Telemetry plugin in the settings.

    Open the plugin settings and click the "INSTALL CLOUDFLARED" button in the top right to set up the necessary bridge components.

📖 How to Use

    Start SimHub: Ensure "Web Access" is enabled in the SimHub Dash Studio settings.

    Initialize: Open the Remote Telemetry plugin and click START REMOTE SESSION.

    Verify: The plugin will perform a preflight check. Once the link appears, click COPY LINK.

    Share: Send the trycloudflare.com URL to your engineer. They can open this in any browser to view your live telemetry.

    Terminate: Click STOP REMOTE SESSION to immediately kill the tunnel and close all background processes.

🛡 Security Architecture

Unlike traditional remote access, this plugin uses an encrypted outbound tunnel.

    Privacy: Your public IP is never shared.

    Encryption: All data is transmitted over HTTPS.

    Ephemeral: Links are unique to every session and expire immediately upon stopping the service.
