# Svelte Native HMR experiment

This is a toy project intended to play & experiment with HMR in [svelte-native](https://github.com/halfnelson/svelte-native) before it is officially supported.

It relies on forked versions of [svelte-loader](https://github.com/sveltejs/svelte-loader) ([fork](https://github.com/rixo/svelte-loader/tree/hmr)), and [svelte-dev-helper](https://github.com/ekhaled/svelte-dev-helper) ([fork](https://github.com/rixo/svelte-dev-helper/tree/hmr)).

**Disclaimer** I am not affiliated with `svelte-loader` team, so this may be completely different to what will eventually be implemented officially.

## Get started

```bash
npx degit rixo/demo-svelte-native-hmr svelte-native-hmr
cd svelte-native-hmr

tns install

tns run android
```

Try HMR!
