# Maintainer: Lukas Fleischer <lfleischer@archlinux.org>
# Contributor: Alexey Yakovenko <waker@users.sourceforge.net>

pkgname=deadbeef-git
pkgver=0.7.0.r1716.gdc0f079ad
pkgrel=1
pkgdesc='A GTK+ audio player for GNU/Linux.'
arch=('x86_64')
url='http://deadbeef.sourceforge.net'
license=('GPL2')
depends=('alsa-lib' 'hicolor-icon-theme' 'desktop-file-utils' 'jansson')
conflicts=(deadbeef)
provides=(deadbeef)
makedepends=('libvorbis' 'libmad' 'flac' 'curl' 'imlib2' 'wavpack' 'libsndfile' 'libcdio' 'libcddb'
             'libx11' 'faad2' 'zlib' 'intltool' 'pkgconfig' 'libpulse' 'libzip' 'libsamplerate'
             'yasm' 'ffmpeg' 'gtk2' 'gtk3')
optdepends=('gtk2: for the GTK2 interface'
            'gtk3: for the GTK3 interface'
            'libsamplerate: for Resampler plugin'
            'libvorbis: for Ogg Vorbis playback'
            'libmad: for MP1/MP2/MP3 playback'
            'mpg123: for MP1/MP2/MP3 playback'
            'flac: for FLAC playback'
            'curl: for Last.fm scrobbler, SHOUTcast, Icecast, Podcast support'
            'imlib2: for artwork plugin'
            'wavpack: for WavPack playback'
            'libsndfile: for Wave playback'
            'libcdio: audio cd plugin'
            'libcddb: audio cd plugin'
            'faad2: for AAC/MP4 support'
            'dbus: for OSD notifications support'
            'pulseaudio: for PulseAudio output plugin'
            'libx11: for global hotkeys plugin'
            'zlib: for Audio Overload plugin'
            'libzip: for vfs_zip plugin'
            'ffmpeg: for ffmpeg plugin')
# DeaDBeeF has not seen a packaged release since 2016, use git.
source=("git+https://github.com/DeaDBeeF-Player/deadbeef.git")
md5sums=('SKIP')

pkgver() {
  cd deadbeef
  git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
  cd ${srcdir}/deadbeef

  ./autogen.sh
  ./configure --prefix=/usr
  make
}

package () {
  cd deadbeef
  make prefix="${pkgdir}/usr" install
}
