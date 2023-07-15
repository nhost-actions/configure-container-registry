# configure-container-registry

Configures docker to access Nhost's container registry

## Usage

You can use this action to configure docker to use Nhost's container registry:


```yaml
    - name: Install Nhost CLI
      id: install-nhost-cli
      uses: nhost-actions/install-nhost-cli@v1

    - name: Authenticate with Nhost
      uses: nhost-actions/authenticate@v1
      with:
        pat: ${{ secrets.NHOST_PAT }}

    - name: Configure docker credentials
      uses: nhost-actions/configure-container-registry@v1

    - name: Build and push
      uses: docker/build-push-action@v4
      with:
        push: true
        tags: registry.eu-central-1.nhost.run/8e00eb02-1e53-40a9-9607-604ad199517d:1.2.3
```
