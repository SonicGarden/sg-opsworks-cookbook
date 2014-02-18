# Use ImageMagick in opsworks
Layers の Custom Chef Recipes の deploy lifecycle event にて imagemagick::default を追加

# Use papertrail in opsworks
Layers の Custom Chef Recipes の setup lifecycle event にて opsworks_papertrail::log_files を追加
Stack の Custom Chef JSON にて以下を追加
{
  "papertrail": {
    "destination": "logs.papertrailapp.com:[PORT]",
    "log_files": {
      "rails": "/srv/www/[APP_NAME]/shared/log/production.log",
      "batch": "/srv/www/[APP_NAME]/shared/log/batch.log"
    }
  }
}
