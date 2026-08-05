# lineageos-flame-ota

Servidor de actualizaciones OTA "self-hosted" para mi build no oficial de
LineageOS 23.2 (Android 16 / Baklava) para el Google Pixel 4 (`flame`).

La app **Updater** de LineageOS incluida en el propio build apunta aquí en
lugar de a `download.lineageos.org` (que no conoce builds no oficiales),
mediante la propiedad de sistema `lineage.updater.uri`, fijada en
`device/google/coral/flame/device.mk`:

```
lineage.updater.uri=https://raw.githubusercontent.com/rhythmcreative/lineageos-flame-ota/main/api/v1/{device}/{type}.json
```

Con `{device}=flame` y `{type}=unofficial`, la URL real que consulta el
teléfono es:

```
https://raw.githubusercontent.com/rhythmcreative/lineageos-flame-ota/main/api/v1/flame/unofficial.json
```

## Estructura

```
api/v1/flame/unofficial.json   # lista de builds disponibles (formato Updater API v1)
```

Cada build es un objeto:

```json
{
  "datetime": 1754351999,
  "type": "UNOFFICIAL",
  "version": "23.2",
  "files": [
    {
      "filename": "lineage-23.2-20260805-UNOFFICIAL-flame-signed.zip",
      "sha256": "<sha256 del zip>",
      "size": 1234567890,
      "url": "https://github.com/rhythmcreative/lineageos-flame-ota/releases/download/<tag>/lineage-23.2-20260805-UNOFFICIAL-flame-signed.zip"
    }
  ]
}
```

El zip en sí **no** se sube al repo (límite de tamaño de git), se sube como
adjunto de un GitHub Release y se enlaza desde el JSON.

## Publicar un build nuevo

Desde la máquina de compilación, con el zip OTA firmado ya generado:

```
./build_lineage_flame.sh publish <ruta-al-zip-firmado>
```

Esto crea un GitHub Release con el zip adjunto y añade una entrada nueva al
principio de `api/v1/flame/unofficial.json`, y empuja el cambio a `main`.

El teléfono verá la actualización la próxima vez que la app Updater
compruebe (o al forzar "Comprobar actualizaciones" a mano). `raw.githubusercontent.com`
cachea unos minutos, así que puede tardar un poco en reflejarse.
