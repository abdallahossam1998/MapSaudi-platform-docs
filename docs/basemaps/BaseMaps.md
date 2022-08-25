# Maps

Estimated reading time : 1 minutes

## Maps preview
If you want to share a preview of your map, use this endpoint.

```
https://basemaps.mapsaudi.com/styles/your-style-id/?raster?access_token=your-MapSaudi-access-token
\___/   \___________________/        \___________/  \____/              \________________________/   
  |               |                        |           \                             |                   
scheme          domain                  style ID       preview type          authentication token           
```

- **style ID**: your style ID or one of our default styles or your custom style from the lab.
- **authentication** token: create your access token on the Keys page.
- **preview type** (optional): choose your preview in raster or vector. Valid values are raster, vector.