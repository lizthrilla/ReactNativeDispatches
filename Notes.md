# Notes

Based on experience building appes with React Native.

Dispatches from react native?

Not knowing native code and working around it

average weekly data: 41k users, 87k sessions, $79.6 million from 56.2k orders
**this works out to more than $4 billion annual revenue. apple confirmed this makes it one of the highest revenue generating apps in the world**


## Val

Val Geyvandov [10:09 AM]
id say dealing with gradle files was definitely a big pain, we had a lot of issues getting custom modules to register within the app due to config referencing


Liz Tiller [10:09 AM]
and the custom modules would be like the keyboard right?

Val Geyvandov [10:11 AM]
we didnt do that one for Android, we had issues registering Mixpanel for logging

Liz Tiller [10:11 AM]
ah yeah

Val Geyvandov [10:12 AM]
but in general, dealing with all the gradle build files was tedious
also, android is more sensitive to things like errant `null`s in the jsx
it would just blow up the app instead of ignoring issues like iOS would

Liz Tiller [10:13 AM]
yes that's it the `null`
i was like there's something I'm missing

Val Geyvandov [10:13 AM]
i also had issues with simulators being a bit wonky, and having to do soft resets on them pretty regularly due to weird behaviour

Liz Tiller [10:14 AM]
the format of the talk is based around how airbnb decided not to continue with react native and a lot of other companies have dropped react native for android but kept it for ios.  No one is talking about why though so I'm trying to give some reasons why it's a pain and how we pushed through some of it

Val Geyvandov [10:15 AM]
yeah, also, android has those global styles for certain native elements
and updating them means rummaging through xml configs

Liz Tiller [10:15 AM]
mm hmm

Val Geyvandov [10:15 AM]
thats a time consuming task
in our scenario, we used expo, and detached expo would constantly update their android project scaffolding
so we would have these complicated migrations
to update
also, android is just not as good at handling RN animations

Liz Tiller [10:16 AM]
no its not and it's way more specific UI wise
or that might be that our designers designed for ios lol

Val Geyvandov [10:16 AM]
hah yeah that may also be the case
but yeah, im trying to think if there is anything else

Liz Tiller [10:17 AM]
yeah i was told 20 minutes for the talk and now they are saying 30 and i'm like "for real?"
it's for google dev fest too so i need to be careful how i put all this lol

Val Geyvandov [10:18 AM]
hah, yeah, you may have to scour some message boards to see what other issues people are having

Liz Tiller [10:18 AM]
i submitted this talk during a big push to get the android build working again, but then we dropped it so I'm like "wait... what was it we were doing?" lol



## Luciano:

so I would mention the pros/cons on using Expo (ex CRNA -> `https://github.com/react-community/create-react-native-app` ) and put it in the shelve that belongs, a tool for quickly scafolding projects/demos, and I would encourge the use of `react-native init` or `expo eject` command when working production builds (edited) 

you can briefly present both tools (Expo vs react-native command line) and fill in those 10 minutes :smile: (edited) 

## Andrew

Andrew Scanlin [10:31 AM]
animation was wonky, from what I remember, and the layers of abstraction really broke. To get really snappy animations you’d have to really optimize it

that was early in the project so maybe there are better libraries or it’s been tightened up. In general it seemed like it was an ios-first project in general and for several plugins, so android implementation was either shoe-horned or non-existent. (edited) 

Liz Tiller [10:38 AM]
yeah

Andrew Scanlin [10:38 AM]
still easier than making two completely separate apps and trying to keep them consistent, but those were the times when I wished there wasn’t that RN layer and I could just program in java