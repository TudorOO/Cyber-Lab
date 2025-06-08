
| Manager de pachete | Tip de pachet | Sisteme de operare / distributie | Comenzi specifice         | Fisier/director de configurare       | Utilitar(e) de configurare |
| ------------------ | ------------- | -------------------------------- | ------------------------- | ------------------------------------ | -------------------------- |
| APT                | .deb          | distributii bazate pe Debian     | apt, aptitude, dpkg       | /etc/apt/sources.list                | apt, dpkg                  |
| YUM & DNF          | .rpm          | distributii bazate pe RedHat     | dnf, rpm                  | /etc/dnf/dnf.conf, /etc/yum.repos.d/ | dnf, rpm                   |
| ZYpp               | .rpm          | distributii bazate pe openSUSE   | zypper, rpm               | /etc/zypp/zypp.conf                  | zypper, rpm                |
| Pacman             | .tar          | Arch                             | pacman, pactree, paccache | /usr/local/etc/pacman.conf           | pacman                     |
| Portage            | .tar.gz       | Gentoo                           | emerge, equery, eix       | /etc/portage                         | emerge                     |
| Port               | .txz          | FreeBSD                          | pkg                       | /etc/portsnap.conf                   | portsnap, pkg              |
| Homebrew           | .tar.gz       | macOS                            | brew                      | N/A                                  | brew                       |
| MacPorts           | .tbz2         | macOS                            | port                      | /etc/macaports                       | port                       |
| Chocolatey         | .nupkg        | Windows                          | choco                     | choco config                         | choco                      |

| Sistem de pachete | Actualizare cache/versiuni     | Upgrade system/pachete           | Cautare                     | Instalare              |
| ----------------- | ------------------------------ | -------------------------------- | --------------------------- | ---------------------- |
| APT               | apt update                     | apt upgrade                      | apt search package          | apt install package    |
| DNF/YUM           | dnf makecache                  | dnf update                       | dnf search package          | dnf install package    |
| Pacman            | pacman -Fy                     | pacman -Syu                      | pacman -Ss package          | pacman -S package      |
| Portage           | emerge --sync                  | emerge --update <br>--deep world | emerge <br>--search package | emerge package         |
| ZYpp              | N/A                            | zypper update                    | zypper search package       | zypper install package |
| Port              | portsnap fetch update          | pkg upgrade                      | pkg search package          | pkg install package    |
| Homebrew          | brew update                    | brew upgrade                     | brew search package         | brew install package   |
| MacPorts          | port selfupdate, <br>port sync | port upgrade outdated            | port search package         | port install package   |
| Chocolatey        | N/A                            | choco upgrade all                | choco search package        | choco install package  |

| Sistem de pachete | Dezinstalare            | Descarcare<br>(fara instalare)             | Descarcare sursa              |
| ----------------- | ----------------------- | ------------------------------------------ | ----------------------------- |
| APT               | apt remove package      | apt install -d package                     | apt source package            |
| DNF/YUM           | dnf remove package      | dnf download package                       | dnf download --source package |
| Pacman            | pacman -R package       | pacman -Sw package                         | asp export package            |
| Portage           | emerge -C package       | emerge --fetchnly package                  | N/A                           |
| ZYpp              | zypper remove package   | zypper install <br>--download-only package | zypper source-install package |
| Port              | pkg remove package      | pkg fetch package                          | pkg fetch package             |
| Homebrew          | brew uninstall package  | N/A                                        | brew fetch package            |
| MacPorts          | port uninstall package  | N/A                                        | port fetch package            |
| Chocolatey        | choco uninstall package | choco download package                     | N/A                           |

| Sistem de pachete | Cautare pachet local              | Continut pachet instalat | Pachet al unui fisier existent  |
| ----------------- | --------------------------------- | ------------------------ | ------------------------------- |
| APT               | dpkg -l package                   | dpkg -L package          | dpkg -S /usr/bin/package        |
| DNF/YUM           | rpm -qi package                   | rpm -ql package          | rpm -qf /usr/bin/package        |
| Pacman            | packman -Qs package               | packam -Ql package       | packman -Qo package             |
| Portage           | N/A                               | emerge files package     | emerge belongs /usr/bin/package |
| ZYpp              | rpm -qi package                   | rpm -ql package          | rpm -qf /usr/bin/package        |
| Port              | pkg info package                  | pkg info -l package      | pkg provides /usr/bin/package   |
| Homebrew          | brew ls \| grep -i package        | brew ls package          | N/A                             |
| MacPorts          | port list                         | port contents package    | port provides /usr/bin/package  |
| Chocolatey        | choco search --local-only package | N/A                      | N/A                             |

<h3> Managerii de tip "all in one"</h3>
	Pe langa packet managerii listati mai sus sunt si ***solutii de tip "all in one"***. Acestea
instaleaza aplicatii sub forma de pachete si creeaza un mediu izolat in jurul acestora, pentru ca acestea sa nu interactioneze cu alte pachete.
	Exemplu de asemenea managerii sunt: ***Snapcraft, Flatpak si AppImage***.
	***Flatpack*** creeaza un mediu izolat folosind o forma de virtualizare de aplicatie, similar cu 
un container.

<h3>Medii specifice pentru limbaje de programare</h3>
Unele limbaje de programare au sisteme de gestiune al pachetelor specifice:
	**pip** - Python
	**gem** - Ruby
	**npm** - Javascript(Node.js)
Pentru a folosi aceste sisteme fara a afecta restul sistemului, trebuie folosite utilitati care sa izoleze sistemul:
	**virtualenv** - pip
	**bundler** - gem
	**nvm** -npm