> :warning: This project is considered experimental and is not recommended for production use. Functionality may break at any time.

# create-device
Create a device in the Golioth Cloud with GitHub Actions. Requires setup via [setup-goliothctl](https://github.dev/golioth).

# ✨ Quickstart

To create a device using the latest version of the Golioth CLI:

```yaml
- name: Checkout
  uses: actions/checkout@v4

- name: Setup goliothctl
  uses: golioth/setup-goliothctl@main
  with:
    apiKey: ${{ secrets.APIKEY }}
    projectId: ${{ secrets.PROJECTID }}

- name: Create device
  uses: golioth/create-device@main
  with:
    deviceName: UniqueDeviceName
    deviceTag: ci
```

`deviceName` is a required input. `setup-goliothctl` requires a Golioth API Key and Project ID. See [golioth/setup-goliothctl](https://github.com/golioth/setup-goliothctl) for more details.

# Inputs

| Parameter | Description | Required |
| --- | --- | --- |
| deviceName | Device name | Yes |
| psk | Pre-shared key. Used as part of device authentication. | No |
| pskId | Pre-shared key ID. Used as part of device authentication. | No |
| deviceTag | Tag used to target a release. | No |