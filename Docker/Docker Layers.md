# Docker Layers Overview

Every command you execute results in a new layer that contains the changes compared to the previous layer
All previously built layers are cached and can be reused
Each layer is build upon the previous one, meaning that the whole chain needs to be stable
If a layer is modified, then its hash changes, which results in the other layers after it will have their hashes changed as well
