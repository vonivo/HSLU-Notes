Wenn der Session-Key nach einem erfolgreichen Login nicht verändert wird, erlaubt dies eine Session-Fixation-Attack.

Senzanrio:
1. Ein Angreiffer öffnet eine E-Banking-Login-Page in einem Internet-Cafe und merkt sich den Session-Key (momentan noch unauthorisiert.)
2. Ein Benutzer des Inter-Kaffes loggt sich über die schon geöffnete Login-Page ein. (In diesem Moment wird die Session zum Session-Key authentisiert)
3. Der Angreifer kann nun zuhause bei dem E-Banking-Portal den Session-Key setzen und ist als der Benutzer des Kaffees angemeldet.

Man kan eine Applikation dagegen schützen, indem man bei einem Login einen neuen Session-Key generiert.