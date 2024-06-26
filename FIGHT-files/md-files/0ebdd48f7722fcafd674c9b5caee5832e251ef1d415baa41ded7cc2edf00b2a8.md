3/24/24, 10:24 AM Subscriber Proﬁle Identiﬁer Discovery: Intercept Home Network via SUCI | MITRE FiGHT™
https://ﬁght.mitre.org/techniques/FGT5019.001/ 1/4Home Techniques Intercept Home Network via SUCI
Subscriber Pro le Identi er
Discovery: Intercept Home
Network via SUCI
Summary
Pre-Conditions󰅂 󰅂
An adversary may intercept unencrypted radio transmissions
of a UE’s SUCI to identify the home network of the UE.
Adversary can tell what the home network of UE is from the
unencrypted portion of the Subscriber Concealed Identity
(SUCI), which is normally sent over the radio interface by a UE
seeking to connect. This can be of value to an adversary when
the home location is unusual.
Background information: In 5G, the UE’s permanent identity,
SUPI (Subscriber Permanent Identi er), includes a home
network identi er and a user-speci c identi er, and is never
sent unencrypted over the radio interface. Instead, a SUCI
(Subscriber Concealed Identi er) is sent when the UE goes
through initial registration to the serving network procedures;
this de-concealment operation can only be done by the UE’s
home network. However, the Home Network identi er part of
the SUCI is sent unencrypted, so that the serving network
knows where to get the information to authenticate this UE.
The home network may constitute sensitive information in
some special cases.This is a FiGHT
Subtechnique.
This is a theoretical behavior
ID: FGT5019.001
The following metadata
fields are relevant to the
behavior in context of 5G
systems.
Architecture segment: RAN
Platforms: 5G
Tactics: Discovery
Parent technique: FGT5019
Mitigation: FGM1505
Other subtechniques:
FGT5019.002,
FGT5019.003,
FGT5019.004,
FGT5019.005, FGT5019.006Matrix Data Sources Mitigations Tactics Techniques Resources󰍝󰇙
CONTACT US3/24/24, 10:24 AM Subscriber Proﬁle Identiﬁer Discovery: Intercept Home Network via SUCI | MITRE FiGHT™
https://ﬁght.mitre.org/techniques/FGT5019.001/ 2/4Post-Conditions
Implementation Examples
Critical AssetsName Description
Ability to receive SUCI over the
airAttacker requires
su cient signal to
noise and interference
ratio
Name Description
Target associationWhen home network is
unusual (e.g., US home
network in
Afghanistan), allows
attacker to identify UE
as target of interest for
geolocation,
degradation of service,
loss of tra c
con dentiality, or
physical attack.
Name Description
Intercept home network over the
radio interfaceReceive SUCI and
extract the  eld “home
network identi er”,
which is never
concealed.
Name Description
UE privacy Home network is
broadcast unconcealed
over the air perMatrix Data Sources Mitigations Tactics Techniques Resources󰍝󰇙
CONTACT US3/24/24, 10:24 AM Subscriber Proﬁle Identiﬁer Discovery: Intercept Home Network via SUCI | MITRE FiGHT™
https://ﬁght.mitre.org/techniques/FGT5019.001/ 3/4Mitigations
ReferencesName Description
standard. No attack on
assets is necessary.
ID Name Mitigates
FGM1505Proxy home
networkWhen the subscriber
a liation is re ected in
the home network
identi er (part of
subscriber identi er),
and would bene t from
not being sent in the
clear, the subscriber's
provider (home
network) should be a
proxy mobile network
operator - whose
identi er does not
reveal the true a liation
of the subscriber.
[1] 3GPP TS 23.003: "Numbering, Addressing and
Identi cation”, Version 17.6.0, Section 2.2B
Detections󰅀
Tactics󰅀
DiscoveryMatrix Data Sources Mitigations Tactics Techniques Resources󰍝󰇙
CONTACT US3/24/24, 10:24 AM Subscriber Proﬁle Identiﬁer Discovery: Intercept Home Network via SUCI | MITRE FiGHT™
https://ﬁght.mitre.org/techniques/FGT5019.001/ 4/4Parent Technique󰅀
Subscriber Pro le Identi er Discovery
Mitigation󰅀
Proxy home network
Other Subtechniques󰅀
Intercept bid-down SUPI
Obtain subscriber identi er via NF
Intercept unencrypted SUPI
Diameter signaling
Silent SMSMatrix Data Sources Mitigations Tactics Techniques Resources󰍝󰇙
CONTACT US