# How to install Plex Media Server on Linux

This writeup will cover how to install Plex Media Server on a linux machines to self-host your own media server.

## Getting Started

To start, you can run Plex in many ways whether in a docker container, to off a nas, or how this will cover in a virtual machine off a server. This can also be a standalone box running a flavor of linux. For this, I am going to use Ubuntu server 20.04 LTS.

For system requirements, Plex recommends at least an intel core i3, this varies by how many people you intend to use your server. I typically give my Vm’s 2 cores for plex.

For ram, at least 2 gb but this also will need to vary depending on how many users there will be.
I would advise to give the VM a drive of 50 gb and host the media off the machine in a nas or network drive.


### Prerequisites

Power your new (or old) linux machine up and make sure is it all updated.

Run:

    sudo apt update

and

    sudo apt upgrade -y

After the machine is up to date, we are ready to install Plex.

### Installing

In your linux machine, make a new directory for the plex installer.

    sudo mkdir PlexInstaller

then navigate to The official plex site and under download, find the latest version of Plex Server for linux.

    https://www.plex.tv/media-server-downloads/#plex-media-server

From there, Select Linux, there will be a button for Choose Distro, click on that then a menu of flavors will open.

![image](https://user-images.githubusercontent.com/63487881/214430325-499dd4a0-6bcd-4e70-b1d1-c7ea1330c7b4.png)

![image](https://user-images.githubusercontent.com/63487881/214430380-6747df8c-798c-4b11-a119-9ce6f3a90caf.png)

Right click on the flavor of linux you are running and click copy link in the menu that opens.


After grabbing the link to the latest version

    Give the example

And repeat

    until finished

End with an example of getting some data out of the system or using it
for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Sample Tests

Explain what these tests test and why

    Give an example

### Style test

Checks if the best practices and the right coding style has been used.

    Give an example

## Deployment

Add additional notes to deploy this on a live system

## Built With

  - [Contributor Covenant](https://www.contributor-covenant.org/) - Used
    for the Code of Conduct
  - [Creative Commons](https://creativecommons.org/) - Used to choose
    the license

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code
of conduct, and the process for submitting pull requests to us.

## Versioning

We use [Semantic Versioning](http://semver.org/) for versioning. For the versions
available, see the [tags on this
repository](https://github.com/PurpleBooth/a-good-readme-template/tags).

## Authors

  - **Billie Thompson** - *Provided README Template* -
    [PurpleBooth](https://github.com/PurpleBooth)

See also the list of
[contributors](https://github.com/PurpleBooth/a-good-readme-template/contributors)
who participated in this project.

## License

This project is licensed under the [CC0 1.0 Universal](LICENSE.md)
Creative Commons License - see the [LICENSE.md](LICENSE.md) file for
details

## Acknowledgments

  - Hat tip to anyone whose code is used
  - Inspiration
  - etc
