RaspberryPi StepMania Binary Package Generator
=====

This helps build `.deb` packages of StepMania binaries for distribution to Raspberry Pi systems.
It should be used on a Raspberry Pi system that has successfully compiled StepMania from source.

Pre-Requisites
-----

1. Your Raspberry Pi system has successfully compiled StepMania from source (perhaps [this repository](https://github.com/SpottyMatt/raspbian-3b-stepmania-arcade) could help with that).
2. Your Raspberry Pi system uses `dpkg` to manage packages.
3. You are able to clone from GitHub.com

Usage
-----

1. Ensure that `/usr/local` contains one or more `stepmania-X.X` directories from successful compilation of StepMania
2. Run `make`
3. One binary package will be generated in the `target` directory for each `/usr/local/stepmania-X.X` directory

### Versioning

Packages will be named following the pattern

	stepmania-VERSION-DATE-ARCHITECTURE.deb

For example, if you built StepMania 5.0.1 beta2, as it stood on July 23, 2018, and packaged it with this tool you would get

	stepmania-5.1.0-b2-2018-07-23-armhf.deb

The version number, source control revision, and revision date used in the binary package
will be determined automatically by looking at the `stepmania` binary that you compiled.

If you want to package and distribute a different version, just compile a different version first!

By default, all binary packages will be labelled with a `YYYY-MM-DD` datestamp, e.g.
If you are packaging a "real release" of StepMania,
run `make RELEASE=true` to generate the packge with just a version number, e.g.

	stepmania-5.1.0-b2-armhf

