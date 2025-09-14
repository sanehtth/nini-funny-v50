
# NiNi — All-in-one v50

## What’s inside
- Netlify Functions: scene picker, U5 explore (start/next/tap/collect/finish), passport APIs.
- Tools: import scenes (WebP 3 size + Firestore), import vocab JSON.
- UI: GameNiniExploreU5 + PassportBook + NiNi Actor + styles.
- Topics skeleton `topics/T_FARM/` to start filling.

## Quick start
1) Copy into your project.
2) `pnpm add firebase-admin sharp yargs @netlify/functions`
3) ENV: FIREBASE_PROJECT_ID, FIREBASE_CLIENT_EMAIL, FIREBASE_PRIVATE_KEY, FIREBASE_STORAGE_BUCKET
4) Put source images into `topics/T_FARM/images/src`, edit `scenes.farm.json` & `vocab.json`.
5) Import:
   - `pnpm tsx tools/import_scenes_from_json.ts --topic T_FARM --json ./topics/T_FARM/scenes/scenes.farm.json --mediaDir ./topics/T_FARM/images/src`
   - `pnpm tsx tools/import_vocab_from_json.ts --topic T_FARM --json ./topics/T_FARM/vocab.json`
6) Run dev (`netlify dev`) and render:
```tsx
import GameNiniExploreU5 from "@/games/ninitrip/GameNiniExploreU5";
<GameNiniExploreU5 userId="demoUser" topicCode="T_FARM" />
```
