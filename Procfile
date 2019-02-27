# sudo ifconfig lo0 alias 172.16.123.1
socat-trezor-bridge: socat TCP-LISTEN:21325,bind=172.16.123.1,fork,reuseaddr TCP:127.0.0.1:21325
socat-trezor-agent: socat UNIX-LISTEN:${HOME}/.ssh/trezor-agent.sock,fork,unlink-early,mode=600 TCP:127.0.0.1:22222
trezor-agent: bin/ssh-agent-conf > config/ssh-agent.conf; docker-compose up