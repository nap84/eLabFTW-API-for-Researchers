# eLabFTW API for Researchers

## Useful links (and things to copy and paste)

### Episode 1: 01_API

Demo Instance: https://elab.parks.web.gateway.ionos.coscine.dev/

### Episode 2: 02_API_cli

Experiment request template:

```json
{
   "title": "Temperature calibration",
   "body": "<p>Calibration check for the temperature sensor before the measurement run.</p><p>Expected range: 20-25 degrees C.</p>",
   "canread_base": 30,
   "canwrite_base": 20,
   "canread": "{\"teams\": [], \"users\": [], \"teamgroups\": []}",
   "canwrite": "{\"teams\": [], \"users\": [], \"teamgroups\": []}",
   "metadata": {
      "extra_fields": {
         "sample_id": {
            "type": "text",
            "value": "TC-2026-001"
         },
         "instrument": {
            "type": "text",
            "value": "Omega HH506RA"
         },
         "run_number": {
            "type": "number",
            "value": 1
         },
         "target_temperature": {
            "type": "number",
            "value": 22
         },
         "calibration_status": {
            "type": "select",
            "value": "planned"
         }
      }
   }
}
```