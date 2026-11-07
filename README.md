# Troybin Dictionary by Tassio 

> Original website: https://troybindictionary.netlify.app

## Contents

- [Introduction](#introduction)
  - [What are troybins?](#what-are-troybins)
  - [What are bins?](#what-are-bins)
  - [Comparison of troybin and bin properties](#comparison-of-troybin-and-bin-properties)
  - [Comparison of troybin and bin format](#comparison-of-troybin-and-bin-format)
- [Useful tools](#useful-tools)
- [Property dictionary](#property-dictionary)

---

## Introduction

I created this site with the intention of leaving here everything I know about troybins.

I wrote all of this assuming you know how to handle Riot files and how particles work, so you better learn about Riot files first!

In this document, I am also going to show you how to translate it to the current particle format, ".bin".

### What are troybins?

Troybins are files where the code of some particle is written, identified by the ".troybin" extension; they were responsible for the visual effects work in the game and were also an old method used by Riot to organize and create VFX (visual effects).

Riot started to stop using troybins around season 7, its substitute was the bin files, which have been used ever since.

### What are bins?

Bins are compressed JSON files. Contains information about spells, skins, champion stats, and visual effects; bins are identified by the .bin extension.

The only differences between bin and troybin are the properties and format. Explaining in a simple way, bins are files that contain a bunch of troybins, like a folder, but its properties (what gives the particle color, gravity, size, etc.) are constructed in a different way.

### Comparison of troybin and bin properties

**Troybin size property:**

```ini
p-scale=115 115 0
```

**Bin size property:**

```text
birthScale0: embed = ValueVector3 {
    constantValue: vec3 = { 115, 115, 0 }
}
```

### Comparison of troybin and bin format

**Troybin format:**

```ini
[2Douterring] <-- Start of a particle code (below are its properties)
e-framerate=0
e-local-orient=0
e-rate=2
flag-disable-z=1
p-bindtoemitter=1.0 1.0
p-flexoffset=0.004999999888241291
p-life=1
p-linger=0
p-offset=0 15 0
p-quadrot=1 1 0
p-quadrotXP1=0 10
p-quadrotXP2=1 -10
p-scale=115 115 0
p-texture="Ryze_Base_P_shield_2D.dds"
p-uvscroll-no-alpha=1
p-xrgba=1.0 1.0 1.0 1.0
p-xrgba1=0 0 0.352941 0.529412 0
p-xrgba2=0.5 0.215686 0.556863 1 1
p-xrgba3=1 0.215686 0.407843 0.713725 0
pass=21
rendermode=4
//line break
[Another particle] <-- Ends after a line break and so the next particles start
```

**Bin format:**

```text
#PROP_text <-- Start of a bin
type: string = "PROP"
version: u32 = 2
linked: list[string] = {}
entries: map[hash,embed] = {
    "C:/ProgramData/TroybinConverter/troybin/Gangplank/Q/pirate_parley_cas" = VfxSystemDefinitionData { <-- Start of a particle
        particlePath: string = "C:/ProgramData/TroybinConverter/troybin/Gangplank/Q/pirate_parley_cas"
        particleName: string = "pirate_parley_cas"
    } <-- End of a particle
} <-- End of a bin
```

## Useful tools

There are some useful tools you can use to help you writing the code:

- **[Troygrade](https://leischii.github.io)** - Currently the most updated and effective troybin converter, by Leischii (it still has some bugs).
- **[Troybin converter](https://www.dropbox.com/scl/fi/c6kv999lixzfrf7a4lmx9/TroybinConverter.rar?rlkey=q5mi3jvu6ugcxel51qgwbjsra&dl=0)** - A forgotten project of moonshadow565, a troybin converter. (It is not 100% effective, however it is still useful to write a big part of the code.)

---

## Property dictionary

Each entry below shows a troybin property and its equivalent in the bin format.

**General:**
[ExcludeAttachmentType](#excludeattachmenttype) ·
[KeywordsExcluded](#keywordsexcluded) ·
[KeywordsRequired](#keywordsrequired) ·
[Particle-Acceleration](#particle-acceleration) ·
[Particle-Drag](#particle-drag) ·
[Particle-Velocity](#particle-velocity)

**Emitter (`e-`):**
[e-alpharef](#e-alpharef) ·
[e-censor-modulate](#e-censor-modulate) ·
[e-disabled](#e-disabled) ·
[e-framerate](#e-framerate) ·
[e-life](#e-life) ·
[e-linger](#e-linger) ·
[e-local-orient](#e-local-orient) ·
[e-period](#e-period) ·
[e-rate](#e-rate) ·
[e-tilesize](#e-tilesize) ·
[e-trail-cutoff](#e-trail-cutoff) ·
[e-trail-smoothing](#e-trail-smoothing) ·
[e-uvoffset](#e-uvoffset) ·
[e-uvoffset-mult](#e-uvoffset-mult) ·
[e-uvscroll](#e-uvscroll) ·
[e-uvscroll-mult](#e-uvscroll-mult)

**Particle (`p-`):**
[p-accel](#p-accel) ·
[p-backfaceon](#p-backfaceon) ·
[p-beammode](#p-beammode) ·
[p-bindtoemitter](#p-bindtoemitter) ·
[p-coloroffset](#p-coloroffset) ·
[p-colorscale](#p-colorscale) ·
[p-colortype](#p-colortype) ·
[p-distortion-mode](#p-distortion-mode) ·
[p-distortion-power](#p-distortion-power) ·
[p-drag](#p-drag) ·
[p-flexoffset](#p-flexoffset) ·
[p-flexscale](#p-flexscale) ·
[p-frameRate](#p-framerate) ·
[p-life](#p-life) ·
[p-linger](#p-linger) ·
[p-local-orient](#p-local-orient) ·
[p-mesh](#p-mesh) ·
[p-meshtex](#p-meshtex) ·
[p-numframes](#p-numframes) ·
[p-offset](#p-offset) ·
[p-postoffset](#p-postoffset) ·
[p-projection-fading](#p-projection-fading) ·
[p-projection-y-range](#p-projection-y-range) ·
[p-quadrot](#p-quadrot) ·
[p-randomstartframe](#p-randomstartframe) ·
[p-scalebias](#p-scalebias) ·
[p-shadow](#p-shadow) ·
[p-simpleorient](#p-simpleorient) ·
[p-startframe](#p-startframe) ·
[p-texdiv](#p-texdiv) ·
[p-texture](#p-texture) ·
[p-texture-mult](#p-texture-mult) ·
[p-uvmode](#p-uvmode) ·
[p-worldaccel](#p-worldaccel)

**Other:**
[pass](#pass) ·
[rendermode](#rendermode) ·
[single-particle](#single-particle) ·
[uniformscale](#uniformscale)

---

### ExcludeAttachmentType

**Troybin property:**

```ini
ExcludeAttachmentType="turret nexus inhibitor"
```

**Bin property:**

```text
excludedAttachmentTypes: list[string] = {
    "turret"
    "nexus"
    "inhibitor"
}
```

### KeywordsExcluded

**Troybin property:**

```ini
KeywordsExcluded="LeeSinSkin05"
```

**Bin property:**

```text
0xf50b1a41: pointer = 0xf4e37e07 {
    keywordsExcluded: list[string] = {
        "LeeSinSkin05"
    }
}
```

### KeywordsRequired

**Troybin property:**

```ini
KeywordsRequired="LeeSinSkin05"
```

**Bin property:**

```text
0xf50b1a41: pointer = 0xf4e37e07 {
    keywordsRequired: list[string] = {
        "LeeSinSkin05"
    }
}
```

### Particle-Acceleration

**Troybin property:**

```ini
Particle-Acceleration=-1000.0 0.0 -1000.0
```

**Bin property:**

```text
acceleration: embed = ValueVector3 {
    constantValue: vec3 = { -1000, 0, -1000 }
}
```

### Particle-Drag

**Troybin property:**

```ini
Particle-Drag=-1000.0 0.0 -1000.0
```

**Bin property:**

```text
drag: embed = ValueVector3 {
    constantValue: vec3 = { -1000, 0, -1000 }
}
```

### Particle-Velocity

**Troybin property:**

```ini
Particle-Velocity=-1000.0 0.0 -1000.0
```

**Bin property:**

```text
velocity: embed = ValueVector3 {
    constantValue: vec3 = { -1000, 0, -1000 }
}
```

### e-alpharef

**Troybin property:**

```ini
e-alpharef=20
```

**Bin property:**

```text
alphaRef: u8 = 20
```

### e-censor-modulate

**Troybin property:**

```ini
e-censor-modulate=0.0 1.0 1.0 1.0
```

**Bin property:**

```text
censorModulateValue: vec4 = { 0, 1, 1, 1 }
```

### e-disabled

**Troybin property:**

```ini
e-disabled=1
```

**Bin property:**

```text
disabled: bool = true
```

### e-framerate

**Troybin property:**

```ini
e-framerate=1.0
```

**Bin property:**

```text
birthFrameRate: embed = ValueFloat {
    constantValue: f32 = 1
}
```

### e-life

**Troybin property:**

```ini
e-life=1.0
```

**Bin property:**

```text
lifetime: option[f32] = {
    1
}
```

### e-linger

**Troybin property:**

```ini
e-linger=1.0
```

**Bin property:**

```text
emitterLinger: option[f32] = {
    0
}
```

### e-local-orient

**Troybin property:**

```ini
e-local-orient=0
```

**Bin property:**

```text
isLocalOrientation: flag = false
```

> **Obs:** The default value for this property is "true", so if the troybin property value is 1, you don't need to write it.

### e-period

**Troybin property:**

```ini
e-period=1.0
```

**Bin property:**

```text
emitterPeriod: option[f32] = {
    1
}
```

### e-rate

**Troybin property:**

```ini
e-rate=1.0
```

**Bin property:**

```text
rate: embed = ValueFloat {
    constantValue: f32 = 1
}
```

### e-tilesize

**Troybin property:**

```ini
e-tilesize=1000.0 0.0 0.0
```

**Bin property:**

```text
primitive: pointer = VfxPrimitiveCameraTrail {
    mTrail: embed = VfxTrailDefinitionData {
        mMode: u8 = 1
        mCutoff: f32 = 600
        mBirthTilingSize: embed = ValueVector3 {
            constantValue: vec3 = { 1000, 0, 0 }
        }
    }
}
```

### e-trail-cutoff

**Troybin property:**

```ini
e-trail-cutoff=600.0
```

**Bin property:**

```text
primitive: pointer = VfxPrimitiveCameraTrail {
    mTrail: embed = VfxTrailDefinitionData {
        mMode: u8 = 1
        mCutoff: f32 = 600
        mBirthTilingSize: embed = ValueVector3 {
            constantValue: vec3 = { 1000, 0, 0 }
        }
    }
}
```

### e-trail-smoothing

**Troybin property:**

```ini
e-trail-smoothing=2
```

**Bin property:**

```text
primitive: pointer = VfxPrimitiveCameraTrail {
    mTrail: embed = VfxTrailDefinitionData {
        mMode: u8 = 1
        mCutoff: f32 = 600
        mBirthTilingSize: embed = ValueVector3 {
            constantValue: vec3 = { 1000, 0, 0 }
        }
        mSmoothingMode: u8 = 2
    }
}
```

### e-uvoffset

**Troybin property:**

```ini
e-uvoffset=-2.0 0.0
```

**Bin property:**

```text
birthUVOffset: embed = ValueVector2 {
    constantValue: vec2 = { -2, 0 }
}
```

### e-uvoffset-mult

**Troybin property:**

```ini
e-uvoffset-mult=0.0 1.0
```

**Bin property:**

```text
birthUVOffsetMult: embed = ValueVector2 {
    constantValue: vec2 = { 0, 1 }
}
```

### e-uvscroll

**Troybin property:**

```ini
e-uvscroll=-2.0 0.0
```

**Bin property:**

```text
emitterUvScrollRate: vec2 = { -2, 0 }
```

### e-uvscroll-mult

**Troybin property:**

```ini
e-uvscroll-mult=0.0 1.0
```

**Bin property:**

```text
emitterUvScrollRateMult: vec2 = { 0, 1 }
```

### p-accel

**Troybin property:**

```ini
p-accel=-1800.0 0.0 -4000.0
```

**Bin property:**

```text
birthAcceleration: embed = ValueVector3 {
    constantValue: vec3 = { -1800, 0, -4000 }
}
```

### p-backfaceon

**Troybin property:**

```ini
p-backfaceon=1
```

**Bin property:**

```text
disableBackfaceCull: bool = true
```

> **Obs:** The default value for this property is "false", so if the troybin property value is 0, you don't need to write it.

### p-beammode

**Troybin property:**

```ini
p-beammode=1
```

**Bin property:**

```text
primitive: pointer = VfxPrimitiveBeam {
    mBeam: embed = VfxBeamDefinitionData {
        mMode: u8 = 1
    }
}
```

### p-bindtoemitter

**Troybin property:**

```ini
p-bindtoemitter=1.0 1.0
```

**Bin property:**

```text
//complexEmitterDefinitionData property
bindWeight: embed = ValueFloat {
    constantValue: f32 = 1
}

//simpleEmitterDefinitionData property
particleBind: vec2 = { 1, 1 }
```

### p-coloroffset

**Troybin property:**

```ini
p-coloroffset=0.0 0.2
```

**Bin property:**

```text
colorLookUpOffsets: vec2 = { 0, 0.200000003 }
```

### p-colorscale

**Troybin property:**

```ini
p-colorscale=0.7 1.0
```

**Bin property:**

```text
colorLookUpScales: vec2 = { 0.7, 1 }
```

### p-colortype

**Troybin property:**

```ini
p-colortype=0.0 1.0
```

**Bin property:**

```text
//In p-colortype the first value is X and the second one is Y.
colorLookUpTypeX: u8 = 0
colorLookUpTypeY: u8 = 1
```

### p-distortion-mode

**Troybin property:**

```ini
p-distortion-mode=2
```

**Bin property:**

```text
distortionDefinition: pointer = VfxDistortionDefinitionData {
    distortion: f32 = 0.035
    distortionMode: u8 = 2
    normalMapTexture: string = "path/texture.dds"
}
```

### p-distortion-power

**Troybin property:**

```ini
p-distortion-power=0.035
```

**Bin property:**

```text
distortionDefinition: pointer = VfxDistortionDefinitionData {
    distortion: f32 = 0.035
    distortionMode: u8 = 2
    normalMapTexture: string = "path/texture.dds"
}
```

### p-drag

**Troybin property:**

```ini
p-drag=8.0 8.0 8.0
```

**Bin property:**

```text
birthDrag: embed = ValueVector3 {
    constantValue: vec3 = { 8, 8, 8 }
}
```

### p-flexoffset

**Troybin property:**

```ini
p-flexoffset=8.0 8.0 8.0
```

**Bin property:**

```text
flexBirthTranslation: pointer = FlexTypeFloat {
    mValue: f32 = 0.005
}
```

### p-flexscale

**Troybin property:**

```ini
p-flexscale=0.005
```

**Bin property:**

```text
flexScaleBirthScale: pointer = FlexTypeFloat {
    mValue: f32 = 0.005
}
```

### p-frameRate

**Troybin property:**

```ini
p-frameRate=16
```

**Bin property:**

```text
frameRate: f32 = 16
```

### p-life

**Troybin property:**

```ini
p-life=3.0
```

**Bin property:**

```text
particleLifetime: embed = ValueFloat {
    constantValue: f32 = 3
}
```

### p-linger

**Troybin property:**

```ini
p-linger=1.0
```

**Bin property:**

```text
particleLinger: option[f32] = {
    1
}
```

### p-local-orient

**Troybin property:**

```ini
p-local-orient=1
```

**Bin property:**

```text
particleIsLocalOrientation: flag = true
```

> **Obs:** The default value for this property is "false", so if the troybin property value is 0, you don't need to write it.

### p-mesh

**Troybin property:**

```ini
p-mesh=mesh.SCB
```

**Bin property:**

```text
primitive: pointer = VfxPrimitiveMesh {
    mMesh: embed = VfxMeshDefinitionData {
        mSimpleMeshName: string = "path/mesh.SCB"
    }
}
```

### p-meshtex

**Troybin property:**

```ini
p-meshtex=texture.dds
```

**Bin property:**

```text
texture: string = "path/texture.dds"
```

### p-numframes

**Troybin property:**

```ini
p-numframes=4
```

**Bin property:**

```text
numFrames: u16 = 4
```

### p-offset

**Troybin property:**

```ini
p-offset=0.0 10.0 0.0
```

**Bin property:**

```text
shape: embed = VfxShape {
    emitOffset: embed = ValueVector3 {
        constantValue: vec3 = { 0, 10, 0 }
    }
}
```

### p-postoffset

**Troybin property:**

```ini
p-postoffset=0.0 10.0 0.0
```

**Bin property:**

```text
shape: embed = VfxShape {
    birthTranslation: embed = ValueVector3 {
        constantValue: vec3 = { 0, 10, 0 }
    }
}
```

### p-projection-fading

**Troybin property:**

```ini
p-projection-fading=100
```

**Bin property:**

```text
primitive: pointer = VfxPrimitivePlanarProjection {
    mProjection: embed = VfxProjectionDefinitionData {
        mYRange: f32 = 50
        mFading: f32 = 100
    }
}
```

### p-projection-y-range

**Troybin property:**

```ini
p-projection-y-range=50
```

**Bin property:**

```text
primitive: pointer = VfxPrimitivePlanarProjection {
    mProjection: embed = VfxProjectionDefinitionData {
        mYRange: f32 = 50
        mFading: f32 = 100
    }
}
```

### p-quadrot

**Troybin property:**

```ini
p-quadrot=90.0 0.0 0.0
```

**Bin property:**

```text
birthRotation0: embed = ValueVector3 {
    constantValue: vec3 = { 90, 0, 0 }
}
```

### p-randomstartframe

**Troybin property:**

```ini
p-randomstartframe=1
```

**Bin property:**

```text
isRandomStartFrame: flag = true
```

> **Obs:** The default value for this property is "false", so if the troybin property value is 0, you don't need to write it.

### p-scalebias

**Troybin property:**

```ini
p-scalebias=1.0 1.0
```

**Bin property:**

```text
scaleBias: vec2 = { 1, 1 }
```

### p-shadow

**Troybin property:**

```ini
p-shadow=1
```

**Bin property:**

```text
doesCastShadow: flag = true
```

> **Obs:** The default value for this property is "false", so if the troybin property value is 0, you don't need to write it.

### p-simpleorient

**Troybin property:**

```ini
p-simpleorient=1
```

**Bin property:**

```text
//Only works in simpleEmitterDefinitionData
0xbc022424: pointer = 0x7f70a2b2 {
    orientation: u8 = 1
}
```

### p-startframe

**Troybin property:**

```ini
p-startframe=4
```

**Bin property:**

```text
startFrame: u16 = 4
```

### p-texdiv

**Troybin property:**

```ini
p-texdiv=4.0 1.0
```

**Bin property:**

```text
texDiv: vec2 = { 4, 1 }
```

### p-texture

**Troybin property:**

```ini
p-texture=texture.dds
```

**Bin property:**

```text
texture: string = "path/texture.dds"
```

### p-texture-mult

**Troybin property:**

```ini
p-texture-mult=texture.dds
```

**Bin property:**

```text
textureMult: pointer = 0xb097c1bd {
    textureMult: string = "path/texture.dds"
}
```

### p-uvmode

**Troybin property:**

```ini
p-uvmode=2
```

**Bin property:**

```text
uvMode: u8 = 2
```

### p-worldaccel

**Troybin property:**

```ini
p-worldaccel=0.0 -800.0 0.0
```

**Bin property:**

```text
worldAcceleration: embed = IntegratedValueVector3 {
    constantValue: vec3 = { 0, -10, 0 }
    dynamics: pointer = VfxAnimatedVector3fVariableData {
        times: list[f32] = {
            0
        }
        values: list[vec3] = {
            { 0, -10, 0 }
        }
    }
}
```

### pass

**Troybin property:**

```ini
pass=60
```

**Bin property:**

```text
pass: i16 = 60
```

### rendermode

**Troybin property:**

```ini
rendermode=3
```

**Bin property:**

```text
blendMode: u8 = 3
```

### single-particle

**Troybin property:**

```ini
single-particle=1
```

**Bin property:**

```text
isSingleParticle: flag = true
```

> **Obs:** The default value for this property is "false", so if the troybin property value is 0, you don't need to write it.

### uniformscale

**Troybin property:**

```ini
uniformscale=1
```

**Bin property:**

```text
isUniformScale: flag = true
```

> **Obs:** The default value for this property is "false", so if the troybin property value is 0, you don't need to write it.
