# SecuriCore Library Documentation

Welcome to the SecuriCore library documentation! This guide will help you understand how to use the SecuriCore library to enhance the security of your applications.

## Table of Contents

- [Installation](#installation)
- [Initialization](#initialization)
- [Methods](#methods)
  - [AntiInject](#antiinject)
  - [AntiDebug](#antidebug)
  - [AntiDump](#antidump)
  - [GetHardwareID](#gethardwareid)
  - [DetectPrograms](#detectprograms)
  - [DetectVPN](#detectvpn)
  - [DetectVNC](#detectvnc)
  - [DetectRDP](#detectrdp)
  - [DetectVM](#detectvm)
  - [ControlMonitor](#controlmonitor)
  - [BlockMouseAndKeyboard](#blockmouseandkeyboard)
  - [CheckInternet](#checkinternet)
  - [CheckNetworkSecure](#checknetworksecure)
  - [InitializeBluescreen](#initializebluescreen)
  - [InitializeDisk](#initializedisk)

## Installation

To install SecuriCore, add the necessary references to your project.

## Initialization

To use the SecuriCore library, you must first initialize it with your User ID and API Key:

```csharp
using SecuriCore;

var securiCore = new SecuriCore("your_user_id", "your_api_key");
```

Optionally, you can set a Discord webhook for logging purposes:

```csharp
securiCore.SetDiscordWebhook("your_discord_webhook_url");
```

## Methods

### AntiInject

Detects and prevents malicious programs from injecting code into your application.

**Usage:**

```csharp
securiCore.AntiInject(showError: true);
```

**Parameters:**
- `showError` (bool): If `true`, a message box will display an error message if the method fails.

**Example:**

```csharp
try
{
    securiCore.AntiInject(showError: true);
}
catch (Exception ex)
{
    Console.WriteLine("AntiInject failed: " + ex.Message);
}
```

### AntiDebug

Prevents managed and unmanaged debuggers from debugging your application.

**Usage:**

```csharp
bool isDebuggerDetected = securiCore.AntiDebug(defaultAction: true);
```

**Parameters:**
- `defaultAction` (bool): If `true`, the process will be killed when a debugger is detected.

**Returns:**
- `bool`: `true` if a debugger is detected, otherwise `false`.

**Example:**

```csharp
bool isDebuggerDetected = securiCore.AntiDebug(defaultAction: true);
if (isDebuggerDetected)
{
    Console.WriteLine("Debugger detected and process terminated.");
}
else
{
    Console.WriteLine("No debugger detected.");
}
```

### AntiDump

Prevents memory dumping by malicious file dumpers.

**Usage:**

```csharp
securiCore.AntiDump();
```

**Example:**

```csharp
try
{
    securiCore.AntiDump();
}
catch (Exception ex)
{
    Console.WriteLine("AntiDump failed: " + ex.Message);
}
```

### GetHardwareID

Retrieves the unique hardware identifier for the system.

**Usage:**

```csharp
string hardwareId = securiCore.GetHardwareID();
```

**Returns:**
- `string`: Unique hardware identifier.

**Example:**

```csharp
string hardwareId = securiCore.GetHardwareID();
Console.WriteLine("Hardware ID: " + hardwareId);
```

### DetectPrograms

Detects any malicious programs running on the machine.

**Usage:**

```csharp
bool areMaliciousProgramsDetected = securiCore.DetectPrograms(defaultAction: true);
```

**Parameters:**
- `defaultAction` (bool): If `true`, the process will be killed when a malicious program is detected.

**Returns:**
- `bool`: `true` if any malicious program is detected, otherwise `false`.

**Example:**

```csharp
bool areMaliciousProgramsDetected = securiCore.DetectPrograms(defaultAction: true);
if (areMaliciousProgramsDetected)
{
    Console.WriteLine("Malicious programs detected and process terminated.");
}
else
{
    Console.WriteLine("No malicious programs detected.");
}
```

### DetectVPN

Detects if the current connection is using a VPN, Proxy, or is a Hosting.

**Usage:**

```csharp
bool isUsingVPN = securiCore.DetectVPN();
```

**Returns:**
- `bool`: `true` if a VPN, Proxy, or Hosting is detected, otherwise `false`.

**Example:**

```csharp
bool isUsingVPN = securiCore.DetectVPN();
if (isUsingVPN)
{
    Console.WriteLine("VPN/Proxy/Hosting detected.");
}
else
{
    Console.WriteLine("No VPN/Proxy/Hosting detected.");
}
```

### DetectVNC

Detects if the current machine is connected to a Virtual Network.

**Usage:**

```csharp
bool isUsingVNC = securiCore.DetectVNC();
```

**Returns:**
- `bool`: `true` if connected to a Virtual Network, otherwise `false`.

**Example:**

```csharp
bool isUsingVNC = securiCore.DetectVNC();
if (isUsingVNC)
{
    Console.WriteLine("VNC detected.");
}
else
{
    Console.WriteLine("No VNC detected.");
}
```

### DetectRDP

Detects if the current machine is connected to a Remote Desktop.

**Usage:**

```csharp
bool isUsingRDP = securiCore.DetectRDP();
```

**Returns:**
- `bool`: `true` if connected to a Remote Desktop, otherwise `false`.

**Example:**

```csharp
bool isUsingRDP = securiCore.DetectRDP();
if (isUsingRDP)
{
    Console.WriteLine("RDP detected.");
}
else
{
    Console.WriteLine("No RDP detected.");
}
```

### DetectVM

Detects if the current machine is a virtual machine.

**Usage:**

```csharp
bool isUsingVM = securiCore.DetectVM();
```

**Returns:**
- `bool`: `true` if the machine is a virtual machine, otherwise `false`.

**Example:**

```csharp
bool isUsingVM = securiCore.DetectVM();
if (isUsingVM)
{
    Console.WriteLine("Virtual Machine detected.");
}
else
{
    Console.WriteLine("No Virtual Machine detected.");
}
```

### ControlMonitor

Controls the power state of the monitor.

**Usage:**

```csharp
securiCore.ControlMonitor(value: true); // true to turn on, false to turn off
```

**Parameters:**
- `value` (bool): `true` to turn the monitor on, `false` to turn it off.

**Example:**

```csharp
securiCore.ControlMonitor(value: false); // Turns off the monitor
```

### BlockMouseAndKeyboard

Controls the mouse and keyboard inputs.

**Usage:**

```csharp
securiCore.BlockMouseAndKeyboard(value: true); // true to enable, false to block
```

**Parameters:**
- `value` (bool): `true` to enable mouse and keyboard inputs, `false` to block them.

**Example:**

```csharp
securiCore.BlockMouseAndKeyboard(value: false); // Blocks mouse and keyboard inputs
```

### CheckInternet

Checks if the current machine is connected to the internet.

**Usage:**

```csharp
bool isConnectedToInternet = securiCore.CheckInternet();
```

**Returns:**
- `bool`: `true` if the machine is connected to the internet, otherwise `false`.

**Example:**

```csharp
bool isConnectedToInternet = securiCore.CheckInternet();
if (isConnectedToInternet)
{
    Console.WriteLine("Internet connection detected.");
}
else
{
    Console.WriteLine("No internet connection detected.");
}
```

### CheckNetworkSecure

Checks if the current machine/network is safe for the program to use.

**Usage:**

```csharp
bool isNetworkSecure = securiCore.CheckNetworkSecure();
```

**Returns:**
- `bool`: `true` if the network is secure, otherwise `false`.

**Example:**

```csharp
bool isNetworkSecure = securiCore.CheckNetworkSecure();
if (isNetworkSecure)
{
    Console.WriteLine("Network is secure.");
}
else
{
    Console.WriteLine("Network is not secure.");
}
```

### InitializeBluescreen

Triggers a bluescreen on the machine (requires administrative privileges).
Note: Any usage of this in any real system is prohibited and not recommended. Please have proper permissions to do so.

**Usage:**

```csharp
securiCore.InitializeBluescreen();
```

**Example:**

```csharp
try
{
    securiCore.InitializeBluescreen();
}
catch (Exception ex)
{
    Console.WriteLine("Failed to initialize bluescreen: " + ex.Message);
}
```

### InitializeDisk

Overwrites the MBR, essentially breaking the system OS (requires administrative privileges).

Note: Any usage of this in any real system is prohibited and not recommended. Please have proper permissions to do so.

**Usage:**

```csharp
securiCore.InitializeDisk();
```

**Example:**

```csharp
try
{
    securiCore.InitializeDisk();
}
catch (Exception ex)
{
    Console.WriteLine("Failed to initialize disk: " + ex.Message);
}
```

---
