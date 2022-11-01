FROM alpine:3.16

RUN apk add --no-cache openssh git && ssh-keygen -A
RUN adduser -D -s /usr/bin/git-shell git && \
    mkdir /home/git/.ssh && \
    echo "git:12345" | chpasswd && \
    chmod 700 /home/git/.ssh

COPY output/fs/home/git/.ssh/authorized_keys /home/git/.ssh/authorized_keys
COPY fs/home/git/git-shell-commands /home/git/git-shell-commands
COPY fs/etc/ssh/sshd_config /etc/ssh/sshd_config

RUN chown git:git -R /home/git/.ssh && \
    chown git:git -R /home/git/git-shell-commands && \
    chmod 600 /home/git/.ssh/authorized_keys && \
    chmod 700 /home/git/git-shell-commands/no-interactive-login

CMD ["/usr/sbin/sshd", "-D"]
