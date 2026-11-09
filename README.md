# Install Hash Fleet with Homebrew

The Mac app and terminal CLI are separate downloads. Install either or both.
These packages require Apple Silicon and macOS 14 (Sonoma) or later.
Intel binaries are not provided in this release.

## Add the project tap

```sh
brew tap smwarren/hashfleet
```

Homebrew requires explicit trust for third-party packages by default starting
with version 6. The trust commands below apply only to the selected package in
this project tap. On older versions without `brew trust`, omit those lines.

Official Homebrew catalog packages are trusted automatically. HashFleet uses
this project-maintained tap until accepted into the official catalog. See the
[official submission roadmap](https://github.com/SMWARREN/hashfleet/blob/main/docs/HOMEBREW.md#moving-into-the-official-homebrew-catalog).

## Native Mac app only

```sh
brew trust --cask smwarren/hashfleet/hashfleet
brew install --cask hashfleet
```

Installs `Hash Fleet.app`. It does not install the terminal command. If you
already installed Hash Fleet through TestFlight or another channel, Homebrew
may refuse the existing app. Do not use `--force` to overwrite a running app.
Choose one app distribution channel and preserve your existing data.

## Terminal CLI only

```sh
brew trust --formula smwarren/hashfleet/hashfleet-cli
brew install hashfleet-cli
```

Installs the `hashfleet` command and its resource bundle, without installing
or launching the Mac app. To explore fictional data without contacting miners:

```sh
hashfleet watch --demo
```

The real CLI can also send reviewed settings changes. It is not exclusively
read-only. No LaunchAgent, mining process, account or background service is
installed by either Homebrew package.

## Downloads and updates

- Source and release downloads: https://github.com/SMWARREN/hashfleet
- Project-maintained Homebrew tap: https://github.com/SMWARREN/homebrew-hashfleet
- Website: https://hashfleet.app

```sh
brew upgrade --cask hashfleet
brew upgrade hashfleet-cli
```

This is the project-maintained tap, not an assertion of inclusion in the
central Homebrew catalog. Both binaries are Developer ID signed and accepted
by Apple notarization. The Mac app includes a stapled notarization ticket.
The standalone CLI relies on the online notarization ticket. Checksums and
license notices accompany the release.

## Stability status

Fixed, not verified. The owner reported roughly ten error-free hours on both
devices. No further stability diagnostics or app workload tests were run for
this distribution task. Release compilation, signing, notarization and package
metadata checks do not establish that intermittent issues cannot recur.
