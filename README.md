# go-gemini

[![Go Reference](https://pkg.go.dev/badge/github.com/makeworld-the-better-one/go-gemini.svg)](https://pkg.go.dev/github.com/makeworld-the-better-one/go-gemini)

go-gemini is a library that provides an easy interface to create client ~~and servers~~ that speak the [Gemini protocol](https://gemini.circumlunar.space/).

**Spec version supported:** v0.16.0, November 14th 2021

This version of the library was forked from [~yotam/go-gemini](https://git.sr.ht/~yotam/go-gemini/) to add additional features, as well as update it to support newer specs. At the time of forking, it had not seen any new commit for 5 months, and was based on v0.9.2. 

**The server part of this library has been removed.** I don't use it and don't want to maintain it.

This is mostly a personal library. You might want to check out [go-gemini](https://sr.ht/~adnano/go-gemini) (no relation) for more features.

## Project Status

go-gemini is in maintenance mode. Bug and spec fixes only. See my [blog post](https://www.makeworld.space/2023/08/bye_gemini.html) for details.

## Improvements
This fork of the library improves on the original in several ways, some listed above already.

- Client supports self-signed certs sent by the server, but still has other checks like expiry date and hostname
  - The original library could only work with self-signed certs by disabling all security.
- Invalid status code numbers raise an error
- Set default port and scheme for client requests
- Raise error when META strings are too long in the response header
- Supports new status code updates
- If `SSLKEYLOGFILE` is set, session keys are written to the file in NSS format. This is useful for debugging TLS connections (but breaks security, so don't use unless necessary).
- Support proxies
- Support client certs
- Add connection/header timeouts, and read timeouts
- And more!

## Notes

This library only works with Go 1.15 and higher.

If you want relatively reliable code, use the latest tag, not the latest commit. Code in the latest master might be untested/buggy. The API might change between tags since it is still v0.

## License
This library is under the ISC License, see the [LICENSE](./LICENSE) file for details. Portions of this library's code are taken from Go, and are under a different license, which can be found in [LICENSE-GO](./LICENSE-GO). Those files are marked accordingly in their comments.
