カナ入力のキー配置を、ローマ字テーブルを使って自由に設定出来るようにするパッチ
です。今のところ、本来のローマ字入力の方の動作を変えてしまっているので、ローマ字入力と併用することは出来ません。

使い方は、Mozc設定パネルでは、ローマ字入力にし、ユーザー定義のローマ字テーブル
として、カナ入力用のテーブルを与えてやるだけです。

トップディレクトリに、サンプルの kanatable.txt を置いてあります。

本修正を使わずにオリジナルのMozcで同じ事をしようとすると、例えば、「か」と「が
」にそれぞれ、"t", "t[" を割り当てている場合、preedit状態で「か」を入力しようと
して"t"を打鍵したときに、まだこの後に"["が続く可能性があるので、「か」と表示されず、「ｔ」が表示されてしまうという不都合があります。

尚、このローマ字テーフルを仮名入力用に書き換えた時には、Mozcの設定で、

・一般(General)タブの「候補選択ショートカット(Candidate selection shortcut)」を
「なし(No shortcut)」

・入力補助(Advanced)タブの「シフトキーでの入力切替(Shift key mode switch)」を
「オフ(Off)」

として使う事になるはずです。


[Mozc - a Japanese Input Method Editor designed for multi-platform](https://github.com/google/mozc)
===================================

Copyright 2010-2018, Google Inc.

Mozc is a Japanese Input Method Editor (IME) designed for multi-platform such as
Android OS, Apple OS X, Chromium OS, GNU/Linux and Microsoft Windows.  This
OpenSource project originates from
[Google Japanese Input](http://www.google.com/intl/ja/ime/).

Build Status
------------

|Android + OS X + Linux + NaCl |Windows |
|:----------------------------:|:------:|
[![Build Status](https://travis-ci.org/google/mozc.svg?branch=master)](https://travis-ci.org/google/mozc) |[![Build status](https://ci.appveyor.com/api/projects/status/1rvmtp7f80jv7ehf/branch/master?svg=true)](https://ci.appveyor.com/project/google/mozc/branch/master) |

What's Mozc?
------------
For historical reasons, the project name *Mozc* has two different meanings:

1. Internal code name of Google Japanese Input that is still commonly used
   inside Google.
2. Project name to release a subset of Google Japanese Input in the form of
   source code under OSS license without any warranty nor user support.

In this repository, *Mozc* means the second definition unless otherwise noted.

Detailed differences between Google Japanese Input and Mozc are described in [About Branding](docs/about_branding.md).

Build Instructions
------------------

* [How to build Mozc in Docker](docs/build_mozc_in_docker.md): Android, NaCl, and Linux desktop builds.
* [How to build Mozc in OS X](docs/build_mozc_in_osx.md): OS X build.
* [How to build Mozc in Windows](docs/build_mozc_in_windows.md): Windows build.

Release Plan
------------

tl;dr. **There is no stable version.**

As described in [About Branding](docs/about_branding.md) page, Google does
not promise any official QA for OSS Mozc project.  Because of this,
Mozc does not have a concept of *Stable Release*.  Instead we change version
number every time when we introduce non-trivial change.  If you are
interested in packaging Mozc source code, or developing your own products
based on Mozc, feel free to pick up any version.  They should be equally
stable (or equally unstable) in terms of no official QA process.

[Release History](docs/release_history.md) page may have additional
information and useful links about recent changes.

License
-------

All Mozc code written by Google is released under
[The BSD 3-Clause License](http://opensource.org/licenses/BSD-3-Clause).
For thrid party code under [src/third_party](src/third_party) directory,
see each sub directory to find the copyright notice.  Note also that
outside [src/third_party](src/third_party) following directories contain
thrid party code.

### [src/data/dictionary_oss/](src/data/dictionary_oss)

Mixed.
See [src/data/dictionary_oss/README.txt](src/data/dictionary_oss/README.txt)

### [src/data/test/dictionary/](src/data/test/dictionary)

The same to [src/data/dictionary_oss/](src/data/dictionary_oss).
See [src/data/dictionary_oss/README.txt](src/data/dictionary_oss/README.txt)

### [src/data/test/stress_test/](src/data/test/stress_test)

Public Domain.  See the comment in
[src/data/test/stress_test/sentences.txt](src/data/test/stress_test/sentences.txt)

### [src/data/unicode/](src/data/unicode)

UNICODE, INC. LICENSE AGREEMENT.
See each file header for details.
