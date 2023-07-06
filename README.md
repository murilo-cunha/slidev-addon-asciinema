<div style="text-align:center;">
    <img src="https://pbs.twimg.com/profile_images/1388805947691134976/bIiEQTyK_400x400.jpg" width=30%/>
    <img src="https://avatars.githubusercontent.com/u/6506055?s=280&v=4" width=30%/>
</div>

# Asciinema player for Slidev

> Slidev addon to embed asciinema casts to presentations.

## Get started

### Create a project

With NPM:

```console
npm init slidev
```

With Yarn:

```console
yarn create slidev
```

With pnpm:

```console
pnpm create slidev
```

### Add slidev addon

With NPM:

```console
npm install slidev-addon-asciinema
```

With Yarn:

```console
yarn add slidev-addon-asciinema
```

With pnpm:

```console
pnpm add slidev-addon-asciinema
```

### Declare the addon

Either add in your `slides.md` top frontmatter:

```yaml
theme: ...
...
addons:
  - slidev-addon-asciinema
---
# Slides markdown
```

Or add it in your `package.json` file:

```json
{
  // ...
  "scripts": {
    // ...
  },
  "slidev": {
    "addons": [
      "slidev-addon-asciinema"
    ]
  }
}
```

### Use it in your presentation

> 🚨 Wrap the component in `<RenderWhen>` tags. Slidev will otherwise render the component multiple times. See [#396](https://github.com/slidevjs/slidev/issues/396#issuecomment-1137191344) for more information.

```md
# Example

<RenderWhen context="main">
    <Asciinema src="/casts/yourcast.cast" />
</RenderWhen>
```

The parameter `src` will look for static assets from the [`public` directory](https://sli.dev/custom/directory-structure.html#public). In this example, the file is be located at `your-project-root/public/casts/yourcast.cast`.

### Customize your player

All the[ `asciinema-player`'s options](https://github.com/asciinema/asciinema-player#options) are available via `:playerProps`. For example, one could change the speed and the number of lines of player's terminal with:

```md
# Example

<RenderWhen context="main">
    <Asciinema src="/casts/yourcast.cast" :playerProps="{speed: 2, rows: 23}"/>
</RenderWhen>
```

## Known issues

There are a couple of issues already identified

- Player placeholder is resized after playing cast - [#1](https://github.com/murilo-cunha/slidev-addon-asciinema/issues/1)
- Nerd fonts are not supported by the player - [#2](https://github.com/murilo-cunha/slidev-addon-asciinema/issues/2)
- Video's progress does not move in the same place where click happens - [#5](https://github.com/murilo-cunha/slidev-addon-asciinema/issues/5)

Would you like to contribute? Leave a PR! 🚀