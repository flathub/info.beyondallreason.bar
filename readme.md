# Beyond All Reason - Flathub

This is the repository for the Flathub Flatpak-package for «Beyond All Reason». The Flathub page can
be found here:

https://flathub.org/apps/details/info.beyondallreason.bar


## Updating generated-sources.json

If there were changes in the NPM modules in the **spring-launcher** repository (package.json / package-lock.json files), Flatpak will require the updated **generated-sources.json** file to bundle the correct modules in the build.
To regenerate it, clone https://github.com/flatpak/flatpak-builder-tools/ locally and run the following command:
```
python3 ./node/flatpak-node-generator.py npm --xdg-layout /path/to/spring-launcher/package-lock.json
```
Then, copy the resulting generated-sources.json file to replace the one in the Flatpak build repository.

Read more about bundling NPM modules here: https://docs.flatpak.org/en/latest/electron.html#bundling-npm-packages


## Packaging

To create the package locally or test a new version use:

```
flatpak-builder build-dir info.beyondallreason.bar.yml --force-clean --install --user
```
