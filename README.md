# Arch-Update

`arch-update` is a simple and effective Bash script designed to update your Arch Linux system and its AUR packages with a user-friendly experience. It dynamically selects the best mirrors based on your country, ensuring faster updates.

## Features

- **Dynamic Mirror Selection**: Automatically determines your country and updates the mirror list for optimal download speeds.
- **System & AUR Updates**: Easily updates both system packages and AUR packages using `pacman` and `paru`.
- **Interactive & User-Friendly**: Prompts you before taking any action, ensuring you're in control of the process.
- **Error Handling & Color-Coded Messages**: Displays success, warning, and error messages in color, making it easier to follow the script's progress.

## Installation

To install `arch-update`, run the following command to download, make the script executable, and move it to `/usr/bin` for global access:

```bash
curl -O https://raw.githubusercontent.com/amateur-hacker/arch-update/main/arch-update\
&& chmod +x arch-update && sudo mv arch-update /usr/bin/arch-update
```

Once installed, you can run `arch-update` from anywhere on your system.

## Usage

```bash
./arch-update [OPTIONS]
```

### Options

- `-h, --help`: Show the help message and exit.

The script will guide you through the update process and prompt you for your confirmation before proceeding with any action.

## Script Flow

1. **Determines Your Country**: Uses your IP address to figure out your location and fetches the best mirror list for your region.
2. **Updates System Mirrors**: It then updates the list of mirrors to use the best and most reliable ones for your country.
3. **System Package Update**: The script checks if there are any available system updates and installs them using `pacman`.
4. **AUR Package Update**: If `paru` is installed, the script checks for and updates AUR packages.
5. **Completion**: Once the update process is complete, you’ll receive a summary message.

## Example Output

```bash
This script will update your Arch Linux system and its mirrors. You may need to enter your password for sudo operations.
Would you like to continue? [Y/n] y

Determining your current location...
Detected country code: IN
Detected country name: India

Fetching the latest mirror list for India...
Mirror list updated successfully.

Synchronizing system and AUR package databases...
Checking for system package updates...
System packages have updates available. Updating now...
System packages updated successfully.

Checking for AUR package updates...
AUR packages have updates available. Updating now...
AUR packages updated successfully.

System is up-to-date!
```

## Dependencies

- `curl`: Required for fetching the country and IP data.
- `geoip`: Used to determine the user's country based on IP.
- `pacman-contrib`: Includes the `rankmirrors` utility to fetch the fastest mirrors.
- `paru`: Optional AUR helper for updating AUR packages.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Feel free to fork, modify, and submit pull requests. If you find any issues or have suggestions for improvement, please open an issue in the GitHub repository.

## Acknowledgments

- [Arch Linux](https://archlinux.org) for being an amazing rolling release distribution.
- [paru](https://github.com/Morganamilo/paru) for the AUR package manager.
- [geoiplookup](https://github.com/maxmind/geoip-api-c) for geolocation services.
