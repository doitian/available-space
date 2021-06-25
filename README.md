# available-space

Get available disk space in megabytes.

Example:

```
steps:
  - name: get avialable space
    id: available-space
    uses: doitian/available-space@v1
  - run: echo available-space ${{ steps.available-space.outputs.available-space }}
    shell: bash
```

Run a custom bash command when the available space is less than the threshold

```
steps:
  - name: make clean when the available space is less than 40G
    if: ${{ always() }}
    id: available-space
    uses: doitian/available-space@v1
    with:
      clean-threshold: 40000
      clean: make clean
```
