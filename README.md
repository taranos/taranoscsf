# *Taranos:Cloud Sonification Framework (CSF)*

## What is it?
_Taranos:CSF_ is an experimental new information [sonification](https://en.wikipedia.org/wiki/Sonification) framework built from the ground up to combine two domain-specific data models - one for signal collection and processing (input) and the other for virtual sound field modeling and rendering (output) - all within a single and easily deployable microservice.  All framework features are accessible through well-defined web APIs enabling easy collaboration among diverse and widely-distributed signal provider and sonification rendering endpoints.

Think of it as a cloud-ready sandbox for information sonification sharing.

_Taranos:CSF_ currently features:

- An Akka-based domain modeling engine ([*Taranos Core*](https://github.com/taranos/taranoscsf-core)), hosted by...
- A minimal Play Framework-based microservice server ([*Taranos Reference Server*](https://github.com/taranos/taranoscsf-refserver)), providing access to...
- Unified services and data models for signal collection and processing and virtual sound field modeling and rendering, completely configurable by...
- A set of [Swagger-defined RESTful web APIs](https://github.com/taranos/taranoscsf-api) with an additional [Python "pseudo-API"](https://github.com/taranos/taranoscsf-papi) augmentation.
- All inspired by a vision of a future full of new and interesting shared-sonification experiences.

## What can I do with it?
_Taranos:CSF_ is designed to be a foundation for building custom, collaborative, and cloud-based information sonification experiences.  It is particularly useful for conveying sonified information that is:

- Positional - gauge proximity via loudness
- Directional - determine bearing via lobes of detection or multi-channel audio panning
- Stateful - understand status and behavior via waveform shape
- Scalar - judge magnitude via pitch
- Variable - monitor rate-of-change via pitch
- Cyclic - observe longer-term trends via periodicity

Or any combination of the above.

Possible applications include:

- Augment silent process monitoring or data center management tools with team-shareable sound capabilities for eyes-away monitoring.
- Extend a system's monitoring capabilities to mobile or other sound-capable portable devices.
- Sonify a website's visitor traffic and share with the world.
- Monitor an investment portfolio in real-time using ambient sound.
- Convert a stand-alone [auditory display](https://en.wikipedia.org/wiki/Auditory_display) into a networked auditory display.
- Create an artistic ecology of natural sounds driven by real-world events and data.
- Add a spatial sound information dimension to moddable games to give you and your teammates an unfair advantage.
- And much more!

All you have to supply are the signal providers that convert your source data into Taranos Signaling API calls.  For sound rendering you may use one of the project-supplied clients or provide your own.  Since the APIs are open and use RESTful HTTP requests, signal providers and alternative rendering clients can be easily implemented in practically any modern scripting or programming language and on a wide variety of networkable devices.

What does a _Taranos:CSF_ sonification sound like?  It's largely left to the imagination of the designer.  Here's a 2-minute [sample](http://netrogenblue.com/Sample1.mp3) of a real-time sonification of price movements of eight NYSE-listed shares captured by the author.  Each share was represented by a dedicated subject emitter spaced equally distant around a central probe and using a custom waveset.  Signaling data was provided by a Python script which used the Yahoo Finance API package to fetch the pricing data and feed it to a Taranos server using the Taranos Signaling API.  A custom Unity3D-based sound rendering client then fetched the waveform reports from the server using the Taranos Rendering API and performed them per the waveset configuration.

## How does it work?
At the highest level _Taranos:CSF_ simulates a sound pressure wavefield populated by virtual sound emitting objects called subjects and virtual sound detecting objects called probes.  Subject and probe objects are user-configurable and can be freely moved and oriented within the modeled wavefield as desired using the Rendering API.

Subjects are attached with emitters which are collections of virtual waveform-producing oscillators.  Emitters transform signals provided by the underlying signaling model into virtual power levels which are then channeled to oscillators to drive waveform emissions in user-defined ways. Any source of data can be used to produce an input signal using the Signaling API.

Probes convert waveforms within their ranges and lobes of detection into waveform quality reports which are then made available to physical sound rendering devices via the Rendering API.  Modeled waveform qualities include loudness, pitch, periodicity, shape and tone.  Any number of rendering devices may be associated with a given probe, enabling wide-area sonified information sharing.  Rendering devices then map the reported waveform qualities into audible sound performances according to their individual capabilities and end-user preferences.

The _Taranos:CSF_ data model is built with information confidentiality in mind.  An input signal is comprised of a single non-described scalar magnitude, completely decoupling  its meaning from its representation.  All externally-publishable model element keys are non-guessable by default, obscuring their meanings and discouraging snooping.  Furthermore, the signal collection model is isolated from the information rendering model by one-way association and independent sets of web API primitives, permitting public access to a user's signaling model by external signal providers without compromising the privacy of the higher level information interpretation elements.

## What can I *not* do with it?
_Taranos:CSF_ is currently distributed as two main components:  [*Taranos Core*](https://github.com/taranos/taranoscsf-core) and [*Taranos Reference Server*](https://github.com/taranos/taranoscsf-refserver).  They are licensed separately as open source for non-proprietary redistribution.  For proprietary redistribution of the *Taranos Core* component a commercial license is required.  See [Licensing](Licensing.md) for more details.  

## What is the project's current status? [January 2017]
The goal of the Taranos Project is to provide a cloud-friendly ecosystem of open source tools for sonification sharing.  _Taranos:CSF_ is intended to be a hub for a broad range of Taranos components and comprises the first phase of this effort.

The plan for the initial set of _Taranos:CSF_ deliverables and their current status can be found on the [Project Status](https://github.com/taranos/taranoscsf/wiki/Project-Status) wiki page.

## How do I get started?
Visit the [project wiki](https://github.com/taranos/taranoscsf/wiki) for helpful guides on building and using the framework and components.

