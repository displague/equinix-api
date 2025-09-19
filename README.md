# Equinix API Tool

This project provides a simple shell script for interacting with Equinix APIs. It glues `curl` together with `yq` or `jq` with a common configuration file for authentication credentials. The script also fetches API schemas to help with understanding the API structure.

## Prerequisites

- `curl` command-line tool
- `yq` or `jq` for JSON processing
- Access to Equinix API credentials

## Help

```console
$ equinix-api --help
Usage:
    equinix-api <api_path> [METHOD] [DATA]
    equinix-api --list <api_prefix>
    equinix-api --help

Arguments:
    <api_path>   The API path, e.g. metal/devices or fabric/v4/connections
    [METHOD]     HTTP method (default: GET)
    [DATA]       Data to send (for POST/PUT/PATCH)
    --list       List all available methods and paths for an API prefix (e.g. metal/v1)
    --help       Show this help message

Environment variables:
    PARSER              Parser command (defaults to first found: 'yq -y .', 'jq .', 'cat')
    METAL_AUTH_TOKEN    Auth token for /metal/ APIs (overrides config)
    EQUINIX_CLIENT_ID   OAuth client ID (overrides config)
    EQUINIX_CLIENT_SECRET OAuth client secret (overrides config)

Config files:
    ~/.config/equinix/equinix.yaml: Contains equinix_client_id, equinix_client_secret, metal_auth_token
    ~/.config/equinix/metal.yaml: Contains token for /metal/ APIs

Examples:
    equinix-api ne/v1/metros
    equinix-api metal/v1/locations/metros
    equinix-api /fabric/v4/connections POST '{"foo": "bar"}'
    equinix-api '/colocations/v2/locations?permissionCode=WORK_VISIT'
    equinix-api --list metal/v1
```

## License

This project is licensed under the MIT No Attribution License. See [LICENSE](LICENSE) for details.

## Credits

*Generated with 🤖 by GPT-4.1.*
