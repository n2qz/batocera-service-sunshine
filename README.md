# batocera-service-sunshine
Install sunshine server into Batocera as a user service

## What is it?

[Sunshine](https://github.com/LizardByte/Sunshine) is a self-hosted
game stream host for
[Moonlight](https://github.com/moonlight-stream/moonlight-qt). Offering
low latency, cloud gaming server capabilities with support for AMD,
Intel, and Nvidia GPUs for hardware encoding.

This repo contains a user service script for
[Batocera.linux](https://github.com/batocera-linux/batocera.linux)
which will install and run the AppImage version of Sunshine on the
x86_64 PC version of Batocera.  This adds remote game streaming to
Batocera, allowing you to play your entire collection of retrogames on
any computer or device capable of running a Moonlight streaming
client.

## Why?

There are already several Batocera installers for Sunshine.  I'm not a
fan of any of them, because:

- I don't like piping unaudited scripts directly to bash.
- I don't like running scripts that seem designed to obfuscate what
  they're doing.
- I don't like scripts that make questionable unaudited modificiations
  to my system.
- I don't like scripts that implement hacky workarounds to fix
  problems of their own creation.

Primary design goals for this project are:

- To provide a clean integration using the standard supported mechanism for such integration provided by Batocera: user services.
- To implement clear, understandable. correct, and optimal integration
  through minimal and easily reversible system changes.

## How do I use it?

- Download the `sunshine` service
  [script](https://raw.githubusercontent.com/n2qz/batocera-service-sunshine/refs/heads/master/sunshine)
  and install it into the `/userdata/system/services/` folder on your
  Batocera system.  If you're connecting to your Batocera system via
  network sharing, start at the network share and then navigate to
  `system` and then `services`.  If the `services` folder doesn't
  already exist there, create it.  Here are the commands to make the
  folder and download directly on Batocera:  
  ```shell
  mkdir -p /userdata/system/services && curl -L -o /userdata/system/services/sunshine https://raw.githubusercontent.com/n2qz/batocera-service-sunshine/refs/heads/master/sunshine
  ```  
- Read the script and try to understand what it's doing as well as how
  it's doing it.  Don't run random scripts that you don't understand
  from random Internet strangers who you have no reason to trust.
  I've made every effort to make this script understandable and short.
- In the EmulationStation main menu, press `[START]` then select
  `SYSTEM SETTINGS` -> `SERVICES` -> `SUNSHINE` to enable the toggle
  for the service.  The script will start running, and will download,
  install, and start Sunshine automatically.
- On the remote PC, navigate to the setup page for the newly installed
  Sunshine.  If you haven't changed the hostname for your Batocera
  from the default, you'll find it at https://batocera.local:47990/
- Follow the [Sunshine configuration
  instructions](https://docs.lizardbyte.dev/projects/sunshine/latest/md_docs_2getting__started.html#configuration),
  to configure Sunshine in the web UI.

