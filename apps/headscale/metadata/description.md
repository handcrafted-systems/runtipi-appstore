![ci](https://github.com/juanfont/headscale/actions/workflows/test.yml/badge.svg)

An open source, self-hosted implementation of the Tailscale control server.

Join our [Discord server](https://discord.gg/c84AZQhmpx) for a chat.

- [Documentation for the stable version](https://headscale.net/stable/)

## What is Tailscale

Tailscale is [a modern VPN](https://tailscale.com/) built on top of [Wireguard](https://www.wireguard.com/). It [works like an overlay network](https://tailscale.com/blog/how-tailscale-works/) between the computers of your networks - using [NAT traversal](https://tailscale.com/blog/how-nat-traversal-works/).

Everything in Tailscale is Open Source, except the GUI clients for proprietary OS (Windows and macOS/iOS), and the control server.

The control server works as an exchange point of Wireguard public keys for the nodes in the Tailscale network. It assigns the IP addresses of the clients, creates the boundaries between each user, enables sharing machines between users, and exposes the advertised routes of your nodes.

A [Tailscale network (tailnet)](https://tailscale.com/kb/1136/tailnet/) is a private network which Tailscale assigns to a user in terms of private users or an organisation.

## Design goal

Headscale aims to implement a self-hosted, open source alternative to the [Tailscale](https://tailscale.com/) control server. Headscale's goal is to provide self-hosters and hobbyists with an open-source server they can use for their projects and labs. It implements a narrow scope, a _single_ Tailscale network (tailnet), suitable for a personal use, or a small open-source organisation.

## Supporting Headscale

If you like `headscale` and find it useful, there is a sponsorship and donation buttons available in the project repo.

## Features

Please see ["Features" in the documentation](https://headscale.net/stable/about/features/).
