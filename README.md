# Haskell
---

## Helpful Docs
- [Learn You a Haskell for Great Good](http://learnyouahaskell.com/)        
- [Haskell Offical Documentation](https://www.haskell.org/documentation/)
- [Haskell from the Very Beginning](https://www.haskellfromtheverybeginning.com/)
- [Real World Haskell](http://book.realworldhaskell.org/)
- [Yesod Web Framework](https://www.yesodweb.com/book)

## Instructions for Initial Install on MacOS
- Make sure `xcode utils` are installed properly
- Make sure `xquartz` is installed
- Make sure `macports` is installed
- Restart machine
- Test proper installation with `port` to see if command is found
  - I would recommend adding `alias ports='sudo port'` to your `~/.bashrc` or similar shell profile
- Run: `( mkdir -p ~/.ghcup/bin && curl https://gitlab.haskell.org/haskell/ghcup/raw/master/ghcup > ~/.ghcup/bin/ghcup && chmod +x ~/.ghcup/bin/ghcup) && echo "Success"`
- Add `export PATH="$HOME/.cabal/bin:$HOME/.ghcup/bin:$PATH"` to your `~/.bashrc` or similar shell profile
- Remember and install if needed, [man-db](http://man-db.nongnu.org/)
  - with the assumed alias from earlier, run: `ports install man-db`
- Test proper installation with `cabal` or `ghcup` to ensure commands work properly
- [More Instructions from Haskell Docs](https://docs.haskellstack.org/en/stable/install_and_upgrade/#os-x)
- For your first project, you can run: `cabal init -n --is-executable` and then `cabal v2-run` where you should see `Hello, Haskell!` as the output

## Installation of the GHC JavaScript Compiler
- Visit [main repo for ghcjs](https://github.com/ghcjs/ghcjs)
- Run: `cd` and then `git clone --branch ghc-8.6 https://github.com/ghcjs/ghcjs.git`
- Run: `cd ghcjs`
- Run: `git submodule update --init --recursive`
- Ensure: `PATH="$HOME/.cabal/bin:$PATH"` is in profile
- Run: `ports install happy`
- Run: `ports install alex`
- Run: `./utils/makePackages.sh`
- Remember, GHC manual is: [/opt/local/share/doc/ghc-8.10.3/users_guide.pdf](file:///opt/local/share/doc/ghc-8.10.3/html/index.html)
- _You can copy/edit `/opt/local/etc/ghci.conf`to your directory `~/.ghc` for a user-specific startup configuration._
- _I also liked these packages from `macports`: `ports install stack lhs2tex hlint hscolour HaXml`
- Try this for troubleshooting `hlint` install after errors: https://hackage.haskell.org/package/base
        

### Cabal Sandbox Option
- Run: `./utils/makeSandbox.sh` and `cabal install`
- OR: `stack build`

### Notes
- _For information on creating a mk/build.mk file, please visit: http://ghc.haskell.org/trac/ghc/wiki/Building/Using#Buildconfiguration_
- _Checkout Sphinx [here for more info](https://github.com/yesodweb/yesod/wiki/Sphinx-Search)._