# pmtiles

PMTiles extacts for use with Protomaps

## Comparison of total tiles count and file size based on the zoom level selected

```
➜  go-pmtiles_1.25.0_Linux_x86_64 ./pmtiles extract https://build.protomaps.com/20250424.pmtiles planet_z0.pmtiles --maxzoom=0
Region tiles 1, result tile entries 1
Extract transferred 66 kB (overfetch 0.05) for an archive size of 66 kB

➜  go-pmtiles_1.25.0_Linux_x86_64 ./pmtiles extract https://build.protomaps.com/20250424.pmtiles planet_z1.pmtiles --maxzoom=1
Region tiles 5, result tile entries 5
Extract transferred 274 kB (overfetch 0.05) for an archive size of 274 kB

➜  go-pmtiles_1.25.0_Linux_x86_64 ./pmtiles extract https://build.protomaps.com/20250424.pmtiles planet_z2.pmtiles --maxzoom=2
Region tiles 21, result tile entries 21
Extract transferred 865 kB (overfetch 0.05) for an archive size of 865 kB

➜  go-pmtiles_1.25.0_Linux_x86_64 ./pmtiles extract https://build.protomaps.com/20250424.pmtiles planet_z3.pmtiles --maxzoom=3
Region tiles 85, result tile entries 84
Extract transferred 2.4 MB (overfetch 0.05) for an archive size of 2.4 MB

➜  go-pmtiles_1.25.0_Linux_x86_64 ./pmtiles extract https://build.protomaps.com/20250424.pmtiles planet_z4.pmtiles --maxzoom=4
Region tiles 341, result tile entries 318
Extract transferred 6.0 MB (overfetch 0.05) for an archive size of 6.0 MB

➜  go-pmtiles_1.25.0_Linux_x86_64 ./pmtiles extract https://build.protomaps.com/20250424.pmtiles planet_z5.pmtiles --maxzoom=5
Region tiles 1365, result tile entries 1090
Extract transferred 15 MB (overfetch 0.05) for an archive size of 15 MB

➜  go-pmtiles_1.25.0_Linux_x86_64 ./pmtiles extract https://build.protomaps.com/20250424.pmtiles planet_z6.pmtiles --maxzoom=6
Region tiles 5461, result tile entries 3467
Extract transferred 43 MB (overfetch 0.05) for an archive size of 43 MB
```

## Converting geojson to pmtiles

1. git clone https://github.com/felt/tippecanoe.git
2. cd tippecanoe
3. make -j
4. make install
5. tippecanoe -o ./countries.mbtiles ./countries.geojson --maximum-zoom=4 --minimum-zoom=0 --no-tile-size-limit
6. ./pmtiles convert ./countries.mbtiles ./countries.pmtiles

## Creating fonts for use with Maps

1. Install build_pbf_glyphs from https://github.com/stadiamaps/sdf_font_tools
2. Get the ttf files for the fonts you want to use.
3. build_pbf_glyphs <TTF Source Directory> <Output Directory>

## Acknowledgments

1. The GeoJSON files used to create country ADM0 and ADM1 pmtiles are sourced from https://www.geoboundaries.org/
2. Global pmtiles are sourced from https://build.protomaps.com
