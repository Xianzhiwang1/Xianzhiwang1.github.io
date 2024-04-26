# Project-04 neovim config
I have been using neovim for a while now,
and yes, the initial upfront time investment 
in learning vim is definitely worthwhile. I have 
kept my neovim config in 
[this repository](https://github.com/Xianzhiwang1/my-neovim-config-from-scratch),
and it is not very original, since it is basically
put together from chunks and snippets of code here and there on the internet,
and adding a little bit of tweak to suit some personal idiosyncrasies.
Nevertheless, it has everything I need for now. I use 
[parker.nvim](https://github.com/wbthomason/packer.nvim) to manage 
my plugins, but I might switch to `lazy.nvim` in the near future.
While writing this post, I could hit `Alt + k` to
open `markdownpreview` in an existing browser session, which 
is equivalent to type the command `:MarkdownPreview`.
And this is achieved by installing the following plugin via `packer`
```sh
-- install without yarn or npm
use({
    "iamcco/markdown-preview.nvim",
    run = function() vim.fn["mkdp#util#install"]() end,
})

use({ "iamcco/markdown-preview.nvim", run = "cd app && npm install", setup = function() vim.g.mkdp_filetypes = { "markdown" } end, ft = { "markdown" }, })
```
And other plugins are installed similarly.
There are full-blown IDEs right in your terminals 
like [LunarVim](https://github.com/LunarVim/LunarVim),
but right now, I just want to focus on a few things.

### nvim and LaTex
I think the major benefit of writing mathematics
using nvim locally versus 
using [Overleaf](https://www.overleaf.com/)
is you get to use snippets. And there is 
[an excellent guide here](https://evesdropper.dev/files/luasnip/ultisnips-to-luasnip/).
Before I tell you how I use snippets in typesetting math,
let us first figure out how to install Tex locally on your machine.
For me, I am on a ubuntu machine right now, so I open a browser and
go to [https://www.tug.org/texlive/quickinstall.html](https://www.tug.org/texlive/quickinstall.html)
and follow their `tl;dr` direction:
1. `cd` into a directory where you want to keep the binary files,
1. download using this command `wget https://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz` 
1. alternatively, using `curl` to download: `curl -L -o install-tl-unx.tar.gz https://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz`
1. then simply enter the following command in the terminal and wait for the process to complete:
```sh
zcat < install-tl-unx.tar.gz | tar xf -
cd install-tl-*
sudo perl ./install-tl --no-interaction
```
#### one common error
One common error is one might not have `perl` or `curl` or (some other necessary packages)
installed on one's linux machine, so we can check via the following command: 
```sh
curl --version
perl --version
```
and if you do not see the version number and some general info in the standard output,
then you might not have it installed on your machine. To install, (take ubuntu for example)
we can do the following;
```sh
sudo apt update && sudo apt upgrade 
```
this step is to update your system's package repository, 
so you could get the latest versions.
Then we run the following;
```sh
sudo apt install perl
sudo apt install curl
```
and after the installation finishes,
we should be good to go.
#### another common error
Another common error is to forget to add `texlive` to your `PATH`.
After installing Tex, usually in the terminal standard output,
there's direction to add a string like the following to `PATH`:
```sh
/usr/local/texlive/2023/bin/x86_64-linux
```
I have the following lines in my `~/.bashrc` to achieve precisely this:
```sh
# add to PATH texlive
export  PATH="/usr/local/texlive/2023/bin/x86_64-linux:$PATH"
```
and if you have just added this line to your `.bashrc`, 
don't forget to `source` it for it to take effect in the existing 
terminal, otherwise, you need to open a new terminal for it to take effect.
One quick way to check if it is already in your PATH:
```sh
echo "$PATH"
```
then you could just eyeball the output and see if the desired string 
is already there.




