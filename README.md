# EMOJI STORY

Start only with some stuff, a swirl, and a spark. Then craft the world one emoji at a time. Be careful, there is a chance for destruction.

---

### CREDITS

- Inspired by the book of [Genesis](https://www.biblegateway.com/passage/?search=Genesis+1&version=GNV)

- Built using the [Emoji One](http://emojione.com/) collection (more at [Emojipedia](http://emojipedia.org/emoji-one/))
  - Their [Guestbook](http://emojione.com/demo/#guestbook-header) is a great scratchpad for crafting recipes and figuring things out

- Originally forked from my insomnia sessions simple clock ticker timer [untitular.html](https://gist.github.com/shuuki/8f5db01e786fecdbc904)


---

## RULES

Your objective is to create resources using the resources that you have.


### RESOURCES

There are three types of resources in the game:

1. base resources
  - gradually fill over time
  - a little weighted randomization
2. expendable resources
  - can be made from either base resources or permanent resources
  - sometimes require certain unlimited resources be unlocked
3. permanent resources
  - only need to be crafted once
  	- but can be crafted many times
  - special resources that require greater investment


base, tools, unlocks

three containers for base materials
[?][?][?]

area to show tools
show an empty gray block if something new can be crafted
show at 50% opacity if it has been crafted before but you have none now
show at 100% opacity if it is currently available
if more than one is available, show a little badge
[ ?
  ? ]


cycle through selection modes on click or touch  
1. temporary selection
2. permanent selection
0. off



## JS PSEUDO SCRATCH
```

new resource

resource is an object {
	name: "Resource Name",
	display: ":icon_character_string:",
	size: number 0-n,
	type: either "base", "permanent", "craftable"
}

iterate over the piles of resources to make an index

inside each pile of resources,

how much is there?


what kind is it?
	base
		refills slowly over time
		roll 1d20
			1. 75% chance for wavy
			2. 20% chance for cyclone
			3. 5% chance for boom

	permanent
		unlocks once 
	expendable

what are its build requirements?





should it be displayed?
	if yes, look at "RENDER RULES"
	if no, see "can you be built now?"
		if cannot be built, do not display

has it been built before?
	if no, mark




can it be built now?


look at requirements
	for each requirement
		look at main index
			if < required, stop looking, can't be built
			if >= required, go to the next requirement and look again
				if that's the end of the requirements, yes it can be built


is it marked?



if it matches all requirements (in "look at requirements")
	and someone has toggled all the resources (see "is it marked?")
		subtract the amount of resources required from each stack
		add the given amount of new resource to its stack
			and mark the new resource as having been built



```
### CSS

```

// RENDER RULES


resources may contain many items

base type
	starts at the top of page 
	has a bar that starts at the top, grows vertically downward
	convert 1*2 + "px" so 2px per amount of resource
	add to style height

goes on top, pushes down base until a point
	elements fill up with buttons in whatever order

	permanent on the right
		text left

	craftable on the left
		text right


buttons are inline, fixed height/width, reflow at will

```


---

### CRAFTING

// base materials  
:wavy_dash: & :cyclone: & :boom: 

// first generation  
> :wavy_dash: + :cyclone: = :snowflake:
> :cyclone: + :boom: = :zap:
> :wavy_dash:x10 + :boom: = :fire: 

// second generation  
> :snowflake: + :zap: = :sweat_drops: or :dash:
> :snowflake:x10 + :cyclone: = :comet:
> :fire:x15 + :zap: = :sunny:
> :snowflake:x20 + :cyclone: = :snowman:
> :snowflake:x100 + :cyclone: =  :new_moon_with_face:




// third generation  
> :comet:x30 + :sunny: + :cyclone: = [:sunrise:]
> :sunny:x20 + :cyclone: = [:milky_way:]

// :sunrise: generation  
> :new_moon_with_face: + :dash: =  [all weather]
> :wavy_dash:x50 + :fire:x5 + :zap: = :volcano:
> :volcano: + :cyclone:x5 = :island: & [ :mountain: & :sunrise_over_mountains: ]
> + :island:x7 + :cyclone: = [ :earth_africa: & :earth_asia: &  :earth_americas: ]
> :mountain: + :snowflake:x10 = [:mountain_snow:]
> :mountain_snow: + :snowman: = :snowman2:



??? :sunrise_over_mountains: + :chestnut: > :seedling: > :ear_of_rice: + :knife: > :rice: + :alembic: > :sake:


// :milky_way: generation
> :rocket: + :zap: = :alien: & :space_invader:
