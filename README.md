# ImposterWeb

Dear ImGui / WebAssembly / WebGL2 depth-volume mesh viewer.

Planned GitHub Pages address: https://zhunbeifang2-cell.github.io/ImposterWeb/

## Site

The `site/` directory contains the prebuilt application and its 329 bundled Kenney Nature Kit models. `index.html` loads the JavaScript, WebAssembly and data files through relative URLs, so the repository path works on GitHub Pages. No cross-origin-isolation headers or server-side application are required.

Features: searchable model library, OBJ/MTL import, linked original-mesh/depth-volume previews, depth-pyramid acceleration, baking controls and camera orbit/zoom. Performance benchmarking and resource export are not included.

## Deploy

The Pages workflow validates file hashes and uploads `site/` on pushes to `main`. The repository owner must set **Settings → Pages → Build and deployment → Source → GitHub Actions**. Workflow permissions are limited to reading repository contents, writing Pages deployments and requesting the deployment identity token.

For a local preview, serve `site/` using an HTTP server; opening the HTML via `file://` is unsupported.

## Updates

Replace `site/index.html`, `imposter.js`, `imposter.wasm` and `imposter.data` together from the same build, regenerate `site/SHA256SUMS`, and commit. The workflow publishes the new bundle.

## Third-party notices

Licenses are preserved in `site/licenses/`: Dear ImGui (MIT), GLFW (zlib/libpng), GLM (MIT), stb_image / stb_image_write (MIT or public domain) and Kenney Nature Kit (CC0). The stb headers include their full license texts.
