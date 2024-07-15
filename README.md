# Signal Processing and Learning for Wearables
<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-6-orange.svg?style=flat-square)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

This repository contains a Jupyter book called 'Signal Processing and Learning for Wearables', which presents tutorials on analysing wearable .

The book is available [here](https://peterhcharlton.github.io/bsp-book/intro.html).

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://peterhcharlton.github.io/"><img src="https://avatars.githubusercontent.com/u/9865941?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Peter H Charlton</b></sub></a><br /><a href="#design-peterhcharlton" title="Design">🎨🖋</a></td>
    <td align="center"><a href="https://www.researchgate.net/profile/Marton-Goda"><img src="https://i1.rgstatic.net/ii/profile.image/11431281095286956-1667828620916_Q512/Marton-Goda.jpg" width="100px;" alt=""/><br /><sub><b>Marton Aron Goda</b></sub></a><br /><a href="#design-martonarongoda" title="Content">🖋</a></td>
    <td align="center"><a href="#"><img src="" width="100px;" alt=""/><br /><sub><b>Zixuan Ding</b></sub></a><br /><a href="#design-zixuanding" title="Content">🖋</a></td>
  </tr>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!

## Acknowledgment

The ['MIMIC WFDB Tutorials' book](https://github.com/wfdb/mimic_wfdb_tutorials) was used as a template for this book. Many thanks to [all those who contributed](https://github.com/wfdb/mimic_wfdb_tutorials#contributors-) to this original resource.

## Development

This website was created with [JupyterBook](https://jupyterbook.org/). To set up a local development environment, follow the steps below:

1. Navigate to the project directory (e.g. `bsp-book`)
2. Install the required packages with `pip install -r requirements.txt` (preferably in a virtual environment using something like venv, virtualenv, conda etc.)
3. Change to the directory with the content (e.g. `cd content`)
4. Run `jupyter-book build --all ./` from within this directory to build the book.
5. The HTML bookfiles should have been created in a `_build` folder.
