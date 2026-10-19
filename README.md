# Cinnabar RTC TURN compatibility fork

This crate follows [rtc-turn 0.21.1](https://crates.io/crates/rtc-turn), from
[webrtc-rs/rtc](https://github.com/webrtc-rs/rtc/tree/2a732df55ca4bcf26b80914fa0f570cfaf74cfcb/rtc-turn).
It preserves the upstream crate history and MIT/Apache-2.0 licenses. Version-only
dependencies keep the published RTC shared types compatible with consumers.

Cinnabar maintains focused TURN compatibility changes here. The client remains
sans I/O: callers supply packets and time, and perform the resulting network I/O.

`ClientConfig::requested_address_family` selects the relay's address family
independently of the connection to TURN. `None` and IPv4 retain the omitted
attribute and IPv4 default; IPv6 is encoded in both Allocate requests before
integrity and fingerprinting. Invalid family values fail before endpoint
resolution. The allocation remains UDP, including over a TCP carrier.

<h1 align="center">
 <a href="https://webrtc.rs"><img src="https://raw.githubusercontent.com/webrtc-rs/webrtc-rs.github.io/master/res/rtc.png" alt="WebRTC.rs"></a>
 <br>
</h1>
<p align="center">
 <a href="https://github.com/webrtc-rs/rtc/actions">
  <img src="https://github.com/webrtc-rs/rtc/workflows/cargo/badge.svg">
 </a>
 <a href="https://codecov.io/gh/webrtc-rs/rtc">
  <img src="https://codecov.io/gh/webrtc-rs/rtc/branch/main/graph/badge.svg">
 </a>
 <a href="https://deps.rs/repo/github/webrtc-rs/rtc">
  <img src="https://deps.rs/repo/github/webrtc-rs/rtc/status.svg">
 </a>
 <a href="https://crates.io/crates/rtc-turn">
  <img src="https://img.shields.io/crates/v/rtc-turn.svg">
 </a>
 <a href="https://docs.rs/rtc-turn">
  <img src="https://docs.rs/rtc-turn/badge.svg">
 </a>
 <a href="https://doc.rust-lang.org/1.6.0/complement-project-faq.html#why-dual-mitasl2-license">
  <img src="https://img.shields.io/badge/license-MIT%2FApache--2.0-blue" alt="License: MIT/Apache 2.0">
 </a>
 <a href="https://discord.gg/4Ju8UHdXMs">
  <img src="https://img.shields.io/discord/800204819540869120?logo=discord" alt="Discord">
 </a>
</p>
<p align="center">
 RTC TURN Protocol in Rust With Sans-IO
</p>
