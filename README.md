# invokeai-docker-build

Standalone repo that builds Docker images of [Pfannkuchensack/InvokeAI](https://github.com/Pfannkuchensack/InvokeAI)
and pushes them to GHCR. Kept separate so the workflow file never lands in
feature branches / upstream PRs.

## Images

- `ghcr.io/pfannkuchensack/invokeai:main-cuda` (also `:latest-cuda`)
- `ghcr.io/pfannkuchensack/invokeai:main-cpu`
- `ghcr.io/pfannkuchensack/invokeai:main-rocm`

## Trigger

- Manually:

```bash
gh workflow run docker.yml \
  -f ref=main \
  -f variants=cuda,cpu,rocm
```

## Usage on remote

```bash
docker pull ghcr.io/pfannkuchensack/invokeai:main-cuda
# then follow docker/README.md in the InvokeAI repo for run.sh / compose
```
