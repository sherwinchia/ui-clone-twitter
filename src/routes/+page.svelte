<script lang="ts">
	const posts = [
		1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21,
		22, 23, 24, 25, 26, 27, 28, 29, 30
	]
	const trendings = [1, 2, 3, 4, 5, 6]

	const sideNav = [
		{
			text: 'Search',
			icon: 'ic:baseline-search'
		},
		{
			text: 'Notifications',
			icon: 'ic:baseline-notifications-none'
		},
		{
			text: 'Messages',
			icon: 'ic:baseline-mail-outline'
		},
		{
			text: 'Lists',
			icon: 'ic:baseline-list-alt'
		},
		{
			text: 'Bookmarks',
			icon: 'ic:baseline-bookmark-border'
		},
		{
			text: 'Verified',
			icon: 'ic:outline-verified'
		},
		{
			text: 'Profile',
			icon: 'ic:outline-person'
		},
		{
			text: 'More',
			icon: 'ic:outline-more-horiz'
		}
	]
</script>

<svelte:head>
	<title>Home / Twitter</title>
</svelte:head>

<main class="min-h-screen bg-black text-neutral-500">
	<div class="grid content-center w-full max-w-6xl grid-cols-8 mx-auto">
		<div class="relative h-full col-span-1 xl:col-span-2">
			<div
				class="sticky top-0 flex flex-col items-center w-full h-screen gap-5 p-4 xl:items-start text-neutral-100"
			>
				<iconify-icon icon="mdi:twitter" class="text-4xl" />
				<a href="/" class="flex items-center gap-4">
					<div class="">
						<iconify-icon icon="ic:baseline-home" class="text-3xl" />
					</div>
					<span class="hidden text-xl font-semibold xl:block">Home</span>
				</a>
				{#each sideNav as nav}
					<a href="/" class="flex items-center gap-4">
						<div class="">
							<iconify-icon icon={nav.icon} class="text-3xl" />
						</div>
						<span class="hidden text-xl xl:block">{nav.text}</span>
					</a>
				{/each}
				<button
					class="p-3 text-lg font-bold rounded-full xl:px-10 xl:py-2 xl:mr-10 bg-primary text-neutral-100"
				>
					<iconify-icon
						icon="material-symbols:edit-outline"
						class="block m-auto text-2xl xl:hidden"
					/>
					<span class="hidden xl:block">Tweet</span>
				</button>

				<div
					class="flex justify-center w-full gap-4 mt-auto xl:justify-between xl:p-4"
				>
					<img
						src="https://i.pravatar.cc/300"
						alt=""
						class="object-contain object-center w-10 h-10 overflow-hidden rounded-full"
					/>
					<div class="items-center justify-between flex-1 hidden gap-4 xl:flex">
						<div class="flex flex-col flex-1">
							<span class="font-bold text-neutral-100">John Doe</span>
							<span class="text-neutral-500">@johndoe</span>
						</div>
						<iconify-icon icon="ic:outline-more-horiz" class="text-xl" />
					</div>
				</div>
			</div>
		</div>
		<div class="flex-1 col-span-7 xl:col-span-4 border-x border-neutral-700">
			<div
				class="sticky top-0 px-4 pt-4 border-b bg-black/50 backdrop-blur border-neutral-700"
			>
				<h1 class="pb-6 text-xl font-bold text-neutral-100">Home</h1>
				<div class="flex w-full">
					<button class="w-1/2 p-2 text-base font-semibold text-center">
						<span class="pb-2 border-b-4 border-primary text-neutral-100">
							For You
						</span>
					</button>
					<button class="w-1/2 p-2 text-base font-semibold text-center">
						<span class="pb-2 border-b-0 border-primary">Following</span>
					</button>
				</div>
			</div>
			<div class="flex border-b border-neutral-700">
				<div class="flex w-full gap-4 p-4">
					<img
						src="https://i.pravatar.cc/300"
						alt=""
						class="object-contain object-center w-10 h-10 overflow-hidden rounded-full"
					/>
					<div class="flex-col flex-1">
						<textarea
							class="w-full text-lg text-left bg-transparent resize-none text-neutral-100"
							placeholder="Whats Happening?!"
						/>
						<div class="flex items-center justify-between gap-4">
							<div class="flex gap-3 text-primary">
								<iconify-icon
									icon="ic:outline-image"
									class="text-xl cursor-pointer"
								/>
								<iconify-icon
									icon="ic:outline-gif-box"
									class="text-xl cursor-pointer"
								/>
								<iconify-icon
									icon="ic:round-format-list-bulleted"
									class="text-xl cursor-pointer"
								/>
								<iconify-icon
									icon="ic:outline-emoji-emotions"
									class="text-xl cursor-pointer"
								/>
								<iconify-icon
									icon="ic:outline-calendar-month"
									class="text-xl cursor-pointer"
								/>
								<iconify-icon
									icon="ic:outline-location-on"
									class="text-xl cursor-pointer"
								/>
							</div>
							<button
								class="px-5 py-[.3rem] font-bold rounded-full bg-primary text-neutral-100"
							>
								Tweet
							</button>
						</div>
					</div>
				</div>
			</div>
			<div class="flex flex-col">
				{#each posts as posts}
					<div class="flex gap-4 p-4 border-b border-neutral-700">
						<img
							src="https://loremflickr.com/320/240/paris/all"
							alt=""
							class="object-contain object-center w-10 h-10 overflow-hidden rounded-full"
						/>
						<div class="flex flex-col flex-1">
							<div class="flex items-center gap-1">
								<span class="font-bold text-neutral-100">John Doe</span>
								<span class="">@johndoe</span>
								<span class="">Jul 8</span>
							</div>
							<p class="pb-2 text-neutral-100">
								Lorem ipsum dolor sit amet consectetur adipisicing elit.
								Voluptate voluptates asperiores itaque earum cumque qui suscipit
								quos, rerum aliquam quidem a ipsum repellat reprehenderit
								eveniet ad recusandae laudantium, sed animi.
							</p>
							<div class="flex justify-between md:justify-start md:gap-10">
								<div class="flex items-center gap-2 text-sm cursor-pointer">
									<iconify-icon
										icon="ic:baseline-chat-bubble-outline"
										class="text-lg cursor-pointer"
									/>
									<span>4</span>
								</div>
								<div class="flex items-center gap-2 text-sm cursor-pointer">
									<iconify-icon
										icon="ant-design:retweet-outlined"
										class="text-lg cursor-pointer"
									/>
									<span>1</span>
								</div>
								<div class="flex items-center gap-2 text-sm cursor-pointer">
									<iconify-icon
										icon="ic:baseline-favorite-border"
										class="text-lg cursor-pointer"
									/>
									<span>2</span>
								</div>
								<div class="flex items-center gap-2 text-sm cursor-pointer">
									<iconify-icon
										icon="ic:baseline-bar-chart"
										class="text-lg cursor-pointer"
									/>
									<span>96</span>
								</div>
								<div class="flex items-center gap-2 text-sm cursor-pointer">
									<iconify-icon
										icon="ic:baseline-ios-share"
										class="text-lg cursor-pointer"
									/>
								</div>

								<div class="flex items-center gap-2 text-sm cursor-pointer">
									<iconify-icon
										icon="ph:google-drive-logo"
										class="text-lg cursor-pointer"
									/>
									<span>Tip</span>
								</div>
							</div>
						</div>
					</div>
				{/each}
			</div>
		</div>
		<div class="relative flex-col hidden col-span-2 lg:flex">
			<div class="sticky top-0 z-10 w-full px-4 py-2 bg-black">
				<div class="relative w-full">
					<iconify-icon
						icon="ic:baseline-search"
						class="absolute text-2xl -translate-y-1/2 left-2 top-1/2"
					/>
					<input
						type="text"
						placeholder="Search Twitter"
						class="w-full py-2 pl-10 rounded-full bg-[#202226] focus:outline focus:outline-primary text-neutral-100"
					/>
				</div>
			</div>

			<div class="sticky bottom-0 flex flex-col self-end gap-4 p-4 pt-16">
				<div
					class="flex rounded-xl bg-[#16191D] p-4 text-neutral-100 flex-col gap-2"
				>
					<span class="pb-4 text-xl font-bold">Get Verified</span>
					<span class="font-bold">Subscribe to unlock new features.</span>
					<div>
						<button
							class="px-4 py-2 mr-10 font-bold rounded-full bg-primary text-neutral-100"
						>
							Get Verified
						</button>
					</div>
				</div>

				<div
					class="flex rounded-xl bg-[#16191D] p-4 text-neutral-100 flex-col gap-2"
				>
					<span class="pb-4 text-xl font-bold">Trends for you</span>
					<div class="flex flex-col gap-4">
						{#each trendings as trending}
							<div class="flex justify-between gap-4 text-neutral-500">
								<div class="flex flex-col">
									<span class="text-xs">Trending {trending}</span>
									<span class="text-lg font-semibold text-neutral-100"
										>Trending {trending}</span
									>
									<span class="text-xs">10.6 Tweets</span>
								</div>
								<iconify-icon
									icon="ic:outline-more-horiz"
									class="text-xl cursor-pointer"
								/>
							</div>
						{/each}
					</div>

					<a href="/" class="text-xs text-primary">Show More</a>
				</div>
				<div
					class="flex rounded-xl bg-[#16191D] p-4 text-neutral-100 flex-col gap-2"
				>
					<span class="pb-4 text-xl font-bold">Who to follow</span>
					<div class="flex flex-col gap-4">
						<div class="flex gap-4">
							<img
								src="https://i.pravatar.cc/300"
								alt=""
								class="object-contain object-center w-10 h-10 overflow-hidden rounded-full"
							/>

							<div class="flex flex-col flex-1">
								<span class="font-semibold">John Doe</span>
								<span class="text-xs text-neutral-500">@johndoe</span>
							</div>
							<div>
								<button
									class="px-3 py-1 text-sm font-semibold text-black bg-white rounded-full"
									>Follow</button
								>
							</div>
						</div>
						<div class="flex gap-4">
							<img
								src="https://i.pravatar.cc/300"
								alt=""
								class="object-contain object-center w-10 h-10 overflow-hidden rounded-full"
							/>

							<div class="flex flex-col flex-1">
								<span class="font-semibold">John Doe</span>
								<span class="text-xs text-neutral-500">@johndoe</span>
							</div>
							<div>
								<button
									class="px-3 py-1 text-sm font-semibold text-black bg-white rounded-full"
									>Follow</button
								>
							</div>
						</div>
						<div class="flex gap-4">
							<img
								src="https://i.pravatar.cc/300"
								alt=""
								class="object-contain object-center w-10 h-10 overflow-hidden rounded-full"
							/>

							<div class="flex flex-col flex-1">
								<span class="font-semibold">John Doe</span>
								<span class="text-xs text-neutral-500">@johndoe</span>
							</div>
							<div>
								<button
									class="px-3 py-1 text-sm font-semibold text-black bg-white rounded-full"
									>Follow</button
								>
							</div>
						</div>
					</div>

					<a href="/" class="text-xs text-primary">Show More</a>
				</div>
			</div>
		</div>
	</div>
</main>
