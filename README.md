# PulseAudio Volume Control

## Build
Via GitHub repository
```bash
$ docker build --tag alireaza/pavucontrol:$(date -u +%Y%m%d) --tag alireaza/pavucontrol:latest https://github.com/alireaza/pavucontrol.git
```

## Run
```bash
$ docker run \
--interactive \
--tty \
--rm \
--mount="type=bind,source=/tmp/.X11-unix,target=/tmp/.X11-unix" \
--env="DISPLAY=$DISPLAY" \
--device="/dev/dri:/dev/dri" \
--env="PULSE_SERVER=unix:${XDG_RUNTIME_DIR}/pulse/native" \
--name="pavucontrol" \
alireaza/pavucontrol
```

