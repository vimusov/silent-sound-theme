pkgname=silent-sound-theme
pkgver=$(date +'%Y%m%d')
pkgrel=1
pkgdesc='Silent sound theme.'
arch=('x86_64')
url='https://github.com/vimusov/silent-sound-theme'
license=('GPL')
source=('index.theme' 'bell.oga')
b2sums=('0fbab92e7ff677ecba2edfb296a366480ae4f92626f830aad6360df70ff50f7e9869fd11f026f089e492760a425929165263e4aaf7f4c9d99f48f9bce47ca596'
        '46de2a80587a4e950db94d81928e51dee4d047040004f5e6b0668e2c5ea6c2522034d2487397c3ead8b1bd31592cd74752c0dc63e25f12f20eec1dbc35328952')

package()
{
    local name=''
    readonly local names=(
        alarm-clock-elapsed
        audio-channel-front-center
        audio-channel-front-left
        audio-channel-front-right
        audio-channel-rear-center
        audio-channel-rear-left
        audio-channel-rear-right
        audio-channel-side-left
        audio-channel-side-right
        audio-test-signal
        audio-volume-change
        camera-shutter
        complete
        device-added
        device-removed
        dialog-error
        dialog-information
        dialog-warning
        message-new-instant
        message
        network-connectivity-established
        network-connectivity-lost
        phone-incoming-call
        phone-outgoing-busy
        phone-outgoing-calling
        power-plug
        power-unplug
        screen-capture
        service-login
        service-logout
        suspend-error
        trash-empty
        window-attention
        window-question
)
    readonly local theme=${pkgname%%-*}

    install -D -m 0644 "$srcdir"/index.theme \
        "$pkgdir"/usr/share/sounds/$theme/index.theme

    readonly local dstdir="$pkgdir"/usr/share/sounds/$theme/stereo

    install -D -m 0644 --target-directory="$dstdir" "$srcdir"/bell.oga

    for name in ${names[@]}; do
        ln -s bell.oga "$dstdir"/"${name}.oga"
    done
}
