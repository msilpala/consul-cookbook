# 0.8.3

* Bug Fixes
  * Export GOMAXPROCS when using runit service style

# 0.8.2

* Bug Fixes
  * Set GOMAXPROCS when using runit service style

# 0.8.1

* Bug Fixes
  * Vanilla init script now points to the proper Consul binary and data dir

# 0.8.0

* Enhancements
  * Upgrading from one version to another of Consul is now supported. The Consul service will automatically restart after upgrade.

* Bug Fixes
  * Partial convergeances will now gracefully recover on the next chef run
  * Upstart will now respawn Consul on crash
  * It is no longer possible to set an invalid install method

* Backwards incompatible changes
  * 'consul/ui_dir' attribute was removed. This will automatically be placed within the directory configured by 'consul/data_dir' as 'ui'

# 0.7.1

* Bug Fixes
  * Fixed: Reloading the Consul service when using the runit init style will

# 0.7.0

* Enhancements
  * Added cluster recipe for easily provisioning new Consul clusters. See the README for details
  * Added support for additional options for service_config
  * Added support for Ubuntu 10.04
  * Allow custom data bag / data bag item for Consul encrypt. Default data bag is still `consul` and default item is still `encrypt`
  * Bump support for Golan cookbook `~> 1.4`
  * Added `consul/retry_on_join` attribute which to specify `retry_join` strategy instead of the default: `start_join`
  * Added consul_service_watch LWRP

* Bug Fixes
  * No longer overwrite service user/group attribute when using non-runit init styles
  * Setting the version attribute will now point to the appropriate download URL
  * Use ID attribute to identify consul check definition files instead of name. If no ID is present name will be used

# 0.6.0
* Add support for TLS, and gossip encryption

New features:
- Add [Chef Provisioning][7] recipe for bootstrapping a cluster.
- Add LWRP for defining [an event watch][8] (thanks [@ericfode][9]

# 0.4.4
* Adds server list to a consul instance running as a cluster with a `bootstrap_expect` value greater than one.

# 0.4.3
* Fix race condition when installing Consul as a runit service
* Documentation fixes

# 0.4.2
Bumps default version of Consul to 0.4.0

# 0.4.1
Bumps default version of Consul to 0.3.1.

Adds support to bind to the IP of a named interface.
- bind_interface, advertise_interface, client_interface attributes
  (thanks [@romesh-mccullough][5])

Test/Quality Coverage
- Expands test coverage to the `consul::ui` and `consul::_service` recipes.
- Passes some more [rubocop][6] and [foodcritic][4] code quality tests.
- Only test in Travis against rubies of future past.

# 0.4.0
Adds [ChefSpec][3] tests and software lint/metrics.

Breaking Changes
- Renames *binary_install* recipe to *install_binary*
- Renames *source_install* recipe to *source_binary*

# 0.3.0
Bumps the release of [Consul][1] to 0.3.0.

Adds Service LWRP (thanks [@reset][2]!)

# 0.2.0
Bumps the release of [Consul][1] to 0.2.0.

Adds `consul::service` recipe.
Adds more tests.

Bug Smashing
- Source installation now works properly.
- Test Kitchen shows all green!

# 0.1.0
Initial release of [Consul][1] cookbook.

Source and binary installation recipes.

[1]: http://consul.io
[2]: https://github.com/reset
[3]: https://github.com/sethvargo/chefspec
[4]: http://acrmp.github.io/foodcritic/
[5]: https://github.com/romesh-mccullough
[6]: https://github.com/bbatsov/rubocop
[7]: https://github.com/opscode/chef-provisioning
[8]: http://www.consul.io/docs/commands/watch.html
[9]: https://github.com/ericfode
