# DeepSeek Harness desktop update feed

Release assets consumed by `electron-updater` through the native GitHub provider
(`provider: github`). The application discovers a build through `/releases/latest`
and then reads that release's `latest-mac.yml`, `rc-mac.yml`, or `latest.yml`.

This repository deliberately holds **no source code**. Releases here are created by:

```sh
export DSH_DESKTOP_AUTO_UPDATE_ENV='github'
export DOWNLOAD_GITHUB_REPOSITORY='zhangligong0826/deepseek-harness-updates'
pnpm run publish:github:mac:arm64
```

The repository must stay public: electron-updater reads the public GitHub Atom feed,
which GitHub does not serve to header-authenticated private requests.

Publish each target to its own release tag, because one tag can carry only one
target's channel metadata.

> The `0.1.5-rc.2` release currently here is a synthetic end-to-end verification
> record whose payload is not a real application. Delete it before publishing the
> first genuine build.
