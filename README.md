
<img width="1365" height="756" alt="NVIDIA_Overlay_QnIk8O8hWj" src="https://github.com/user-attachments/assets/937c2a4d-9d7d-4deb-b91a-23edadbd8183" />




# How to Modify the ASCII Art and Run Gemini CLI Locally

 This guide teaches you how to change the ASCII art displayed in the terminal and how to run/test the `gemini` command using your local version of the project.

---


## 1. Modifying the ASCII Art

The ASCII art displayed in the terminal is located in:

```
packages/cli/src/ui/components/AsciiArt.ts
```

You can edit the variables `longAsciiLogo`, `shortAsciiLogo`, and `tinyAsciiLogo` to customize the displayed logo.

Example:

```typescript
export const longAsciiLogo = `
Your new logo here
`;
```

After saving your changes, you must rebuild the project for the update to take effect:

```
npm run build
```

---

## 2. Changing the Gradient Colors

The gradient colors for the logo are defined in the themes, in the file:

```
packages/cli/src/ui/themes/theme.ts
```

Look for the `GradientColors` array inside the `lightTheme`, `darkTheme`, or `ansiTheme` objects and change the colors as you wish:

```typescript
GradientColors: ['#4796E4', '#847ACE', '#C3677F'],
```

---

## 3. Running the Gemini CLI Command Locally

To test your changes locally, follow these steps:

### a) Build the project

From the project root, run:

```
npm run build
```

### b) Link the CLI package locally

Go to the CLI package folder:

```
cd packages/cli
```

And run:

```
npm link
```

This creates a global link for the `gemini` command pointing to your local version.

### c) Run the command

Now, just run:

```
gemini
```

Any changes made to the source code will be reflected after running the build again.

---

## 4. Undoing the Local Link

If you want to remove the link and go back to using the global npm version:

```
cd packages/cli
npm unlink
```

---

## 5. Frequently Asked Questions

- **The art doesn't change even after editing?**
  - Make sure to run `npm run build` after saving the file.
  - Check if you are running the `gemini` command via local link (`npm link`).

- **How do I change the theme or colors?**
  - Edit the `GradientColors` array in the desired theme in `theme.ts`.

---

## 6. Useful Resources

- [Official documentation](./docs/index.md)
- [Theme guide](./docs/cli/themes.md)
- [How to contribute](./CONTRIBUTING.md)

---

<p align="center">
  Made with ❤️ by the open source community
</p>
