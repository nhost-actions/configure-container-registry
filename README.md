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

    - name: Set up QEMU
      uses: docker/setup-qemu-action@v2

    - name: Set up Docker Buildx
      uses: docker/setup-buildx-action@v2

    - name: Build and push
      uses: docker/build-push-action@v4
      with:
        context: .
        platforms: linux/amd64,linux/arm64
        push: true
        tags: registry.eu-central-1.nhost.run/8e00eb02-1e53-40a9-9607-604ad199517d:1.2.3
```
