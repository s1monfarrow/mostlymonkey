# Systems Thinking
Or why is my bloody shower too hot or cold.

## The Boiler
We have an old, probably cheap, boiler in our house. Hot water on demand, all good. the control on the front looks like it controls the temperature of the water, but what it really does is control the size of the flame to heat it. This is sort of the same thing, except when it isn’t.

The interesting thing about this is the slower the water goes through the hotter it gets, to a point, then the flame turns off and it gets cold. Linear relationship with a cutoff.

## The Shower
The shower is newer and probably the most recent bit of plumbing in the house. Like most new showers it has a small bar of wax in the middle that expand and contracts with the temperature of the water flowing near it. The wax changes the amount of hot water flowing through regulating the temperature of the water raining down on my sleepy head. It’s a good simple system that it pretty much indestructible.

## Most of the time
This has been working fine for ages, the boiler makes the hot water and the shower water is at a consistent temperature. All good, happy dude slowly waking up in the shower.

## Gahh
Recently out of the blue the water coming out of the shower is either hotter than the sun or like the north Atlantic. Occasionally, and this is extra exciting, it cycles rapidly between the two. This results in me being awake but not necessarily happy.

## The Solution
I’d love to say that it was me that solved this problem, it wasn’t. It was my wife, who I’m required (by laws more fundamental than physics) to say is smarter than me.

My wife pointed out that its been unusually warm over the last few days and the water coming out of the hot tap was scorching. So she turned down the flame a bit in the boiler to sort it. Instantly the shower starts tormenting me, hmm.

## Systems
To control the temperature of the water the shower reduces the flow, which causes it to get hotter because its flowing through the boiler more slowly. This happens till the flow reaches the cutoff threshold and the gas turns off, the temperature drops.

When the temperature drops, the shower immediately lets through loads of water from the boiler that it thinks should be at a constant temperature. However, it’s now stone cold.

The water gradually warms up again until it gets squeezed off by the wax cylinder.

The whole thing starts again. The temperature of the water goes up and down making things very exciting for me.

Someone with a control systems background would be talking about the dangers of positive feedback this point I think. Its been some time since I went to (slept through) those lectures.

## The Moral Of The Story
This system was always broken, or at least on the edge of breaking, it just appeared to operate correctly. Both of the components were working exactly as specified. All it took was for an outside influence to change slightly and the whole things started to operate in a new way.

## So What?
No more plumbing from this point I promise.

Its becoming increasingly routine at the moment to create small services and connect them loosely together with message queues and direct calls.

Everything works fine in dev, test, UAT and Live until one day at 3am something changes…

## And I Do What About This?
When your trying to figure out why something is busted the first question to ask is what’s changed, bear in mind it might be some magic threshold has been passed and the system does a whole new thing.

Monitor everything, test everything a lot. It will still happen but hopefully not often.