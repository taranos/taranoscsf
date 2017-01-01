### Taranos CSF Component Licensing ###

The Taranos Cloud Sonification Framework is currently distributed as two main components:  [*Taranos Core*](https://github.com/taranos/taranoscsf-core) and [*Taranos Reference Server*](https://github.com/taranos/taranoscsf-refserver).  They are licensed separately.

Source code for the *Taranos Core* component is licensed under the terms of the open source [GNU Affero General Public License](https://www.gnu.org/licenses/agpl-3.0.en.html).  For distribution with a proprietary product or closed-source project a separate commercial license is required and available.  Furthermore, any modified version of the *Taranos Core* source code that is proprietary or closed-source may not facilitate remote network interaction with service users without a commercial license.

Source code for the *Taranos Reference Server* component is licensed for any purpose under the terms of the open source [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0).  Note that *Taranos Reference Server* is essentially a web API service wrapper for *Taranos Core*.  When used in combination both licenses are in effect.

The web APIs used to communicate with the *Taranos Reference Server*, on the other hand, are non-proprietary.  This means:

- You may freely develop alternative client implementations, proprietary or otherwise, which use the Taranos web APIs to communicate with Taranos or third-party Taranos-compatible server implementations.

- You may freely develop alternative server implementations, proprietary or otherwise, which use the Taranos web APIs to communicate with Taranos or third-party Taranos-compatible client implementations.

For additional information contact David Hinson, Netrogen Blue LLC (dhinson@netrogenblue.com)
