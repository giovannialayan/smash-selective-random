<script>
  import Character from '../components/character.svelte';
  import Button from '../components/button.svelte';
  import Dropdown from '../components/dropdown.svelte';

  import { onMount } from 'svelte';

  onMount(() => {
    let items = localStorage.getItem(localStorageKey);

    if (items) {
      profiles = JSON.parse(items);
    }
  });

  const localStorageKey = 'smash-selective-random.profiles';

  const characters = [
    {
      name: 'mario',
      selected: true,
      id: 0,
    },
    {
      name: 'donkeykong',
      selected: true,
      id: 1,
    },
    {
      name: 'link',
      selected: true,
      id: 2,
    },
    {
      name: 'samus',
      selected: true,
      id: 3,
    },
    {
      name: 'darksamus',
      selected: true,
      id: 4,
    },
    {
      name: 'yoshi',
      selected: true,
      id: 5,
    },
    {
      name: 'kirby',
      selected: true,
      id: 6,
    },
    {
      name: 'fox',
      selected: true,
      id: 7,
    },
    {
      name: 'pikachu',
      selected: true,
      id: 8,
    },
    {
      name: 'luigi',
      selected: true,
      id: 9,
    },
    {
      name: 'ness',
      selected: true,
      id: 10,
    },
    {
      name: 'captainfalcon',
      selected: true,
      id: 11,
    },
    {
      name: 'jigglypuff',
      selected: true,
      id: 12,
    },
    {
      name: 'peach',
      selected: true,
      id: 13,
    },
    {
      name: 'daisy',
      selected: true,
      id: 14,
    },
    {
      name: 'bowser',
      selected: true,
      id: 15,
    },
    {
      name: 'iceclimbers',
      selected: true,
      id: 16,
    },
    {
      name: 'sheik',
      selected: true,
      id: 17,
    },
    {
      name: 'zelda',
      selected: true,
      id: 18,
    },
    {
      name: 'drmario',
      selected: true,
      id: 19,
    },
    {
      name: 'pichu',
      selected: true,
      id: 20,
    },
    {
      name: 'falco',
      selected: true,
      id: 21,
    },
    {
      name: 'marth',
      selected: true,
      id: 22,
    },
    {
      name: 'lucina',
      selected: true,
      id: 23,
    },
    {
      name: 'younglink',
      selected: true,
      id: 24,
    },
    {
      name: 'ganondorf',
      selected: true,
      id: 25,
    },
    {
      name: 'mewtwo',
      selected: true,
      id: 26,
    },
    {
      name: 'roy',
      selected: true,
      id: 27,
    },
    {
      name: 'chrom',
      selected: true,
      id: 28,
    },
    {
      name: 'mrgameandwatch',
      selected: true,
      id: 29,
    },
    {
      name: 'metaknight',
      selected: true,
      id: 30,
    },
    {
      name: 'pit',
      selected: true,
      id: 31,
    },
    {
      name: 'darkpit',
      selected: true,
      id: 32,
    },
    {
      name: 'zerosuitsamus',
      selected: true,
      id: 33,
    },
    {
      name: 'wario',
      selected: true,
      id: 34,
    },
    {
      name: 'snake',
      selected: true,
      id: 35,
    },
    {
      name: 'ike',
      selected: true,
      id: 36,
    },
    {
      name: 'pokemontrainer',
      selected: true,
      id: 37,
    },
    {
      name: 'diddykong',
      selected: true,
      id: 38,
    },
    {
      name: 'lucas',
      selected: true,
      id: 39,
    },
    {
      name: 'sonic',
      selected: true,
      id: 40,
    },
    {
      name: 'kingdedede',
      selected: true,
      id: 41,
    },
    {
      name: 'olimar',
      selected: true,
      id: 42,
    },
    {
      name: 'lucario',
      selected: true,
      id: 43,
    },
    {
      name: 'rob',
      selected: true,
      id: 44,
    },
    {
      name: 'toonlink',
      selected: true,
      id: 45,
    },
    {
      name: 'wolf',
      selected: true,
      id: 46,
    },
    {
      name: 'villager',
      selected: true,
      id: 47,
    },
    {
      name: 'megaman',
      selected: true,
      id: 48,
    },
    {
      name: 'wiifittrainer',
      selected: true,
      id: 49,
    },
    {
      name: 'rosalinaandluma',
      selected: true,
      id: 50,
    },
    {
      name: 'littlemac',
      selected: true,
      id: 51,
    },
    {
      name: 'greninja',
      selected: true,
      id: 52,
    },
    {
      name: 'palutena',
      selected: true,
      id: 53,
    },
    {
      name: 'pacman',
      selected: true,
      id: 54,
    },
    {
      name: 'robin',
      selected: true,
      id: 55,
    },
    {
      name: 'shulk',
      selected: true,
      id: 56,
    },
    {
      name: 'bowserjr',
      selected: true,
      id: 57,
    },
    {
      name: 'duckhunt',
      selected: true,
      id: 58,
    },
    {
      name: 'ryu',
      selected: true,
      id: 59,
    },
    {
      name: 'ken',
      selected: true,
      id: 60,
    },
    {
      name: 'cloud',
      selected: true,
      id: 61,
    },
    {
      name: 'corrin',
      selected: true,
      id: 62,
    },
    {
      name: 'bayonetta',
      selected: true,
      id: 63,
    },
    {
      name: 'inkling',
      selected: true,
      id: 64,
    },
    {
      name: 'ridley',
      selected: true,
      id: 65,
    },
    {
      name: 'simon',
      selected: true,
      id: 66,
    },
    {
      name: 'richter',
      selected: true,
      id: 67,
    },
    {
      name: 'kingkrool',
      selected: true,
      id: 68,
    },
    {
      name: 'isabelle',
      selected: true,
      id: 69,
    },
    {
      name: 'incineroar',
      selected: true,
      id: 70,
    },
    {
      name: 'piranhaplant',
      selected: true,
      id: 71,
    },
    {
      name: 'joker',
      selected: true,
      id: 72,
    },
    {
      name: 'hero',
      selected: true,
      id: 73,
    },
    {
      name: 'banjoandkazooie',
      selected: true,
      id: 74,
    },
    {
      name: 'terry',
      selected: true,
      id: 75,
    },
    {
      name: 'byleth',
      selected: true,
      id: 76,
    },
    {
      name: 'minmin',
      selected: true,
      id: 77,
    },
    {
      name: 'steve',
      selected: true,
      id: 78,
    },
    {
      name: 'sephiroth',
      selected: true,
      id: 79,
    },
    {
      name: 'pyramythra',
      selected: true,
      id: 80,
    },
    {
      name: 'kazuya',
      selected: true,
      id: 81,
    },
    {
      name: 'sora',
      selected: true,
      id: 82,
    },
    {
      name: 'miibrawler',
      selected: true,
      id: 83,
    },
    {
      name: 'miiswordfighter',
      selected: true,
      id: 84,
    },
    {
      name: 'miigunner',
      selected: true,
      id: 85,
    },
  ];

  let currentCharacter = 'mario';

  let profileName = '';
  let newProfileMenuOn = false;

  let profiles = [];
  let currentProfile = -1;

  function updateCharacterSelection(id, selected) {
    characters[id].selected = selected;
  }

  function updateAllSelection(selectState) {
    for (let i = 0; i < characters.length; i++) {
      characters[i].selected = selectState;
    }
  }

  function roll() {
    const availableCharacters = characters.filter((c) => c.selected && c.name != currentCharacter);

    const randomCharacter = Math.floor(Math.random() * availableCharacters.length);

    currentCharacter = availableCharacters[randomCharacter].name;
  }

  function createNewProfile() {
    let newProfile = {
      name: profileName,
      characters: characters.filter((c) => c.selected).map((c) => c.id),
    };

    profiles = [...profiles, newProfile];

    newProfileMenuOn = false;
    currentProfile = profiles.length - 1;

    saveProfiles();
  }

  function changeProfile(index) {
    for (let i = 0; i < characters.length; i++) {
      characters[i].selected = profiles[index].characters.includes(i);
    }

    currentProfile = index;
  }

  function editProfile() {
    profiles[currentProfile].characters = characters.filter((c) => c.selected).map((c) => c.id);

    saveProfiles();
  }

  function deleteProfile(index) {
    profiles.splice(index, 1);
    profiles = profiles;

    saveProfiles();
  }

  function saveProfiles() {
    localStorage.setItem(localStorageKey, JSON.stringify(profiles));
  }
</script>

<div class="flex flex-col items-center gap-8">
  <div class="charactersDiv flex flex-col items-center gap-4 my-4">
    {#each { length: 7 } as _, i}
      <div class="flex flex-row justify-content-center gap-4">
        {#each { length: 13 } as _, j}
          {#if i * 13 + j < 86}
            <Character
              name={characters[i * 13 + j].name}
              selected={characters[i * 13 + j].selected}
              id={i * 13 + j}
              on:select={(e) => updateCharacterSelection(e.detail.id, e.detail.selectState)}
            ></Character>
          {/if}
        {/each}
      </div>
    {/each}
  </div>
  <div class="charactersMobileDiv flex flex-col items-center gap-4 my-4">
    {#each { length: 15 } as _, i}
      <div class="flex flex-row justify-content-center gap-4">
        {#each { length: 6 } as _, j}
          {#if i * 6 + j < 86}
            <Character
              name={characters[i * 6 + j].name}
              selected={characters[i * 6 + j].selected}
              id={i * 6 + j}
              on:select={(e) => updateCharacterSelection(e.detail.id, e.detail.selectState)}
            ></Character>
          {/if}
        {/each}
      </div>
    {/each}
  </div>

  <div class="flex flex-row justify-center gap-5">
    <Button on:click={() => updateAllSelection(true)}>select all</Button>
    <Button on:click={() => updateAllSelection(false)}>deselect all</Button>
  </div>

  <div class="flex flex-col items-center gap-5">
    <Button on:click={roll}>roll</Button>
    <img class="w-48" src="characters selected/{currentCharacter} selected.webp" alt="{currentCharacter} selected image" />
  </div>

  <div>
    <div class="flex flex-col items-center gap-3 {!newProfileMenuOn ? '' : 'hidden'}">
      <Button
        on:click={() => {
          newProfileMenuOn = true;
        }}
      >
        new profile
      </Button>
      <div class={profiles.length == 0 || currentProfile == -1 ? 'hidden' : ''}>
        <Button on:click={editProfile}>
          save {profiles.length > 0 && currentProfile != -1 ? profiles[currentProfile].name : ''}
        </Button>
      </div>
    </div>

    <div class="flex flex-col items-center gap-5 {newProfileMenuOn ? '' : 'hidden'}">
      <Button
        on:click={() => {
          newProfileMenuOn = false;
        }}>close</Button
      >
      <div class="flex flex-row justify-content-center gap-2">
        <p class="text-white">profile name:</p>
        <input bind:value={profileName} />
      </div>
      <Button on:click={createNewProfile}>create profile</Button>
    </div>
  </div>

  <div>
    <Dropdown
      options={profiles.map((p) => {
        return p.name;
      })}
      on:dropdownChange={(e) => changeProfile(e.detail.optionIndex)}
      on:dropdownDelete={(e) => deleteProfile(e.detail.optionIndex)}
    >
      profiles
    </Dropdown>
  </div>
</div>

<style>
  .charactersDiv {
    display: flex;
  }

  .charactersMobileDiv {
    display: none;
  }

  @media (max-width: 576px) {
    .charactersDiv {
      display: none;
    }
    .charactersMobileDiv {
      display: flex;
    }
  }
</style>
