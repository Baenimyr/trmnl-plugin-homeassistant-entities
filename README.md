# Plugin Home Assistant—Entités
Ce projet est un plugin pour TRMNL.
Il affiche des entités de HomeAssistant comme la température, l’humidité ou la consommation d’énergie.

Ce plugin utilise l’API REST de HomeAssistant `/api/states/<id>` pour récupérer la valeur de vos senseurs.
```json
{
    "state": "…",
    "attributes": {
        "device_class": "…",
        "friendly_name": "…",
        "unit_of_measurement": "…"
    }
}
```

La valeur *device_class* permet d’afficher une icône.
Liste des senseurs [analogues](https://www.home-assistant.io/integrations/sensor#device-class) et [binaires](https://www.home-assistant.io/integrations/binary_sensor/#device-class).

## Configuration
### Token
Le *token* est un jeton d’accès longue durée, associé à un compte utilisateur.

1. Créer un utilisateur avec seulement les permissions de lecture
2. Dans `/profile/security`, créer un jeton d’accès.
3. Reporter le jeton dans la configuration.

### URL
La valeur *URL* doit être l’URL vers votre serveur HomeAssistant (avec http ou https).

Votre serveur doit être accessible par les serveurs TRMNL (donc internet).
1. Configurer le pare-feu pour autoriser les connexions extérieures.
2. Pour IPv4, créer une redirection de ports sur votre routeur Internet.
  Pour IPv6, votre serveur est déjà accessible depuis Internet.

### Entités
La valeur `entities` est une liste de noms d’entités HomeAssistant, généralement de la forme `sensor.…`.
