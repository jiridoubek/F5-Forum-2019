# F5-Forum-2019
Source pro live ukazku na F5 Forum 2019 v Praze

Jak to cele funguje?

Ať v GitHubu (online) nebo v GitLab (lokální instance) se vytváří projekty, evidují změny kódu atd. Jen vyjmenovaní uživatelé mohou akceptovat změny od ostatních. Git eviduje kompletní historii všeho, co je v něm uloženo.

Pokud proběhne Commit, tj. je uložena nová verze souboru tak Git pomocí WebHooku zavolá definovanou url a pošle tam údaje o Commitu.

Cílem WebHooku je URL, na kterém poslouchá orchestrátor, v našem případě Jenkins. Jenkins ví o projektu v Gitu a při informaci o změně si stáhne aktuální verze objektů v projektu.

V nastavení Jenkinsu je pro projekt specifikováno co se má stát za akce. Například poslat notifikaci do Webexu, spustit Ansible Playbook atd., rozšíření je mnoho. V našem případě se spouští ansible playbook deploy_appsvc.yaml, který použije AS3 deklaraci z as3_service.json a nakonfiguruje F5 podle jsonu.
