# Cisco EPC3008 — template Zabbix 7.4

Szablon monitoruje modem kablowy Cisco EPC3008 przez stronę statusu DOCSIS.

## Monitorowane parametry

- Moc downstream i SNR dla 8 kanałów.
- Moc nadawania upstream dla 4 kanałów.
- Stan pracy modemu i etapy rejestracji DOCSIS.
- Pulpit hosta z wykresami liniowymi oraz poziomami granicznymi.

## Progi

- Moc downstream: ostrzeżenie poniżej −10 lub powyżej +10 dBmV; alarm krytyczny poza −15…+15 dBmV.
- SNR downstream: progi 33 dB (ostrzeżenie) i 30 dB (krytyczny), z warunkiem uwzględniającym moc kanału.
- Moc upstream: ostrzeżenie poza 38…48 dBmV.

Progi można dostosować makrami szablonu.

## Instalacja

W Zabbix 7.4 wybierz **Zbieranie danych → Szablony → Import**, wskaż plik YAML i zaktualizuj istniejący szablon. Następnie połącz template `Template Cisco EPC3008 DOCSIS` z hostem modemu.

Domyślne makro `{$EPC3008.URL}` wskazuje `http://192.168.100.1/Docsis_system.asp`; zmień je, jeśli modem jest dostępny pod innym adresem.

## Pliki

- `Template_Cisco_EPC3008_Zabbix_7.4_with_dashboard.yaml` — plik importu dla Zabbix 7.4.
