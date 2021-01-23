# Sans garbage collector

il n'a pas de garbage-collector ("ramasse-miette" en Français), ce qui rend ses performances vraiment bonnes

L'ownership est la fonctionnalité la plus unique en Rust.tout en étant capable d'être lancé sans garbage-collector (comme JavaScript ou Python) qui vérifie constamment la mémoire du programme pour libèrer les ressources non-utilisées.

Rust vous donne le choix de stocker des données sur la pile ou le tas et détermine au moment de la compilation quand la mémoire n'est plus nécessaire et peut être nettoyé. Cela permet une utilisation efficace de la mémoire ainsi qu'un accès à la mémoire plus performant. [Tilde](https://www.tilde.io/), un des premiers utilisateurs de Rust en production dans leur produit [Skylight](https://www.skylight.io/), a découvert qu'il étaient en mesure de [réduire leur utilisation de la mémoire de 5GiB à 50Mib](https://www.rust-lang.org/static/pdfs/Rust-Tilde-Whitepaper.pdf) en réécrivant certains points de terminaison HTTP Java dans un Rust idiomatique. Des économies comme celle-ci s'additionnent rapidement lorsque les fournisseurs de cloud facturent des prix plus élevés pour une mémoire accrue ou des noeuds supplémentaires.

Sans la nécessite d'avoir un garbage collector (ramasse-miettes en français) fonctionnant en permanence, les projets Rust sont bien adaptés pour être utilisés comme bibliothèques par d'autres langages de programmation via des interfaces de fonctions étrangères. Cela permet aux projets existants de remplacer les éléments essentiels aux performances par du code Rust rapide sans les risques de sécurité de la mémoire inhérents aux autres langages de programmation de systèmes. Certains projets ont même été [réécrits progressivement en Rust](https://people.gnome.org/~federico/blog/librsvg-is-almost-rustified.html) en utilisant ces techniques.