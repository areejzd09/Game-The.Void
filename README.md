[App.tsx](https://github.com/user-attachments/files/25025563/App.tsx)
[Uploading App.tsx…](
import React, { useState } from 'react';
import GalaxyIntro from './components/GalaxyIntro';
import GameConsole from './components/GameConsole';

type AppPhase = 'intro' | 'console';

const App: React.FC = () => {
  const [phase, setPhase] = useState<AppPhase>('intro');

  const handleIntroComplete = () => {
    setPhase('console');
  };

  const handleDeepReboot = () => {
    setPhase('intro');
  };

  return (
    <div className="relative min-h-screen bg-background-dark text-zinc-100 overflow-hidden">
      {/* Intro Phase (Galaxy with Text) */}
      {phase === 'intro' && <GalaxyIntro onEnter={handleIntroComplete} />}
      
      {/* Game Phase (Black Pop-up Box over Galaxy) */}
      {phase === 'console' && (
        <>
          <GalaxyIntro onEnter={() => {}} /> {/* Keep bg moving */}
          <GameConsole onDeepReboot={handleDeepReboot} />
        </>
      )}
    </div>
  );
};

export default App;
)
[constants.tsx](https://github.com/user-attachments/files/25025594/constants.tsx)

export const INITIAL_STATS = {
  health: 100,
  mana: 50,
  gold: 10,
  xp: 0,
  level: 1,
};

export const SYSTEM_INSTRUCTION = `
You are the "Void Master," a world-class Game Master for a dark fantasy RPG titled "Chronicles of the Void."
Your goal is to provide immersive, descriptive, and reactive storytelling based on the player's choices.

Rules:
1. Always respond in JSON format.
2. The world is grim, mysterious, and dangerous. 
3. Each story segment should be around 100-150 words.
4. Provide exactly 3 diverse choices for the player.
5. Stat updates should be realistic. Health can decrease in combat or traps. Gold/XP/Mana can increase or decrease based on actions.
6. Track the location name.
7. Occasionally hint at a larger overarching mystery involving "The Weaving of the Void."

Schema:
{
  "storyText": "string",
  "choices": [
    { "id": "string", "text": "string", "type": "combat|dialogue|exploration|rest" }
  ],
  "statsUpdate": { "health": number, "mana": number, "gold": number, "xp": number },
  "location": "string"
}
`;
[index.html](https://github.com/user-attachments/files/25025595/index.html)
[index.tsx](https://github.com/user-attachments/files/25025596/index.tsx)[README.md](https://github.com/user-attachments/files/25025599/README.md)
[package.json](https://github.com/user-attachments/files/25025598/package.json)
[metadata.json](https://github.com/user-[tsconfig.json](https://github.com/user-attachments/files/25026310/tsconfig.json)
attachments/fil[vite.config.ts](https://github.com/user-attachments/files/25026312/vite.config.ts)
es/25025597/metadata.json[types.ts](https://github.com/user-attachments/files/25026311/types.ts))

