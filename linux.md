# Linux `.bashrc and .zshrc`

These are both shell configuration files used to customize the behavior of interactive shell sessions on Unix. They serve similar purposes; _setting environment variables, defining aliases, configuring prompts and running commands on shell setup_. They are primarily known as "rc" (run commands), which are shell configurations for interactive shells. These are the key differences

- `.bashrc` is used by Bash (Bourne Again SHell), it is the default shell on many linux distros
 - `.zshrc` is used by Zsh (Z Shell). It is popular for its advanced features like better autocompletion and themes.


.bashrc: Used by Bash (Bourne Again SHell), the default shell on many Linux distributions like Ubuntu.


## Loading Behavior:

`.bashrc`: Sourced (loaded) for non-login interactive shells (e.g., when you open a new terminal window or run bash in an existing session). For login shells (e.g., SSH login or first terminal after boot), Bash prioritizes .bash_profile or .profile first, which may source .bashrc if configured.

`.zshrc`: Sourced for all interactive shells, whether login or non-login. Zsh has a more modular startup sequence: .zprofile (for login shells, like .bash_profile), .zshenv (always sourced, for environment vars), and others like .zlogin.

## Syntax and Features:

`.bashrc`: Uses Bash-specific syntax. Supports basic scripting, but lacks some of Zsh's built-in enhancements.

`.zshrc`: Uses Zsh syntax, which is mostly backward-compatible with Bash but includes extras like globbing patterns, advanced history search, and plugins. Zsh scripts can be more concise and powerful.

## Common Use Cases:

`.bashrc`: Often simpler for basic setups. If you're switching from Bash to Zsh, you might copy much of it over with minor tweaks.

`.zshrc`: Frequently customized with frameworks like Oh My Zsh, which adds themes, plugins (e.g., git integration, syntax highlighting), and auto-suggestions. This makes it more extensible out of the box.