---
slug: /releasing/
sidebar_position: 11
---

# Релизы

Процесс выпуска новой версии Task осуществляется с помощью [GoReleaser][goreleaser]. Вы можете протестировать процесс релиза новой версии локального, вызвав задачу `test-release` в Taskfile.

[GitHub Actions](https://github.com/go-task/task/actions) должны автоматически выпускать артефакты, когда создаётся новый Git-тег в `main` ветке (сырые исполняемые файлы и пакеты DEB и RPM).

Начиная с версии 3.15. сырые, необработанные исполняемые файлы также могут быть воспроизведены и проверены локально путем проверки конкретного тега и вызова `goreleaser build`, используя версию Go, определенную в GitHub Actions.

# Homebrew

Goreleaser автоматически отправит новый коммит в файл [Formula/go-task.rb][gotaskrb] в репозитории [Homebrew tap][homebrewtap] для выпуска новой версии.

# npm

Для выпуска npm обновите версию пакета в файле [`package.json`][packagejson] и затем выполнить `задачу npm:publish`, чтобы опубликовать его.

# Snapcraft

Для выпуска новой версии [Snap пакета][snappackage] необходимо:

- Обновить текущую версию в [snapcraft.yaml][snapcraftyaml].
- Переместить `amd64`, `armhf` и `arm64` артефакты в стабильный канал на панели [Snapcraft][snapcraftdashboard].

# Scoop

Scoop - это менеджер пакетов командной строки для операционной системы Windows. Сообщество поддерживает манифесты пакета Scoop. Владельцы Scoop обычно заботятся об обновлении версий, редактируя [этот файл](https://github.com/ScoopInstaller/Main/blob/master/bucket/task.json). Если вы считаете, что его версия Task устарела, откройте issue, чтобы уведомить нас.

# Nix

Nix - это метод установки, принадлежащий сообществу. Мейнтейнеры Nix пакетов позаботились об обновлении версий, редактируя [этот файл](https://github.com/NixOS/nixpkgs/blob/nixos-unstable/pkgs/development/tools/go-task/default.nix). Если вы считаете, что его версия Task устарела, откройте issue, чтобы уведомить нас.

<!-- prettier-ignore-start -->

<!-- prettier-ignore-end -->
[goreleaser]: https://goreleaser.com/
[homebrewtap]: https://github.com/go-task/homebrew-tap
[gotaskrb]: https://github.com/go-task/homebrew-tap/blob/master/Formula/go-task.rb
[packagejson]: https://github.com/go-task/task/blob/main/package.json#L3
[snappackage]: https://github.com/go-task/snap
[snapcraftyaml]: https://github.com/go-task/snap/blob/master/snap/snapcraft.yaml#L2
[snapcraftdashboard]: https://snapcraft.io/task/releases
