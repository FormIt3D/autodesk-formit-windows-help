# Prerequisites and Installation

## Download and Installation

* Download the latest [FormIt for Windows](https://formit.autodesk.com/page/download).
* Use your Autodesk account to sign in, or [create a free Autodesk account here](https://accounts.autodesk.com).
* The FormIt Add-In for Revit is included with Revit 2017 and newer. You can also download and manually install the add-in [from our website](https://formit.autodesk.com/page/formit-revit).

## Recommended System Configuration

| Requirement                    | Details                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Operating System**           | <p>Microsoft® Windows® 8, 8.1, 10, or 11. </p><p><em></em></p><p><em>Note: Parallels Desktop is not officially supported due to degraded performance and graphics issues in OpenGL drivers.</em></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **CPU**                        | <p>Intel® Pentium®, Xeon®, or i-Series processor or AMD® equivalent with SSE2 technology. </p><p></p><p>Highest affordable CPU speed rating recommended.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Memory**                     | 4 GB RAM minimum, 8GB or higher recommended.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Video Card (GPU)**           | <p>A discrete NVIDIA or AMD video card that supports OpenGL 2.0 is required. OpenGL 4.2 support is strongly recommended. </p><p></p><p>For systems with switchable video cards, follow manufacturer instructions to ensure FormIt always uses the dedicated GPU for best performance. See instructions for <a href="https://www.amd.com/en/support/kb/faq/dh-017">AMD </a>and <a href="http://nvidia.custhelp.com/app/answers/detail/a_id/2615/kw/manage%203d%20settings/related/1">NVIDIA</a>. </p><p></p><p>For best performance and reliability, ensure your video card drivers are up-to-date from the manufacturer's website or Windows Update. </p><p></p><p>FormIt will show a message at startup if it's unable to use your video card due to outdated drivers or other issues. If FormIt fails to start after updating drivers, please <a href="https://forums.autodesk.com/t5/formit-forum/bd-p/142">reach out on the forums</a>.</p> |
| **Disk Space**                 | 1 GB free disk space.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Connectivity and Licensing** | <p>An internet connection is required when launching FormIt for the first time, in order to sign in to your Autodesk account. </p><p></p><p>An internet connection is also required to load plugins when launching FormIt. If an internet connection is not detected at startup, the application will launch without plugins.</p><p></p><p>An Autodesk account with a FormIt Pro cloud subscription is required to run FormIt Pro on Windows. <em></em> FormIt Pro is available as part of the <a href="https://www.autodesk.com/collections/architecture-engineering-construction/overview"><strong>Autodesk AEC Collection</strong></a>.</p>                                                                                                                                                                                                                                                                                                  |

## Offline Access

When you first run FormIt for Windows, you need to be connected to the internet so your license can be validated. After the first sign-in, you can use the app offline for 30 days. After this, you’ll need to go online to validate your license again.

When using FormIt for Windows offline, some functionality will be limited:

* The Set Location tool will not function, as it requires an internet connection to retrieve satellite and terrain data from Bing Maps.&#x20;
  * However, any existing satellite and terrain already in the model from a previous online session will remain.&#x20;
* Any plugins, including the Plugin Manager, will not load, as they get the latest code from GitHub on every application launch.&#x20;
  * Workaround: If you load up all your plugins while online and keep the FormIt session running when going offline, the plugins that were previously loaded will remain and function normally.
* Sample materials will not load, since they come from a cloud-hosted server.&#x20;
  * Workaround: Navigate into the sample materials category folders while connected to the internet. The folders are downloaded and stored on your machine and can be accessed later when offline.&#x20;
* You will not be able to save to or open from Autodesk Docs, including from within the Content Library.

## Recommended Windows DPI Settings

FormIt for Windows works best when the display screen is set to 125% or less DPI scaling in Windows.

You can change this in Windows 10 by doing the following:

* Search "Display" in the Start Menu, and choose "Change Display Settings"&#x20;
* Select the rectangle representing the monitor you'll be using with FormIt
* Under "Scale and Layout" section, open the "Size of text, apps, and other items" dropdown and select a value of 125% or less

## Troubleshooting

### Windows 10 system error

If you're running FormIt on Windows 10 version 1909, you may see this error message:

![FormIt.exe System Error on Windows 10](<../.gitbook/assets/windows 10 error message.png>)

This is due to a known issue with certain versions of Windows 10 Pro N. To avoid this error, download the Media Feature Pack for your version of Windows 10 here: [Media Feature Pack List for Windows N Editions](https://support.microsoft.com/en-us/topic/media-feature-pack-list-for-windows-n-editions-c1c6fffa-d052-8338-7a79-a4bb980a700a).

### Unable to sign in

When attempting to sign in to your account in FormIt, the login dialog may hang, preventing you from proceeding. If this happens, you may need to unblock \*.autodesk.com in your network firewall. Contact your IT department for support.
