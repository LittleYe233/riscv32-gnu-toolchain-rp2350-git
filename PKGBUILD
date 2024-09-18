# Maintainer: LittleYe233 <littleye233@gmail.com>

pkgname=riscv32-gnu-toolchain-rp2350-git
pkgver=2024.09.03
pkgrel=1
pkgdesc='Cross compiler for 32-bit RISC-V, specified for Raspberry Pi RP2350'
arch=('x86_64')
url='https://github.com/riscv-collab/riscv-gnu-toolchain'
license=('GPL2')
depends=(autoconf automake curl python gawk bison flex texinfo gperf libtool patchutils cmake libmpc mpfr gmp expat ninja glib2 libslirp bc zlib base-devel)
makedepends=('git')
options=(!emptydirs !strip  staticlibs !lto)
source=("git+${url}.git#tag=${pkgver}")
sha256sums=('SKIP')

_basedir='opt/riscv32-gnu-toolchain-rp2350'

prepare() {
    cd "$srcdir/riscv-gnu-toolchain"
    git clone https://github.com/gcc-mirror/gcc gcc -b releases/gcc-14.2.0
}

build() {
    "$srcdir/riscv-gnu-toolchain/configure" --prefix="$pkgdir/$_basedir" --with-arch=rv32ima_zicsr_zifencei_zba_zbb_zbs_zbkb_zca_zcb --with-abi=ilp32 --with-multilib-generator="rv32ima_zicsr_zifencei_zba_zbb_zbs_zbkb_zca_zcb-ilp32--;rv32imac_zicsr_zifencei_zba_zbb_zbs_zbkb-ilp32--" --with-gcc-src="$srcdir/riscv-gnu-toolchain/gcc"
    make -j$(nproc)
}

package() {
    echo
}
