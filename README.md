# vim-gitlab

vim-gitlab is a vim client for GitLab



## Install

Use any bundle management as you want, for example, using [Plug](https://github.com/junegunn/vim-plug).

```vim
Plug 'bilbopingouin/vim-gitlab', {
    \ 'autoload' : {
    \ 'commands' : 'Gitlab'}}
```

## Config

Several servers or configuration could be defined. For example, the `FOO` configuration could look like

```vim
g:gitlab_config['FOO'] = {
\    'url' : 'https://www.myserver.com/gitlab',
\    'user' : 'myself',
\    'email' : 'myself@myserver.com',
\    'password' : 'optional',
\}
```

But more recent version of Gitlab recommends alternative authentification methods instead of passwords. 
You could use the Gitlab's GUI to get a private token. And then configure as

```vim
g:gitlab_config['FOO'] = {
\    'url' : 'https://www.myserver.com/gitlab',
\    'user' : 'myself',
\    'email' : 'myself@myserver.com',
\    'password' : '',
\    'token' : {'token' : 'private token hash', 'url' : 'https://www.myserver.com/gitlab/api/v4'},
\}
```

## Usage

To list the issues of the repo `sandbox` from the `root` namespace using the `FOO` configuration, you could use

```vim
:Gitlab FOO issues root/sandbox
```

## Known issues

So far, it is mostly the original work from synegan, and I haven't tested everything. However, I already found the following:

- [ ] Only issues (and their respective comments) are accessed (no merge request, or other)
- [ ] Longer path fail, e.g. `root/sandbox/myrepo`
- [ ] The original work was made for gitlab's v3, this one is made for gitlab's v4. It isn't possible to switch between the versions at this stage.

## License

This is a fork from synegan's [vim-gitlab](https://github.com/syngan/vim-gitlab).

I kept the zlib license, but mentioned the files that I modified.

For an earlier work, see also

* https://github.com/thinca/vim-github
* http://d.hatena.ne.jp/thinca/20100701/1277994373

