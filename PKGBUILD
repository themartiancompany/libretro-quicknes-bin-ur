# SPDX-License-Identifier: AGPL-3.0

#    ----------------------------------------------------------------------
#    Copyright © 2025  Pellegrino Prevete
#
#    All rights reserved
#    ----------------------------------------------------------------------
#
#    This program is free software: you can redistribute it and/or modify
#    it under the terms of the GNU Affero General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.
#
#    This program is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU Affero General Public License for more details.
#
#    You should have received a copy of the GNU Affero General Public License
#    along with this program.  If not, see <https://www.gnu.org/licenses/>.

# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>

_os="$( \
  uname \
    -o)"
_evmfs="true"
_pkgname="libretro-quicknes"
_Pkg="QuickNES"
pkgname="${_pkgname}-bin"
pkgver=2025.1.29
pkgrel=1
_pkgdesc=(
  "NES core for RetroArch."
)
pkgdesc="${_pkgdesc[*]}"
arch=(
  'arm'
  'armv7l'
)
_http="https://github.com"
_ns="kode54"
url="${_http}/${_ns}/${_Pkg}"
license=(
  'GPL2'
)
depends=(
  'retroarch'
)
[[ "${_os}" != "GNU/Linux" ]] && \
[[ "${_os}" == "Android" ]] && \
  depends+=(
    'inteppacman'
  )
optdepends=(
)
[[ "${_os}" != "GNU/Linux" ]] && \
[[ "${_os}" == "Android" ]] && \
  optdepends+=(
  )
makedepends=(
  'coreutils'
  'evmfs'
)
checkdepends=(
)
provides=(
  "${_pkgname}=${pkgver}"
)
conflicts=(
  "${_pkgname}"
)
source=()
sha256sums=()
_lib="quicknes_libretro_android.so"
_evmfs_network="100"
_evmfs_address="0x69470b18f8b8b5f92b48f6199dcb147b4be96571"
_evmfs_ns="0x87003Bd6C074C713783df04f36517451fF34CBEf"
_lib_sum="d673db3424732d271d992a635cd6f3786a635b73c840562e151694d7ff1ac128"
_evmfs_uri="evmfs://${_evmfs_network}/${_evmfs_address}/${_evmfs_ns}/${_lib_sum}"
_lib_src="${_lib}::${_evmfs_uri}"
source+=(
  "${_lib_src}"
)
sha256sums+=(
  "${_lib_sum}"
)

validgpgkeys=(
)

package() {
  local \
    _dest_dir
  _dest_dir="/data/data/com.retroarch/cores"
  install \
    -dm755 \
    "${pkgdir}${_dest_dir}"
  install \
    -Dm644 \
    "${srcdir}/${_lib}" \
    "${pkgdir}/${_dest_dir}/${_lib}"
}

# vim: ft=sh syn=sh et
