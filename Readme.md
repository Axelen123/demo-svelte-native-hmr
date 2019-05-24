# Svelte Native HMR experiment

This is a toy project intended to play & experiment with HMR in [svelte-native](https://github.com/halfnelson/svelte-native) before it is officially supported.

It relies on forked versions of [svelte-loader](https://github.com/sveltejs/svelte-loader) ([fork](https://github.com/rixo/svelte-loader/tree/hmr)), and [svelte-dev-helper](https://github.com/ekhaled/svelte-dev-helper) ([fork](https://github.com/rixo/svelte-dev-helper/tree/hmr)).

**Disclaimer** I am not affiliated with `svelte-loader` team, so this may be completely different to what will eventually be implemented officially.

**WARNING This has been developed and tested against Android only.** I don't own an iPhone, so I've got no idea how it performs on iOS unfortunately.

## Get started

```bash
npx degit rixo/demo-svelte-native-hmr svelte-native-hmr
cd svelte-native-hmr

tns install

tns run android
```

Go edit some `.svelte` files!

## Known limitations

Only preserved state of Svelte components is public props. And also events, but this has not been thoroughly tested, so maybe not so much for events.

This is using some internal API from NativeScript, that they use for their own (core) HMR but are documented as private for the moment.

Also, rapid firing HMR events (i.e. fast ctrl-s in a row) tends to make HMR unstable.

Modals: on HMR, the existing modal is closed and another one is immediately opened with the new content, with a visible transition.

## TODO

- [ ] error management in HMR cycle to achieve better stability (then 1. full reload on save 2. display current error instead of crashing the running app)

- [ ] extract native stuff from svelte-dev-helper into their own native-dedicated package (to prevent webpack from trying to require native things in non-native projects -- for now we're using the `hmr-native` branch or rixo/svelte-dev-helper#hmr-native but that's probably not a perene solution)

- [ ] test modal stack HMR (multiple modals in a frame, with navigation between modal pages)
