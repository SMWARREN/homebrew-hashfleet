# HashFleet Homebrew packages have moved

The Mac app, CLI, website, release downloads, and Homebrew package definitions
are now maintained together in **[HashFleet](https://github.com/SMWARREN/HashFleet)**.

This repository is a frozen compatibility copy for existing installations.
Do not submit new package updates here.

## Move an existing tap

```sh
brew tap --custom-remote smwarren/hashfleet https://github.com/SMWARREN/HashFleet.git
brew update-reset "$(brew --repo smwarren/hashfleet)"
```

The reset replaces local changes in that Homebrew tap checkout. Preserve any
custom edits there first. It does not reinstall the app or CLI, or erase their
data. Trust the package you want from the new source:

```sh
# Mac app
brew trust --cask smwarren/hashfleet/hashfleet

# CLI
brew trust --formula smwarren/hashfleet/hashfleet-cli
```

## New installations

Follow the current [installation guide](https://github.com/SMWARREN/HashFleet/blob/main/docs/HOMEBREW.md).
After setup, the separate install commands remain:

```sh
brew install --cask hashfleet
brew install hashfleet-cli
```

[Downloads](https://github.com/SMWARREN/HashFleet/releases/latest) · [Website](https://hashfleet.app)
