# Install CeWL without `sudo`

Instructions to install and run **CeWL** (user-local install) on Linux, macOS, or WSL **without `sudo`**.

> Two safe options:  
> 1. Install the gem into your user gem directory (`gem install --user-install`).  
> 2. Clone the CeWL repo and run it with Ruby directly (no installation).

---

## Prerequisites (no sudo)
You need a working Ruby and RubyGems on your PATH. Check with:

```bash
sudo apt update
sudo apt install cewl
sudo apt install ruby-spider
gem install spider
ruby --version
gem --version
cewl --version
cewl -d 2 -w test.txt https://example.org
cat test.txt
Example
Domain
use
This
domain
for
documentation
examples
without
needing
permission
Avoid
operations
Learn
more
```
