# polaris-codescanner
A custom action to run Polaris code scan for SAST. The script looks for polaris.yaml file if present in the root dir of the code repo else generates it dynamically with supplied inputs and default values.

## Inputs
### `POLARIS_SERVER_URL`
  Required
### `POLARIS_ACCESS_TOKEN`
  Required
### `POLARIS_PROJECT_NAME`
  Required
### `POLARIS_PROJECT_BRANCH`
  Required
### `POLARIS_COMMAND_OPTS`
  Optional. 

## Usage 
### Minimum configuration in action workflow

```yaml
uses: sukot1/sk-myaction@v0.01
  with:
    POLARIS_SERVER_URL: <<your_server_url>>
    POLARIS_ACCESS_TOKEN: <<your_access_token>>
    POLARIS_PROJECT_NAME: <<your_project_name>>
    POLARIS_PROJECT_BRANCH: <<your_branch_name>>
```

### Using custom config file
```yaml
uses: sukot1/sk-myaction@v0.01
  with:
    POLARIS_SERVER_URL: <<your_server_url>>
    POLARIS_ACCESS_TOKEN: <<your_access_token>>
    POLARIS_PROJECT_NAME: <<your_project_name>>
    POLARIS_PROJECT_BRANCH: <<your_branch_name>>
    POLARIS_COMMAND_OPTS: "-c polaris.yml"
```
### Using command line options
```yaml
uses: sukot1/sk-myaction@v0.01
  with:
    POLARIS_SERVER_URL: <<your_server_url>>
    POLARIS_ACCESS_TOKEN: <<your_access_token>>
    POLARIS_PROJECT_NAME: <<your_project_name>>
    POLARIS_PROJECT_BRANCH: <<your_branch_name>>
    POLARIS_COMMAND_OPTS: "--co install.coverity.version='default' --co analyze.mode='central'"
```
> Please refer to Synopsys official [documentation](https://sig-docs.synopsys.com/polaris/topics/c_cli-config-overrides.html?hl=install%2Ccoverity%2Cversion) for a full list of supported CLI options for code scanning.
