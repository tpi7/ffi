<script lang="ts">
	interface Weapon {
		name: string;
		damage: number;
		hitRate: number;
		equippableBy: string;
		location: string;
		specialEffect?: string;
	}

	interface WeaponCategory {
		label: string;
		weapons: Weapon[];
	}

	const categories: WeaponCategory[] = [
		{
			label: 'Swords',
			weapons: [
				{ name: 'Broadsword', damage: 7, hitRate: 10, equippableBy: 'Warrior/Knight, Thief/Ninja, Red Mage/Wizard, Black Mage/Wizard', location: 'Loot: Elfheim & Marsh Cave 2F. Shop: Pravoka (175 Gil)' },
				{ name: 'Rapier', damage: 9, hitRate: 5, equippableBy: 'Warrior/Knight, Thief/Ninja, Red Mage/Warrior', location: 'Shop: Cornelia (10 Gil)' },
				{ name: 'Scimitar', damage: 10, hitRate: 10, equippableBy: 'Warrior/Knight, Thief/Ninja, Red Mage/Wizard', location: 'Shop: Pravoka (200 Gil)' },
				{ name: 'Saber', damage: 13, hitRate: 5, equippableBy: 'Warrior/Knight, Thief/Ninja, Red Mage/Wizard', location: 'Loot: Cornelia. Shop: Elfheim & Melmond (450 Gil)', specialEffect: 'Strong vs Magic users' },
				{ name: 'Falchion', damage: 15, hitRate: 10, equippableBy: 'Warrior/Knight, Thief/Ninja, Red Mage/Wizard', location: 'Loot: Western Keep. Shop: Melmond (450 Gil)' },
				{ name: 'Rune Blade', damage: 18, hitRate: 15, equippableBy: 'Warrior/Knight, Thief/Ninja, Red Mage/Warrior', location: 'Loot: Chaos Shrine' },
				{ name: 'Werebane', damage: 18, hitRate: 15, equippableBy: 'Warrior/Knight, Red Mage/Wizard, Ninja', location: 'Loot: Chaos Shrine', specialEffect: 'Strong vs Were enemies' },
				{ name: 'Wyrmkiller', damage: 19, hitRate: 15, equippableBy: 'Warrior/Knight, Thief/Ninja, Red Mage/Wizard', location: 'Loot: Mt. Duergar', specialEffect: 'Strong vs Dragon enemies' },
				{ name: 'Coral Sword', damage: 19, hitRate: 15, equippableBy: 'Warrior/Knight, Thief/Ninja, Red Mage/Wizard', location: 'Loot: Cavern of Earth', specialEffect: 'Strong vs Water enemies' },
				{ name: 'Claymore', damage: 21, hitRate: 20, equippableBy: 'Warrior/Knight, Red Mage/Wizard, Ninja', location: 'Loot: Mt. Gulg 2F', specialEffect: 'Strong vs Giant enemies' },
				{ name: 'Venom Blade', damage: 22, hitRate: 20, equippableBy: 'Knight, Red Wizard, Ninja', location: 'Loot: Flying Fortress 1F', specialEffect: 'Casts Poison on all enemies' },
				{ name: 'Mythril Sword', damage: 23, hitRate: 15, equippableBy: 'Warrior/Knight, Red Mage/Wizard, Ninja', location: 'Shop: Elfheim or Crescent Lake (4,000 Gil)' },
				{ name: 'Vorpal Sword', damage: 24, hitRate: 25, equippableBy: 'Knight, Red Wizard, Ninja', location: 'Loot: Tower of Mirage 1F' },
				{ name: 'Flame Sword', damage: 26, hitRate: 20, equippableBy: 'Warrior/Knight, Red Mage/Wizard, Ninja', location: 'Loot: Ice Cavern L2', specialEffect: 'Strong vs Undead & Ice element' },
				{ name: 'Ice Brand', damage: 29, hitRate: 25, equippableBy: 'Warrior/Knight, Red Mage/Wizard, Ninja', location: 'Loot: Mt. Gulg L4, Citadel of Trials L3', specialEffect: 'Strong vs Fire element' },
				{ name: 'Long Sword', damage: 29, hitRate: 10, equippableBy: 'Warrior/Knight, Red Mage/Wizard, Ninja', location: 'Shop: Melmond (1,500 Gil)' },
				{ name: 'Defender', damage: 30, hitRate: 35, equippableBy: 'Knight, Ninja, Red Wizard', location: 'Loot: Waterfall Cavern', specialEffect: 'Casts Blink (evasion up) on user' },
				{ name: 'Sunblade', damage: 32, hitRate: 30, equippableBy: 'Warrior/Knight, Red Mage/Wizard, Ninja', location: 'Loot: Tower of Mirage 2F', specialEffect: 'Strong vs Undead enemies' },
				{ name: 'Sasuke', damage: 33, hitRate: 35, equippableBy: 'Ninja', location: 'Loot: Flying Fortress 3F & Chaos Shrine Fire Floor' },
				{ name: 'Excalibur', damage: 45, hitRate: 35, equippableBy: 'Knight', location: 'Loot: Mt. Duergar (requires Adamantite from Flying Fortress)', specialEffect: 'Strong vs All Monsters' },
				{ name: 'Masamune', damage: 56, hitRate: 50, equippableBy: 'All Classes', location: 'Loot: Chaos Shrine, Air/Wind Floor (Tiamat)' }
			]
		},
		{
			label: 'Daggers',
			weapons: [
				{ name: 'Knife', damage: 5, hitRate: 10, equippableBy: 'Warrior/Knight, Thief/Ninja, Red Mage/Wizard, Black Mage/Wizard', location: 'Shop: Cornelia (5 Gil)' },
				{ name: 'Mythril Knife', damage: 10, hitRate: 15, equippableBy: 'Warrior/Knight, Thief/Ninja, Red Mage/Wizard, Black Mage/Wizard', location: 'Loot: Cornelia Castle & Marsh Cave 3F. Shop: Crescent Lake (800 Gil)' },
				{ name: 'Dagger', damage: 15, hitRate: 10, equippableBy: 'Warrior/Knight, Red Mage/Wizard, Ninja', location: 'Loot: Marsh Cave L2 & Pravoka. Shop: Elfheim (550 Gil)' },
				{ name: 'Cat Claws', damage: 22, hitRate: 35, equippableBy: 'Knight, Ninja, Red Wizard, Black Wizard', location: 'Shop: Gaia (65,000 Gil)' }
			]
		},
		{
			label: 'Axes',
			weapons: [
				{ name: 'Battle Axe', damage: 16, hitRate: 5, equippableBy: 'Warrior/Knight, Ninja', location: 'Shop: Pravoka (550 Gil)' },
				{ name: 'Great Axe', damage: 22, hitRate: 5, equippableBy: 'Warrior/Knight, Ninja', location: 'Loot: Titan\'s Cave' },
				{ name: 'Mythril Axe', damage: 25, hitRate: 10, equippableBy: 'Warrior/Knight, Ninja', location: 'Loot: Mt. Gulg 2F. Shop: Crescent Lake (4,500 Gil)' },
				{ name: 'Light Axe', damage: 28, hitRate: 15, equippableBy: 'Warrior/Knight, Ninja', location: 'Loot: Sunken Shrine 2F & 4F', specialEffect: 'Strong vs Undead. Casts Diara in battle' }
			]
		},
		{
			label: 'Hammers',
			weapons: [
				{ name: 'Hammer', damage: 9, hitRate: 0, equippableBy: 'Warrior/Knight, White Mage/Wizard, Ninja', location: 'Shop: Cornelia or Pravoka (10 Gil)' },
				{ name: 'Mythril Hammer', damage: 12, hitRate: 5, equippableBy: 'Warrior/Knight, White Mage/Wizard, Ninja', location: 'Loot: Elven Castle. Shop: Crescent Lake (2,500 Gil)' },
				{ name: 'Thor\'s Hammer', damage: 18, hitRate: 15, equippableBy: 'Warrior/Knight, White Mage/Wizard, Ninja', location: 'Loot: Tower of Mirage 2F', specialEffect: 'Casts Thundara on all enemies' }
			]
		},
		{
			label: 'Nunchaku',
			weapons: [
				{ name: 'Nunchaku', damage: 12, hitRate: 0, equippableBy: 'Ninja, Monk, Master', location: 'Shop: Cornelia (10 Gil)' },
				{ name: 'Iron Nunchaku', damage: 16, hitRate: 0, equippableBy: 'Ninja, Monk, Master', location: 'Shop: Elfheim (200 Gil)' }
			]
		},
		{
			label: 'Staves',
			weapons: [
				{ name: 'Staff', damage: 6, hitRate: 0, equippableBy: 'All Classes', location: 'Loot: Mt. Gulg 4F & Cavern of Earth 4F. Shop: Cornelia (5 Gil)' },
				{ name: 'Healing Staff', damage: 6, hitRate: 0, equippableBy: 'White Mage/Wizard, Ninja', location: 'Loot: Citadel of Trials 3F' },
				{ name: 'Mage\'s Staff', damage: 12, hitRate: 10, equippableBy: 'Black Mage/Wizard, Ninja', location: 'Loot: Sunken Shrine 4F' },
				{ name: 'Power Staff', damage: 12, hitRate: 0, equippableBy: 'All Classes', location: 'Loot: Western Keep' },
				{ name: 'Crosier', damage: 14, hitRate: 0, equippableBy: 'Warrior/Knight, Monk/Master, Ninja', location: 'Loot: Cornelia Castle. Shop: Elfheim & Melmond (200 Gil)' },
				{ name: 'Spellbinder', damage: 15, hitRate: 15, equippableBy: 'Black Wizard', location: 'Loot: Waterfall Cavern', specialEffect: 'Casts Confuse on all enemies' }
			]
		}
	];
</script>

<div class="mx-auto max-w-7xl px-4 py-10 sm:px-6 lg:px-8">
	<h1 class="text-3xl font-bold text-amber-400 mb-10">Weapons</h1>

	{#each categories as category}
		<section class="mb-12">
			<h2 class="text-2xl font-semibold text-amber-300 mb-4 border-b border-gray-700 pb-2">
				{category.label}
			</h2>

			<div class="overflow-x-auto rounded-lg border border-gray-700">
				<table class="w-full text-sm text-left">
					<thead class="bg-gray-800 text-gray-300 uppercase text-xs tracking-wider">
						<tr>
							<th class="px-4 py-3">Name</th>
							<th class="px-4 py-3 text-center">Damage</th>
							<th class="px-4 py-3 text-center">Hit Rate</th>
							<th class="px-4 py-3">Equippable By</th>
							<th class="px-4 py-3">Location</th>
						</tr>
					</thead>
					<tbody class="divide-y divide-gray-800">
						{#each category.weapons as weapon, i}
							<tr class="{i % 2 === 0 ? 'bg-gray-900' : 'bg-gray-900/50'} hover:bg-gray-800 transition-colors">
								<td class="px-4 py-3 font-medium text-white whitespace-nowrap">
									{weapon.name}
									{#if weapon.specialEffect}
										<span class="block text-xs text-purple-400 mt-0.5">{weapon.specialEffect}</span>
									{/if}
								</td>
								<td class="px-4 py-3 text-center text-orange-300 font-mono">{weapon.damage}</td>
								<td class="px-4 py-3 text-center text-sky-300 font-mono">{weapon.hitRate}</td>
								<td class="px-4 py-3 text-gray-300">{weapon.equippableBy}</td>
								<td class="px-4 py-3 text-gray-400">{weapon.location}</td>
							</tr>
						{/each}
					</tbody>
				</table>
			</div>
		</section>
	{/each}
</div>
