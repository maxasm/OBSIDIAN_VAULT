`npm` is quite slow tbh. `pnpm` is a better and faster alternative to `npm` that claims to be 2x faster than `npm` and its alternatives. 

To install `pnpm` you need to have `node-js` installed. Use the following bash command to install `node-js` on your `Debian` system. [Link](https://github.com/nodesource/distributions#deb)

Run the following command as `root` 👇

```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | bash - &&\
apt-get install -y nodejs
```

Once you have `node-js` installed, its time to install `pnpm`. Use the following bash command.

```bash
wget -qO- https://get.pnpm.io/install.sh | sh -
```

**`pnpm` has more or less the same commands as `npm`, so use it as you would use `npm` 😉**



