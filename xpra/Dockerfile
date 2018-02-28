FROM alpine

RUN apk add --no-cache \
    py-netifaces py2-pip xterm xpra && \
    pip install websockify lz4 && \
    cp /etc/xpra/xorg.conf /etc/X11/xorg.conf.d/00_xpra.conf && \
    adduser me -Du 777 && \
    mkdir -p /run/user/777 /run/xpra && \
    chown me /run/user/777 /run/xpra && \
    echo "xvfb=Xorg -dpi 96 -noreset -nolisten tcp +extension GLX +extension RANDR +extension RENDER" >> /etc/xpra/xpra.conf

CMD xpra start --html=on --daemon=no --notifications=no --dbus-proxy=no --mdns=no --bind-tcp=0.0.0.0:10000 --start-child=xterm --exit-with-children

EXPOSE 10000

USER me
