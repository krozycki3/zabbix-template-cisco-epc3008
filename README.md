# Cisco EPC3008 Zabbix 7.4 Template

This template monitors a Cisco EPC3008 cable modem through its DOCSIS status page.

## Monitored metrics

- Downstream power and SNR for up to 8 channels.
- Upstream transmit power for up to 4 channels.
- Modem operational status and DOCSIS registration stages.
- A host dashboard with line charts and signal threshold lines.

## Thresholds

- Downstream power: warning below -10 or above +10 dBmV; critical outside -15 to +15 dBmV.
- Downstream SNR: warning at 33 dB and critical at 30 dB, with conditions that account for channel power.
- Upstream transmit power: warning outside 38 to 48 dBmV.

Thresholds can be adjusted with template macros.

## Polling interval

The status page is downloaded every 1 minute by default. Change the `{$EPC3008.INTERVAL}` macro on the template or host to use a different interval, for example `30s`. Dependent items are updated whenever the status page is downloaded.

## Installation

In Zabbix 7.4, go to **Data collection → Templates → Import**, select the YAML file, and update the existing template. Then link `Template Cisco EPC3008 DOCSIS` to the modem host.

The default `{$EPC3008.URL}` macro points to `http://192.168.100.1/Docsis_system.asp`. Change it if the modem uses a different address.

## Files

- `Template_Cisco_EPC3008_Zabbix_7.4_with_dashboard.yaml` — import file for Zabbix 7.4, including the dashboard.
