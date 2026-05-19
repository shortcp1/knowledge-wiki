---
title: "Is It Really Impossible To Cool A Datacenter In Space?"
source: "https://www.youtube.com/watch?v=FlQYU3m1e80"
author:
  - "[[Scott Manley]]"
published: 2026-03-18
created: 2026-05-19
description: "Let's actually explain how thermal balance of spacecraft works, and how we'd need to configure a spacecraft to eliminated the heat that's produced by compute..."
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=FlQYU3m1e80)

## Transcript

**0:04** · Hello, it's Scott Manley here. People tell me that cooling data centers in space is easy because space is cold.

**0:13** · Other people say it's non impossible because in Earth we have conduction and convection to get rid of the heat. But in the vacuum of space, all you have is radiation. Now, this is one of those things that people seem to be arguing over repeatedly and I kind of wanted to just sit down and give you a rough idea of how you actually do the math so that we can know the real answer. There are all sorts of software packages out there that are designed for professionals or you know people that are actually designing spacecraft will have software to do all this.

**0:44** · They model the heat flow, the absorption, uh you know, the emission, and they are all very expensive pieces of software that are very accurate. But we're not going to do this because this had a lot of complexity that actually gets in the way of understanding the basic numbers.

**0:58** · Instead, I'm kind of going to aim to do this with like pen and paper. Actually, that's a really bad idea because my handwriting is terrible. So, I'll probably just like put equations on the screen and print the numbers up there.

**1:10** · But either way, you should be able to follow along. So to figure out the temperature of an object in space, you uh figure out how much energy is coming in, how much is being absorbed, and then given the surface area of the radiators, you then figure out how much heat those will emit at a given temperature. And you basically need to balance the incoming energy with the outgoing energy to get the temperature. Now, in real spacecraft, the geometry of all this is really important. But to get started, we're going to work with a very simplified model of a spacecraft. So let's start with the easy example.

**1:41** · I can imagine imagine you have a spacecraft that has a bunch of graphics cards on it, right? GPUs all over one side. Now, it doesn't really matter what the exact hardware that's on there because after all, by the time you watch this, it could well be out of date. Let's take a popular estimate of about 20 kW of power on a Starlink V3 satellite. So the spacecraft will be consuming 20 kowatts of electricity and it will be taking that in from the solar panels and converting that into heat and cat memes.

**2:16** · In the case of Starlink, a decent chunk of that energy is also coming out as radio waves. But if it's just a computer that is crunching numbers, all of that power ends up being converted into heat.

**2:27** · So now we've specified how much heat is coming in. That's 20 kow. Let's figure out the radiator sizes that are needed from first principles. Now, for those of you that haven't done physics, the amount of heat that is emitted by a surface is covered by the Stefan Boltzman law, which is stupidly simple.

**2:45** · It says the amount of energy emitted is proportional to the temperature raised to the fourth power multiplied by the Stefan Boltzman constant. Right? And this is physics. So temperature is of course measured relative to absolute zero in Kelvin or in ranking if you're weird. Uh so at room temperature of 20 Celsius or 68 Fahrenheit that's about 293 Kelvin and plugging that in with one square meter of surface it tells you that it emits about 420 watt blazing.

**3:16** · Right now increasing the temperature very quickly increases the power radiated. Doubling the temperature increases the radiated thermal energy by a factor of 16. Right? Double it, you get a factor of 16 increase. That's huge. There's another factor we need to include and that's the emissivity of the surface, right? How much it emits. And it's a simple num number between either zero and one which uh it defines how good the surface is at emitting black body radiation.

**3:42** · I mean, rough black surfaces tend to have high emissivities, while really perfectly smooth, shiny surfaces are bad at emitting heat and actually have low emissivities. Also, the number frequently changes with wavelength. So, things can be better at emitting heat in the infrared, not so good in the, you know, visible or vice versa. I'm largely going to ignore this initially and we'll add it in later. But you sort of need to know that this exists and I also need to make sure all the physicists out there aren't typing in comments telling me I forgot it.

**4:12** · So now imagine our Starlink satellite trying to get rid of 20 kow at room temperature. At 420 watts per square meter, it would need about 50 square meters. Now we can divide that by two because a thin flat spacecraft like Starlink has two sides 25 square meters for the entire satellite. So what is the surface area of the core of the Starlink satellite?

**4:38** · Well, we're looking at the V3 satellites and the only ones that we've actually seen tested are the dummy satellites that are deployed from Starship tests. And those look to be about 7 m wide on the rails with two per rack. So let's just say it's 7 m by 3 1/2 m. That's 24.5 m per side. And wow, I did not expect this to be so close.

**5:01** · Like I literally just put those numbers in and this is what I ended up with, right? But we have a lot of other things to account for, but ideal situation would be that we emit all the thermal radiation from the sat flat satellite bus without having to add any deployable radiators or anything around it. So now let's bump up the temperature increase the emission and in turn this lets us reduce the surface area that's required.

**5:25** · So now let's imagine that our radiators are operating at 80 Celsius right or 353 Kelvin and that is pretty hot for silicon chips but it is still doable right now. The radiated power uh at 80 Celsius is 880 watts per square meter.

**5:41** · That's more than twice what we got at room temperature. That's a huge advantage. And of course our required radiator is now 23 square meters. We only need half the satellite to cool it.

**5:50** · Uh and that of course also assumes that our emissivity is high, right? The emissivity is close to one. Now obviously having higher temperature radiators really helps a lot. But we can't just keep raising the temperature because the first law of thermodynamics tells us that heat only flows from hot to cold. So you have to imagine the coolant is flowing through the system past the servers and cooling them down and then it flows out to the radiator panels, right? And the that means the fluid has to be colder than the operating temperatures of your chips.

**6:22** · And similarly uh if you look at the space station, the radiators that cool down the crew segment could be smaller if they were allowed to run hotter. But the crew have a limit on the cabin temperatures where they are comfortable.

**6:33** · Right? Granted, you can actually have a heat pump that raises the temperature of the radiators above what the area you're cooling, but then you're expending energy to do this. Regardless, my point is that the radiator areas need to cool 20 kW of GPUs is smaller than the bus of a V3 Starlink satellite. But the problem isn't solved by any means. This is just a starting point to get everyone up to speed on the idea of thermal balance.

**7:00** · The satellite does not exist in a vacuum. Well, actually doesn't exist in a vacuum, but it doesn't exist in space without outside influences. We have to talk about the sun and the earth. There is a classic problem in astrophysics that we learn where you derive the temperature of an object based upon its distance from the sun. An object like say an asteroid or a planet or a spacecraft. What you do is you figure out how much heat it absorbs from the sun and then how hot it has to be to emit all that heat.

**7:26** · So if we imagine our object as a flat panel facing square onto the sun at the distance of the earth it gets hit by 1356 watts of thermal power per square meter. Now not all of that gets absorbed. Some of it will be reflected and scattered. And so there's a difference between a black rock and say a highly reflective mirror.

**7:48** · The ability to absorb light is the thermal absorptivity. Right? And so it's the counterpart to emissivity that I mentioned earlier. In fact, it's literally the twin. Uh, and for the same wavelength, it should actually take the same value. There's something called Kirchoff's law of thermal radiation, which says that the emissivity and the absorptivity are the same at any wavelength. Right? And this is a pretty cool and important result that actually cause it stops a lot of problems in thermodynamics.

**8:15** · But I need to point out that very recently there's some people using some very clever tricks with meta materials have demonstrated uh the ability to break this symmetry in very narrow wavelength w ranges and this is all very cool academic work but it's not going to change the landscape overnight.

**8:33** · So we are going to assume for now that uh the emission and absorption use exactly the same factor. So for a simple gray body with no variation in the emission or absorption with frequency, the absorptivity and the emissivity factors will actually cancel out for a body that is getting illuminated by the sun. And that means that our one square meter of surface exposed to 1356 watts of power needs to emit the same amount back out. And it needs to do that.

**9:01** · And to do that, it needs to be at a temperature of about 393 Kelvin or 120 Celsius, which is above the boiling point of water. This is roughly the temperature of the surface of the moon at midday with the sun high in the sky.

**9:16** · On the Earth, we don't see these temperatures being reached during the middle of the day because the surface transfers heat into the atmosphere, and that tends to keep the surface at a more reasonable temperature. How about a two-sided panel floating in space that has twice the surface area for emission?

**9:33** · In that case, the equilibrium temperature drops to 330 Kelvin or 57 Celsius because you've got twice the uh emitting area. And if you've got, say, a two-sided panel that's exposed to the sun, you can have different surface materials on each side. For example, you can have low absorption on the sunny side and high emission on the backside, and that will lower the temperature even further. Still, this is a kind of like trick that you will see spacecraft designers using to balance the thermals on their spacecraft.

**10:02** · Solar panels are, of course, an excellent example of a flat surface in space that has to be pointed at the sun.

**10:09** · And they have the added bonus of converting some of the power they absorb from the sun into electricity and sending that power elsewhere. So, the operating temperature of solar panels on spacecraft drops a bit lower than an idealized flat plane.

**10:24** · So, what about the panels that aren't directly face onto the sun? Well, how does that change? Right? What really matters is the cross-section that these panels offer to the incoming light. And for a point source, this varies with the angle. So, as the angle turns edge on, the amount of the cross-section drops off. And it's just like a sine wave that varies with the angle. So, with the sun at 90°, you get full power. At 45°, you only get 70% of the power. And if it's completely edge on, you shouldn't see anything.

**10:53** · Although the sun isn't a point source, and technically neither are your panels. The sun's about half a degrees across, so you'll always have some illumination there, even if the panel is perfectly edge on. Now, obviously, you don't want solar panels to do this, but you do want your radiators to do this because those are trying to emit heat and not absorb it from the sun. And that's why you tend to try to put your radiator panels edge onto the sun as much as possible. But when you're near the Earth, the sun isn't the only source of heating, right?

**11:24** · The Earth is reflecting sunlight back into space. And even at night, the Earth is emitting thermal radiation into space. That's why it gets so cold on a clear night. The exact amount of heat that is being emitted varies depending upon your location on the Earth and the weather.

**11:39** · But on average, it works out to about 200 watts per square meter at about 500 km. And it'll also change with altitude, getting lower as you get further away from the planet. And then there's the light reflected from the Earth, right?

**11:53** · And this varies a lot more depending upon the spacecraft's position. If it's in a low orbit at the subsolar point with the sun directly above and the Earth directly below them, then the reflected light could be as high as 450 watts per square meter. About onethird of the sunlight uh passing in comes back at you from the opposite side to heat you up.

**12:15** · So unlike the sun, you can't really treat the earth like a point source. So even turning edge onto the earth doesn't actually reduce the heating that much when you're in a very low orbit. And of course, Starlink satellites, their bus is actually required to face the planet below them and receive all this radiation because the antennas are on the bottom and they're supposed to point at the customers below them. So, let's put all this together, all these numbers to try to get the best and worstcase heating scenarios for a hypothetical data center in space.

**12:45** · We're just going to look at the core satellite bus since that's the part that people are arguing over. I mean, I think we can all agree here that solar panels do in fact work in space, right? Okay. So, we have 20 kW of power coming in and heating up that bus. Now, the sun is coming in and it's illuminating that satellite bus. And the amount of heat changes based upon the angle of illumination and the emissivity of the surface being illuminated. Uh the light from the earth will vary throughout the day.

**13:16** · But let's imagine that we are putting a data center into sun-synchronous orbit. That's the idea that started this whole thing. It's riding along the dayight terminator. The total illumination from the Earth is a combination of reflection and emission.

**13:31** · It'll be about 400 watts per square meter. There's a lot of potential variation here. I'm just using 400. It doesn't actually care that much about the angle of the spacecraft that it makes to the surface because the Earth covers such a large part of the sky in low Earth orbit. Now remember, our radiator is at 80 Celsius. We've just chosen that number because it seems reasonable. That will emit at 880 watts per square meter.

**13:55** · The best case scenario is that we have the satellite bus over the surface of the Earth and the sun is coming to the side. So we are is essentially orienting the satellite bus edge on to minimize the amount of solar illumination. So for now we will say that the solar illumination is zero and see how much margin we have. The earthsiding face of the satellite we're going to have 400 watts coming up right and we have 880 watts being radiated from both sides of the satellite.

**14:23** · So let's say we have go for a reasonably like emissive surface with an emissivity of about 08. It isn't that high. You can definitely do better, but 400 watts coming from the Earth over half of the satellite area, which is 24 1/2 square meters, is 8 kW of extra heat.

**14:38** · Add that into the 20 kW of electrical power being converted into heat and internet memes, of course, and we get 28 kW, which is significantly less than the 34 kW of heat the structure will emit if it's run at 80 C. In fact, we could happily drop the radiator temperature down to about 65 Celsius and it would still maintain thermal balance if we just were able to completely ignore the sun.

**15:08** · And I sort of feel that the sun is kind of important here and we shouldn't be ignoring it. But yeah, if we have six kilowatts of margin uh and we know the solar flux and we know the absorptivity of the satellite, we can figure out that the satellite has about a 10° dead zone where if it goes beyond 10°, it will start to absorb more than 6 kow of solar heating. So that's actually pretty good. We can keep the satellite in a good uh position and keep it like cool. But if we just keep the satellite bus edge onto the sun, you can go better.

**15:39** · You could actually just put a bunch of shades along one edge and actually shade the satellite reducing the heating a little more using very highly reflective surface along one side. So if you have a flat spacecraft similar to a Starlink going in sunsync orbit around the earth you and you can maintain the correct attitude using sun shades and reflectors and highly emissive radiator surface to handle the 20 kows of heat generated by all that computer hardware. You can do that fine as long as your computer hardware can handle 80 Celsius.

**16:08** · You can even drop the temperature a bit and lose some of that margin. And of course, if the solar panels move in the right way, the orientation could actually have you in a position where you're able to use your propulsion system without compromising the attitude, you know, for uh and messing up your cooling. Now, this is an extraordinarily highlevel analysis.

**16:28** · There's a lot of room for real world thermal engineering and analysis to understand this in more detail. What I'm really trying to show here is that it does not require ginormous radiators or some sci-fi level technology which hasn't been developed yet. This is showing that a Starlink satellite design is broadly in the right ballpark of viability for running computers. That's the best case scenario. What about the worst case scenario? Maybe there's good reasons why the satellite can't maintain edgeon attitude to the sun.

**16:58** · Well, if you absolutely have to face one side of the satellite to the sun, you can cover it in highly reflective insulation. That'll deflect or sorry, reflect about 95% of the incoming radiation. That means the sun's only going to add 1 to 2 kilowatt.

**17:14** · And really, it's only going to be about 1 kilowatt when you account for the heat being emitted. H this isn't too bad, but really what is bad is that you lose that entire side of the satellite as the radiator. So you lose half the radiator area and in turn that means you need to you need to add actual extra radiation area. You need to have a radiator that sticks out of the backside and adds a little bit of surface area but not a huge amount of surface area. It doesn't you know it's not uh it's not going to break your design at least in this power range. But how do you scale this up?

**17:46** · Right? 20 kow used to be enough to power a full rack of computer gear but we're seeing predictions now of 100 kilowatts per rack. And that's just one rack in a data center which might contain hundreds of racks of gear crunching numbers. The first renderings of space data centers showed masses solar arrays attached to a single hub with all the computers. But a year later, the more practical vision is individual satellites that communicate with each other to create a ginormous supercomput.

**18:14** · And as fast as these links are between satellites and different orbits, the light, the information is crossing hundreds of kilometers in space rather than a few meters off a satellite network. And that increases the latency of interprocess communication, which can slow the ability for these computers to collaborate on certain types of problems. So, you know, you're ending up optimizing for problems that can only be run on a single satellite. There is now an incentive to put as much hardware on a single satellite as possible.

**18:42** · So, how would you put a 100 kowatt rack in something like a Starlink satellite?

**18:49** · Well, obviously you need bigger panels, probably something like 400 square meters worth from a thermal point of view, there's now no longer enough surface area on a Starlink bus. So, you'd need to actually have it also deploy a radiator with about an extra 20 square meters of double-sided radiator, maybe for every 20 kW over that base 20 kW. Again, assuming about 80 Celsius.

**19:12** · And once you start getting into these large deployable radiators, you really need to start thinking a bit harder about how you move the heat out to those radiators. Solar panels can be built like ultralight wings because the only thing that they're moving around is electrons. But radiators, they need to move heat. And thermal conductivity is a lot slower than electrical conductivity.

**19:35** · Right? So we are moving hot fluids in pipes out to the radiators and we're bringing cooler fluids back in. Water can carry about 4.2 kJ per kilogram per degree C. So if you have a 20° temperature difference between going out to the radiators and coming back that needs about 1.2 kg of water per second or 70 L of water per minute to remove 100 kW of heat. And you know 70 L per minute is not actually that bad.

**20:03** · But the power required to move that amount of fluid really depends upon the geometry of the radiators and very specifically the geometry of the plumbing. There's like tradeoffs to be made where the narrower you make the pipes carrying the fluid. The more surface area they have to lose heat, but the narrower they are, the more viscosity is going to tend to slow your uh fluid down and they therefore mean that the pumps need more power. You absolutely need to factor in the power that's going to be required for these pumps.

**20:32** · You can spend a lot of energy pumping cooling fluid through really really tiny channels in a radiator fighting against that viscosity. But by using really tiny holes, you then in turn reduce the amount of fluid that actually needs to sit inside the radiators and cool down.

**20:49** · And that in turn reduces the overall satellite mass. So there's a lot of trades to be made if you're designing a cooling system. And to be clear, these kind of cooling systems are needed even if you're able to just use the surface of satellite for cooling. still need to be able to move the heat away from the CPU cores and to the surface of the satellite. But when you get to massive deployable radiators, you have to start thinking about the inertia of that fluid and how it interacts with the radiators that you're trying to make as lightweight as possible. And on Earth, we use water obviously, right?

**21:19** · That works very well because it's pretty easy and pretty available. But water is probably not the best fluid to be used in space if because in particular it can freeze and break pipes. The ISS uses ammonia and Russian spacecraft use glycol. Uh there's things like two-phase coolers where the coolant vaporizes at the hot side and then is recondensing.

**21:42** · Uh vaporization is actually really good because it's very energy intensive. So you can reduce your mass flow rates to much smaller numbers. These are all like optimizations to be made. But the most important optimization that a spacecraft designer can make appears to be raising the radiator temperature. And because that is closely related to the operating temperature of the hardware, that could give a big advantage to someone who can design their own custom silicon that operates at higher temperatures.

**22:08** · And Elon Musk has even talked about how getting chips that operate at 370 Kelvin or 97 C makes increasing the power density of data center satellites far more viable. And incidentally, we've been talking about flat satellites and of course anyone that's worked in a data center knows that there's like these racks, right? The 48U 19in rack which is, you know, big and it's just dense with computers. How does that fit into a flat satellite?

**22:37** · Well, it turns out that like 19in rack is about 50 cm wide. It's about 1 m deep per unit. And if you've got a 24 1/2 square meter satellite and you take all your one UU units and stack them out, it's actually roughly the same size. Now, this is obviously a really bad way to design a satellite, but I found the fact that the the, you know, the Starlink satellite idea that I was using was almost exactly the same volume as a 48U rack. Maybe I'm easily amused.

**23:09** · So, yeah, when I first saw the original StarCloud renderings and read their white paper, I knew that they were making a lot of simplifications that would complicate turning their design and vision into reality. And I pointed those out, right?

**23:22** · The vision of massive data centers in orbit faces all sorts of technical challenges. Cooling a five gawatt data center with giant radiators means pumping tons of cooling fluids around every second. Even if you come up with a suitable two-phase cooling solution, right? But now the swarm of AI servers is becoming the solution that people are actually pursuing. Not that the costs are going to work out anytime soon, but one day they might. And maybe we will see the first migration of commercial industrial hardware from the surface into space.

**23:54** · And maybe finally people will stop arguing over the ease of cooling computers and things in space and instead start arguing about the real problem of cooling nuclear reactors in space. I'm Scott Manley. Fly safe.