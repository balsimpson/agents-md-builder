# Nuxt profile

Apply only after confirming the repository uses Nuxt or the user explicitly requests these preferences. Do not impose them on an existing project that intentionally differs.

- For a new Nuxt project, check current official docs and use the current official Nuxt UI starter.
- Prefer npm unless the repo clearly uses another package manager or the user specifies one. Inspect `package.json`, package-manager metadata, and lockfiles before changing conventions.
- Prefer existing Nuxt UI components and Tailwind utilities over custom CSS; keep required CSS entry points/imports and add custom CSS only when justified.
- Reuse existing patterns; favor small components/composables with clear responsibilities and separate presentation from domain/data logic when useful.
- Do not remove `.github/` or workflows without inspecting them and confirming this matches the user's requested convention.

Official references: https://ui.nuxt.com/docs/getting-started/installation/nuxt and https://nuxt.com/docs/4.x/getting-started/installation
