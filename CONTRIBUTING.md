## To serve the site locally on your computer:

- [Install Hugo](https://gohugo.io/installation/)
- Run `hugo server --disableFastRender`

## To update Hugo and Hextra:

When there's a new [Hextra](https://github.com/imfing/hextra) release, find the latest supported `HUGO_VERSION` from [this page](https://github.com/imfing/hextra/blob/main/.github/workflows/pages.yml) and update our `.github/workflows/pages.yaml` file to match it. It kind of looks like this:

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    env:
      HUGO_VERSION: 0.123.4
```

Also, you'll need to update the theme from a device with the Hugo executable installed using:

```bash
hugo mod get -u
hugo mod tidy
```

Finally, create a PR with the changes.

** If, for some reason, you start to see the `README.md` instead of the site after deploying, check the [repo settings](https://github.com/SePrAnd/seprand.github.io/settings/pages) and confirm under "Build and deployment" the source is set to "GitHub Actions".
