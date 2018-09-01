# Hacking in a World  of Perfect Encryption

*"We estimate that we can crack this faster by waiting a few years for computers to become faster and then starting the project on the new generation of machines."*

Cryptography is a complex thing. But an immutable fact of it is that if you are handed a set of data that has been scrambled by a non-repeating transformation of comparable size, that you *cannot* decipher it. Not "it's really hard to decipher" or "It'll take you a long time to decipher that" but that in fact you simply can't do it at all. So anyone with sufficient time on their hands and dedication to cryptographic secrecy *can* make a system that cannot be decrypted under any circumstances. It's called a one-time pad, and while resource intensive it is actually unbreakable. But people generally don't really *need* codes that can't be broken *ever*, most people will settle for codes that cannot be broken any time in the next hundred million years. That's the kind of time frame that even the extremely long lived are generally willing to concede that their secrets of today won't matter much once it has passed.

So while it is entirely within everyone's capacity to go out into the street, turn the microphone on super high and record random discordant noise for an hour, then download that hour into their drone as an exceedingly long cypher to get an hour of unbreakably encrypted communications between themselves and their drone, the vast majority of people are willing to accept a less intensive system where their communications are merely *unlikely* to be decrypted before the sun peters out.

Most secure communications use Essentially Unbreakable Encryption (EUE), a system where the sender and the intended recipient both have a cypher that is overlain on the messages and subsequently removed. The keys used in the 2070s are of variable length, but generally are thousands of bits long, and cannot be expected to be broken by any sort of mathematical attack. In order to attain such levels of security the cypher itself must have been shared at some earlier point between the intended sender and receiver, and it can of course be stolen either during the hand off or at any time that anyone has direct access to any of the computers which store the cypher itself. After all, EUE doesn't make the message completely illegible to anyone but the intended recipient; it makes the message completely unintelligible to anyone who doesn't have the key, which is *not* the same thing once espionage comes into the equation.

#### A Note on Cryptographic Realism

Real world cryptography and code breaking in the modern age revolves around incredibly intensive mathematical analysis and exploitations of technical weaknesses and user error. This is a fascinating field and incredibly non-photogenic. This means that it's the kind of thing that makes a very bad game, because it is almost impossible to describe the action in a way that is in any way comprehensible or cool. I mean basically it would largely come down to people rolling some kind of dice to determine if the security spiders or some non-security conscious user had made some bone headed mistake and then making more die rolls to see if the player could find that mistake and exploit it. You seriously might as well flip coins to see if you win or not, because nothing the player describes their actions as will make any difference to such a system.

In the interests of playability, the weaknesses of computers have been standardized. If you can project high density signal into a computer, you can manipulate it on the hardware level. And if you have access to both the plain text (or brain text) and the encrypted text version of a message you can break the code. Other weaknesses are assumed to not exist. This is admittedly and specifically an abstraction, but it makes the action *so much cooler looking* and the game so much more accessible to non-mathematicians that the sacrifice is well worth it.

## Vaguely Decent Protection: Asymmetric Encryption

*"The algorithms required to decrypt these things are illegal, so no one has them."*

Sending a message of any kind through EUE requires that both the sender and the receiver have a copy of the key. But what if you *don't* have a prearranged key, how can you communicate with any privacy? The answer is Asymmetric Encryption. Here's how it works: There are a set of mathematical transformations based on one number that are really hard to undo *unless* you happen to know a specific second number. So your Commcode gives out the first number to anyone who wants it, and then people can send transformed (and thus encrypted) data *to you* and since you have the magic second number you can reverse those changes very easily. 

You can also do this in the reverse order, transforming your message with the secret number and letting the receivers of the message decrypt it with the publicly available number. While this is a fairly useless way to keep information secret, it makes a fairly decent digital signature. Whoever sent the encrypted message must have known your personal secret number. This is the core of how every Access ID in the Matrix is verified.

#### A Note on Hacking: Spoofing an Access ID

The key weakness of Asymmetric Code is that by its very nature anyone who really wants to can have both plain text and encrypted text of their choice. Simply take plain text of your choice and encrypt it with the public key and you can spend some time doing "math" to decrypt it back out and have what is essentially the private key. Oh snap.

What this means is that the Access ID verification system of the Matrix at large is inherently weak. Anyone with the right hacker algorithms who observes the asymmetric key broadcasting of any device can back form an essentially identical key for their own use and then assign themselves the Access ID of that device.

## Passing Notes: Encryption, Reception, and Retransmission

*"The paper doesn't know what is written on it, but the scribe and the reader do."*

In Shadowrun, an encryption scheme can be undone if one has both the encrypted and the unencrypted version of the message. This means that if one compromises the computer on either terminal end of a message relay, that the code itself is compromised. However, merely listening to the encrypted transmission is essentially worthless. Indeed, any number of devices can be along the chain and be compromised without endangering the code in any way. Each computer can take the encrypted information and pass it on, still encrypted, without understanding or changing the data in any way. It is only when one gets to a computer that actually composes the encrypted data or is intended to put the data into brain text or other usable format that a hardware compromise gives away the show.

#### Equipment Spotlight: the Retransmitter

A retransmitter is a neat little device, it takes signal *in*, and then it pumps the same signal *out*. It can take signal in or out through wired or wireless channels depending upon how it has been set up (and thus can convert one type of signal to the other), and it can be set up in hardware to transmit in high density or low density signal. Of primary use for those who want to draw their signal LOS from a place that they are not literally at (possibly even a drone), but clever people have put these bad boys to all kinds of uses. Retransmitting low density signal through a wired interface across a Faraday cage is the basis of the account protections of Zürich Orbital, for example.

## Breaking Encryption: If You Can't Win, Cheat

*"Break the code? Nah, I just read the original over your shoulder."*

Over the probable length of time that any game of Shadowrun covers, it is unreasonable to suspect that you will ever see anyone brute force a node's EUE. It simply will not happen, and we aren't even going to bother having rules for it. However, that in no way means that you can't read someone's mail just because it is encoded in EUE. The truth is that for an EUE transmission to work at all, that the sender and all intended receivers must have a copy of the cypher. This creates two main weaknesses, which a hacker can exploit:

**The Physical Hardware:** High Density Signal can cause hardware to do pretty much anything as if it had gotten the correct user inputs to do whatever. This can include forking over the unencrypted versions of encrypted data or even giving out the codes directly if it has that information anywhere on the system in any format.

**The Initial Handoff:** The EUE cypher that any two nodes wish to use to communicate has to be initially generated on one device and transferred to the other. And while information transfer is very secure *after* the code has been shared, there's nothing in particular protecting the code transfer itself. This is where people do stuff like sneak around late at night in order to hand off their precious data chips hidden away in their shoes.

### Protecting Unencrypted Data: Using Your Inside Voice

*"You actually are the weakest link."*

No matter how sweet your encryption is, everyone's brain runs on pretty much the same codes. When each data packet is sent to a metahuman brain, that data is essentially unencrypted. Anyone who can "hear" that transmission can read it. Worse, if someone hears the transmission in brain text and they also had a recording of the encrypted version, they can make a Rosetta Stone to decrypt all the rest of your data, which makes all your base belong to them. So it is of no surprise that people in the 2070s attempt to make the actual communications between their brain and the rest of their network be as "quiet" as possible, which is why people use Datajacks, Internal Commlinks, and Trodes. The first two have a directly wired (and shielded) connection between themselves and the brain, while the last option is merely at very low signal strength and very close to the intended recipient. In any case, these methods of data transfer are very difficult to listen in to, and people generally feel relatively safe sending brain formatted information into their own heads by these means.

Now no data transfer mechanism is truly 100% safe: unscrupulous men *can* get microtransceivers  very close to your trode set and rebroadcast the precious unencrypted information to their own networks. They *can* compromise the physical hardware of the datajack or the trode net. And so it is that over and above having relatively secure direct neural interfaces, the truly security conscious will endeavor to conduct important communications from the sanctity of rooms that have been cleared of bugs and at special times and places that hopefully opposing spies won't know about. Cloak and dagger stuff that has been going on for literally thousands of years and shows no signs of stopping at any time in the future.
