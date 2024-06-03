FROM archlinux:base-devel


ENV LANG en_US
ENV LANGUAGE en_US:en
ENV TZ=Europe/Madrid

EXPOSE 8080 8081 8082 8083 8084 8085

RUN pacman -Syu --noconfirm

RUN pacman -Sy wget ripgrep fzf lazygit python python-pip python-pynvim unzip nodejs npm neovim starship tmux --noconfirm

RUN npm i -g neovim


WORKDIR /root

COPY install-dotfiles /root/install-dotfiles

RUN ./install-dotfiles

RUN git clone https://github.com/amenrio/nvim.git $HOME/.config/nvim

RUN python -m venv $HOME/.config/nvim/venv

RUN $HOME/.config/nvim/venv/bin/python -m pip install -U pip neovim

CMD ["tail", "-f", "/dev/null"]
