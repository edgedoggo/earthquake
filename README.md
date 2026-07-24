# Earthquake
A Foundry VTT module to shake the screen like an earthquake.

![earthquake](https://private-user-images.githubusercontent.com/152747753/289698879-47535dc4-65bc-4d8e-9428-2de33f6b5a27.gif?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODIzMTUxODcsIm5iZiI6MTc4MjMxNDg4NywicGF0aCI6Ii8xNTI3NDc3NTMvMjg5Njk4ODc5LTQ3NTM1ZGM0LTY1YmMtNGQ4ZS05NDI4LTJkZTMzZjZiNWEyNy5naWY_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNjI0JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDYyNFQxNTI4MDdaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1mNjUwNDFhNGNjZTE3ZmYyZTgyNTZhNjkwMGM1YzAxZWMxMDFjNDg4NjQzNjEzNDg1NWZhYWYyN2RlZTEwMmVjJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZnaWYifQ.CUm_tmu96wmpAerXp_rX9MfqNPr9-X1ccG9n8woQUms)

Have you ever wanted your players to shake and tremble as the ground rocks and shifts below them? 
Is a castle crumbling and they need to escape before its too late?
Is the very mountain itself exploding with magma as an active volcano erupts?

Well, before now - your players might have no idea... but now - the whole map is SHAKING!!!

Earthquake lets a GM trigger a configurable earthquake effect across every connected player client, with optional GM shaking.

The module includes bundled sounds, a draggable compendium macro, and an optional chat prompt for Dexterity checks. Tokens that fail the configured DC can be knocked Prone automatically.

Earthquake 3.1.7 is verified for Foundry VTT 14 while retaining runtime fallbacks for Foundry VTT 10-13. If your table needs the exact pre-v14 package, use the `v3.0.0` release instead of `latest`.

------------------------------------------------------------------

## Installation

1) Install Earthquake from the Module Installation page of Foundry VTT

https://github.com/openkyle/earthquake/releases/download/latest/module.json

2) Enable it in your world.
3) Open the **Earthquake Macros** compendium pack.
4) Drag the **Earthquake** macro to your hotbar.
5) Click the macro to shake all connected clients and play the configured sound.

## Settings

- **Shake Intensity**: How strong the canvas shake feels.
- **Shake Duration**: How long the shake lasts.
- **Earthquake Sound**: The audio file played for every connected client.
- **Earthquake Sound Volume**: Per-client playback volume.
- **Shake GM Canvas**: Allows the GM to opt out of the visual shake.
- **Show quick menu on macro launch**: Let the GM adjust earthquake settings before shaking.
- **Dexterity Check Prompt Audience**: Choose no prompt, every actor token on the active scene, or player-owned tokens on the active scene only.
- **Dexterity Check DC**: The DC used by the chat prompt.
- **Knock Prone On Failed Check**: Applies the Prone status when a token fails.

## Macro API

The included macro runs:

```js
await game.earthquake.trigger();
```

Advanced macros can override settings for a single earthquake:

```js
await game.earthquake.trigger({
  intensity: 120,
  duration: 8000,
  soundPath: "modules/earthquake/assets/sounds/collapse.ogg",
  promptAudience: "everyone",
  dexterityDC: 16,
  applyProne: true
});
```
