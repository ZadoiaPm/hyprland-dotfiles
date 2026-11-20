## Внешний вид 

#### Панель ![Waybar Preview](../assets/bar.png) 

1. Сделайте бэкап своего текущего конфига: 
```bash
cp -r ~/.config/waybar ~/.config/waybar.bak
```
## Зависимости

Обязательные:

```bash
sudo pacman -S waybar hyprland jq playerctl curl
```

Для отдельных модулей:

| Модуль | Что нужно |
|---|---|
| `custom/weather` | `curl` (wttr.in) |
| `custom/media` | `playerctl` |
| `custom/gpu` | `nvidia-smi` (только NVIDIA) |
| `pulseaudio` | `pamixer`, `pavucontrol` |
| `network` | `nm-connection-editor` |
| `custom/notification` | `swaync` |
| `custom/power` | `wofi` |
| иконки | шрифт Nerd Fonts |

## Что поменять под себя

- **Клавиатура.** В `hyprland/language` укажите `keyboard-name` из `hyprctl devices`.
- **Приложения.** Команды в `custom/firefox`, `custom/telegram`, `custom/vesktop`, `custom/amberol`, `custom/steam`, `custom/vscode`.
- **GPU.** Для AMD/Intel удалите модуль `custom/gpu` из `modules-right`.
- **Погода.** Добавьте город: `https://wttr.in/Moscow?format=%c+%t&m`. если оставить то будет по публичному ip угадывать.
- **Часы и uptime.** Форматы в `clock` и `custom/uptime`.
- **Воркспейсы.** Используется `ext/workspaces`. Если он недоступен в вашей версии Waybar, замените на `hyprland/workspaces` и поменяйте блок настроек.
- **Уведомления.** Кнопка вызывает `swaync-client -t -sw`. Если swaync не установлен — удалите `custom/notification`.
