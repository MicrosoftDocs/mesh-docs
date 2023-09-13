---
title: Microsoft Mesh Physics
description: Microsoft Mesh Physics
author: typride
ms.author: vinnietieto
ms.date: 9/13/2023
ms.topic: Guide
keywords: Microsoft Mesh, physics, allowlist
---

# Microsoft Mesh Physics

## Scene

### Microsoft\.Mesh\.Physics\.BodyPairDistanceSensor

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`ReferencePoint`|Microsoft\.Mesh\.Physics\.BodyPairDistanceSensor\.ReferencePointType||yes|yes|no|Body Pair Distance Sensor \| Get Reference Point<br>Body Pair Distance Sensor \| Set Reference Point
|`ReferencePointOffset`|UnityEngine\.Vector3||yes|yes|yes|Body Pair Distance Sensor \| Get Reference Point Offset<br>Body Pair Distance Sensor \| Set Reference Point Offset
|`ReferenceRigidbody`|UnityEngine\.Rigidbody||yes|yes|no|Body Pair Distance Sensor \| Get Reference Rigidbody<br>Body Pair Distance Sensor \| Set Reference Rigidbody

### Microsoft\.Mesh\.Physics\.BouncingSurface

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`bounceEffect`|Microsoft\.Mesh\.Physics\.BouncingSurface\.BounceEffect||yes|yes|no|Bouncing Surface \| Get Bounce Effect<br>Bouncing Surface \| Set Bounce Effect
|`friction`|float||yes|yes|yes|Bouncing Surface \| Get Friction<br>Bouncing Surface \| Set Friction
|`randomizeAngle`|float||yes|yes|yes|Bouncing Surface \| Get Randomize Angle<br>Bouncing Surface \| Set Randomize Angle
|`targetBody`|UnityEngine\.GameObject||yes|yes|no|Bouncing Surface \| Get Target Body<br>Bouncing Surface \| Set Target Body

### Microsoft\.Mesh\.Physics\.BuoyancyField

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`BuoyancyHullPhysicMaterialName`|string||yes|no|no|Buoyancy Field \| Get Buoyancy Hull Physic Material Name
|`density`|float||yes|yes|yes|Buoyancy Field \| Get Density<br>Buoyancy Field \| Set Density
|`drag`|float||yes|yes|yes|Buoyancy Field \| Get Drag<br>Buoyancy Field \| Set Drag
|`preventDrift`|bool||yes|yes|yes|Buoyancy Field \| Get Prevent Drift<br>Buoyancy Field \| Set Prevent Drift
|`skinFriction`|float||yes|yes|yes|Buoyancy Field \| Get Skin Friction<br>Buoyancy Field \| Set Skin Friction
|`surfaceType`|Microsoft\.Mesh\.Physics\.BuoyancyField\.SurfaceType||yes|yes|no|Buoyancy Field \| Get Surface Type<br>Buoyancy Field \| Set Surface Type

### Microsoft\.Mesh\.Physics\.BuoyancyFieldWaves

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

### Microsoft\.Mesh\.Physics\.ButtonJoint

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`anchor`|UnityEngine\.Vector3||yes|no|no|Button Joint \| Get Anchor
|`autoConfigureConnectedAnchor`|bool||yes|no|no|Button Joint \| Get Auto Configure Connected Anchor
|`axis`|UnityEngine\.Vector3||yes|no|no|Button Joint \| Get Axis
|`connectedAnchor`|UnityEngine\.Vector3||yes|no|no|Button Joint \| Get Connected Anchor
|`connectedBody`|UnityEngine\.Rigidbody||yes|no|no|Button Joint \| Get Connected Body
|`damper`|float||yes|yes|yes|Button Joint \| Get Damper<br>Button Joint \| Set Damper
|`enableCollision`|bool||yes|yes|yes|Button Joint \| Get Enable Collision<br>Button Joint \| Set Enable Collision
|`maxLength`|float||yes|yes|yes|Button Joint \| Get Max Length<br>Button Joint \| Set Max Length
|`minLength`|float||yes|yes|yes|Button Joint \| Get Min Length<br>Button Joint \| Set Min Length
|`restLength`|float||yes|yes|yes|Button Joint \| Get Rest Length<br>Button Joint \| Set Rest Length
|`spring`|float||yes|yes|yes|Button Joint \| Get Spring<br>Button Joint \| Set Spring

### Microsoft\.Mesh\.Physics\.CenterOfMassOffset

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`OffsetInLocalCoordinates`|UnityEngine\.Vector3||yes|yes|yes|Center Of Mass Offset \| Get Offset In Local Coordinates<br>Center Of Mass Offset \| Set Offset In Local Coordinates

### Microsoft\.Mesh\.Physics\.CollisionEventsSensor

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

### Microsoft\.Mesh\.Physics\.ContainmentField

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`maxDeviationFromContainment`|float||yes|yes|yes|Containment Field \| Get Max Deviation From Containment<br>Containment Field \| Set Max Deviation From Containment

### Microsoft\.Mesh\.Physics\.DirectionalExplosion

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`angularImpulseScale`|float||yes|yes|yes|Directional Explosion \| Get Angular Impulse Scale<br>Directional Explosion \| Set Angular Impulse Scale
|`criticalMass`|float||yes|yes|yes|Directional Explosion \| Get Critical Mass<br>Directional Explosion \| Set Critical Mass
|`Direction`|UnityEngine\.Vector3||yes|yes|yes|Directional Explosion \| Get Direction<br>Directional Explosion \| Set Direction
|`directionInLocalSpace`|bool||yes|yes|yes|Directional Explosion \| Get Direction In Local Space<br>Directional Explosion \| Set Direction In Local Space
|`Strength`|float||yes|yes|yes|Directional Explosion \| Get Strength<br>Directional Explosion \| Set Strength

### Microsoft\.Mesh\.Physics\.JointStabilization

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`jointProjection`|bool||yes|yes|yes|Joint Stabilization \| Get Joint Projection<br>Joint Stabilization \| Set Joint Projection
|`projectionDistance`|float||yes|yes|yes|Joint Stabilization \| Get Projection Distance<br>Joint Stabilization \| Set Projection Distance
|`stabilizationFactor`|float||yes|yes|yes|Joint Stabilization \| Get Stabilization Factor<br>Joint Stabilization \| Set Stabilization Factor

### Microsoft\.Mesh\.Physics\.MagneticBody



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`disableGravityOnContact`|bool||yes|yes|yes|Magnetic Body \| Get Disable Gravity On Contact<br>Magnetic Body \| Set Disable Gravity On Contact
|`DistanceOfInfluence`|float||yes|yes|yes|Magnetic Body \| Get Distance Of Influence<br>Magnetic Body \| Set Distance Of Influence
|`fieldType`|Microsoft\.Mesh\.Physics\.MagneticBody\.FieldType||yes|yes|no|Magnetic Body \| Get Field Type<br>Magnetic Body \| Set Field Type
|`MagnetPole`|Microsoft\.Mesh\.Physics\.MagneticBody\.MagneticPole||yes|yes|no|Magnetic Body \| Get Magnet Pole<br>Magnetic Body \| Set Magnet Pole
|`Strength`|float||yes|yes|yes|Magnetic Body \| Get Strength<br>Magnetic Body \| Set Strength

### Microsoft\.Mesh\.Physics\.MaxAngularVelocity



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

### Microsoft\.Mesh\.Physics\.OrbitalGravityField



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`DefaultForceRadius`|float||yes|yes|yes|Orbital Gravity Field \| Get Default Force Radius<br>Orbital Gravity Field \| Set Default Force Radius
|`disableGlobalGravity`|bool||yes|yes|yes|Orbital Gravity Field \| Get Disable Global Gravity<br>Orbital Gravity Field \| Set Disable Global Gravity
|`forceMoonsOnCircularOrbit`|bool||yes|yes|yes|Orbital Gravity Field \| Get Force Moons On Circular Orbit<br>Orbital Gravity Field \| Set Force Moons On Circular Orbit
|`Gravity`|float||yes|yes|yes|Orbital Gravity Field \| Get Gravity<br>Orbital Gravity Field \| Set Gravity
|`setForcedRadiusWhereDropped`|bool||yes|yes|yes|Orbital Gravity Field \| Get Set Forced Radius Where Dropped<br>Orbital Gravity Field \| Set Set Forced Radius Where Dropped
|`setForcedRadiusWherePlaced`|bool||yes|yes|yes|Orbital Gravity Field \| Get Set Forced Radius Where Placed<br>Orbital Gravity Field \| Set Set Forced Radius Where Placed
|`strengthOfForcedOrbit`|float||yes|yes|yes|Orbital Gravity Field \| Get Strength Of Forced Orbit<br>Orbital Gravity Field \| Set Strength Of Forced Orbit

### Microsoft\.Mesh\.Physics\.PreventSleep



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`timeThreshold`|float||yes|yes|yes|Prevent Sleep \| Get Time Threshold<br>Prevent Sleep \| Set Time Threshold

### Microsoft\.Mesh\.Physics\.ResetBodyTransforms



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`IsResetInProgress`|bool||yes|no|no|Reset Body Transforms \| Is Reset In Progress

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`ResetBodyTransformsNow`||void||Reset Body Transforms \| Reset Body Transforms Now
|`SaveBodyTransformsNow`||void||Reset Body Transforms \| Save Body Transforms Now

### Microsoft\.Mesh\.Physics\.ScaledGravityField



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`GravityScale`|float||yes|yes|yes|Scaled Gravity Field \| Get Gravity Scale<br>Scaled Gravity Field \| Set Gravity Scale

### Microsoft\.Mesh\.Physics\.SphericalExplosion



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`angularImpulseScale`|float||yes|yes|yes|Spherical Explosion \| Get Angular Impulse Scale<br>Spherical Explosion \| Set Angular Impulse Scale
|`criticalMass`|float||yes|yes|yes|Spherical Explosion \| Get Critical Mass<br>Spherical Explosion \| Set Critical Mass
|`DistanceOfInfluence`|float||yes|yes|yes|Spherical Explosion \| Get Distance Of Influence<br>Spherical Explosion \| Set Distance Of Influence
|`fieldType`|Microsoft\.Mesh\.Physics\.SphericalExplosion\.ExplosionType||yes|yes|no|Spherical Explosion \| Get Field Type<br>Spherical Explosion \| Set Field Type
|`occlusion`|bool||yes|yes|yes|Spherical Explosion \| Get Occlusion<br>Spherical Explosion \| Set Occlusion
|`Strength`|float||yes|yes|yes|Spherical Explosion \| Get Strength<br>Spherical Explosion \| Set Strength

### Microsoft\.Mesh\.Physics\.StickyBody



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`CanStickToDynamic`|bool||yes|no|no|Sticky Body \| Can Stick To Dynamic
|`CanStickToSpace`|bool||yes|no|no|Sticky Body \| Can Stick To Space
|`CanStickToStatic`|bool||yes|no|no|Sticky Body \| Can Stick To Static
|`CollisionControl`|Microsoft\.Mesh\.Physics\.StickyBody\.CollisionControlType||yes|no|no|Sticky Body \| Get Collision Control
|`IsSticking`|bool||yes|no|no|Sticky Body \| Is Sticking
|`StickingTo`|UnityEngine\.Rigidbody||yes|no|no|Sticky Body \| Get Sticking To
|`StickTo`|Microsoft\.Mesh\.Physics\.StickyBody\.BaseType||yes|yes|no|Sticky Body \| Get Stick To<br>Sticky Body \| Set Stick To
|`When`|Microsoft\.Mesh\.Physics\.StickyBody\.SettleType||yes|yes|no|Sticky Body \| Get When<br>Sticky Body \| Set When

### Microsoft\.Mesh\.Physics\.TeleportBody



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`AngularVelocity`|UnityEngine\.Vector3||yes|yes|yes|Teleport Body \| Get Angular Velocity<br>Teleport Body \| Set Angular Velocity
|`Coordinates`|UnityEngine\.Vector3||yes|yes|yes|Teleport Body \| Get Coordinates<br>Teleport Body \| Set Coordinates
|`EulerAngles`|UnityEngine\.Vector3||yes|yes|yes|Teleport Body \| Get Euler Angles<br>Teleport Body \| Set Euler Angles
|`LinearVelocity`|UnityEngine\.Vector3||yes|yes|yes|Teleport Body \| Get Linear Velocity<br>Teleport Body \| Set Linear Velocity
|`localSpaceTransform`|UnityEngine\.Transform||yes|yes|no|Teleport Body \| Get Local Space Transform<br>Teleport Body \| Set Local Space Transform
|`randomizeRadius`|float||yes|yes|yes|Teleport Body \| Get Randomize Radius<br>Teleport Body \| Set Randomize Radius
|`respectLocalSpaceOrientation`|bool||yes|yes|yes|Teleport Body \| Get Respect Local Space Orientation<br>Teleport Body \| Set Respect Local Space Orientation
|`respectLocalSpaceScale`|bool||yes|yes|yes|Teleport Body \| Get Respect Local Space Scale<br>Teleport Body \| Set Respect Local Space Scale
|`setAngularVelocity`|bool||yes|yes|yes|Teleport Body \| Get Set Angular Velocity<br>Teleport Body \| Set Set Angular Velocity
|`setLinearVelocity`|bool||yes|yes|yes|Teleport Body \| Get Set Linear Velocity<br>Teleport Body \| Set Set Linear Velocity
|`setRotation`|bool||yes|yes|yes|Teleport Body \| Get Set Rotation<br>Teleport Body \| Set Set Rotation

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`Apply`||void||Teleport Body \| Apply

### Microsoft\.Mesh\.Physics\.ThrowableBody



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`ThrowVelocity`|float||yes|yes|yes|Throwable Body \| Get Throw Velocity<br>Throwable Body \| Set Throw Velocity

### Microsoft\.Mesh\.Physics\.TriggerEventsSensor



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

### Microsoft\.Mesh\.Physics\.VelocityDirectionField



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`accelerationType`|Microsoft\.Mesh\.Physics\.VelocityDirectionField\.AccelerationType||yes|yes|no|Velocity Direction Field \| Get Acceleration Type<br>Velocity Direction Field \| Set Acceleration Type
|`directionInLocalSpace`|bool||yes|yes|yes|Velocity Direction Field \| Get Direction In Local Space<br>Velocity Direction Field \| Set Direction In Local Space
|`followGameObject`|bool||yes|yes|yes|Velocity Direction Field \| Get Follow Game Object<br>Velocity Direction Field \| Set Follow Game Object
|`MaxAcceleration`|float||yes|yes|yes|Velocity Direction Field \| Get Max Acceleration<br>Velocity Direction Field \| Set Max Acceleration
|`targetBody`|UnityEngine\.GameObject||yes|yes|no|Velocity Direction Field \| Get Target Body<br>Velocity Direction Field \| Set Target Body
|`TargetDirection`|UnityEngine\.Vector3||yes|yes|yes|Velocity Direction Field \| Get Target Direction<br>Velocity Direction Field \| Set Target Direction
|`velocityType`|Microsoft\.Mesh\.Physics\.VelocityDirectionField\.VelocityType||yes|yes|no|Velocity Direction Field \| Get Velocity Type<br>Velocity Direction Field \| Set Velocity Type

### Microsoft\.Mesh\.Physics\.VelocityMagnitudeField



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`accelerationType`|Microsoft\.Mesh\.Physics\.VelocityMagnitudeField\.AccelerationType||yes|yes|no|Velocity Magnitude Field \| Get Acceleration Type<br>Velocity Magnitude Field \| Set Acceleration Type
|`MaxAcceleration`|float||yes|yes|yes|Velocity Magnitude Field \| Get Max Acceleration<br>Velocity Magnitude Field \| Set Max Acceleration
|`velocityType`|Microsoft\.Mesh\.Physics\.VelocityMagnitudeField\.VelocityType||yes|yes|no|Velocity Magnitude Field \| Get Velocity Type<br>Velocity Magnitude Field \| Set Velocity Type

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`setMaxSpeed`|`maxSpeed` float|void||Velocity Magnitude Field \| Set Max Speed
|`setMinSpeed`|`minSpeed` float|void||Velocity Magnitude Field \| Set Min Speed
|`setTargetSpeed`|`targetSpeed` float|void||Velocity Magnitude Field \| Set Target Speed

### Microsoft\.Mesh\.Physics\.VelocityVectorField



Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`accelerationType`|Microsoft\.Mesh\.Physics\.VelocityVectorField\.AccelerationType||yes|yes|no|Velocity Vector Field \| Get Acceleration Type<br>Velocity Vector Field \| Set Acceleration Type
|`directionInLocalSpace`|bool||yes|yes|yes|Velocity Vector Field \| Get Direction In Local Space<br>Velocity Vector Field \| Set Direction In Local Space
|`MaxAcceleration`|float||yes|yes|yes|Velocity Vector Field \| Get Max Acceleration<br>Velocity Vector Field \| Set Max Acceleration
|`TargetVelocity`|UnityEngine\.Vector3||yes|yes|yes|Velocity Vector Field \| Get Target Velocity<br>Velocity Vector Field \| Set Target Velocity
|`velocityType`|Microsoft\.Mesh\.Physics\.VelocityVectorField\.VelocityType||yes|yes|no|Velocity Vector Field \| Get Velocity Type<br>Velocity Vector Field \| Set Velocity Type

## Enums

### Microsoft\.Mesh\.Physics\.BodyPairDistanceSensor\.ReferencePointType



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`RigidbodyCenterOfMass`|0|
|`GameObjectPosition`|1|
### Microsoft\.Mesh\.Physics\.BouncingSurface\.BounceEffect



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`PerfectBounce`|0|
|`SetVelocityMagnitude`|1|
|`SetNormalVelocity`|2|
|`BounceTowardsTargetBody`|3|
### Microsoft\.Mesh\.Physics\.BuoyancyField\.SurfaceType



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`StaticFlat`|0|
|`DynamicFlat`|1|
|`DynamicFlatPerBody`|2|
### Microsoft\.Mesh\.Physics\.MagneticBody\.FieldType



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`Constant`|0|
|`Linear`|1|
|`Inverse`|2|
|`InverseSquared`|3|
### Microsoft\.Mesh\.Physics\.MagneticBody\.MagneticPole



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`NorthPole`|0|
|`SouthPole`|1|
|`Magnetic`|2|
### Microsoft\.Mesh\.Physics\.SphericalExplosion\.ExplosionType



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`Constant`|0|
|`LinearDrop`|1|
### Microsoft\.Mesh\.Physics\.StickyBody\.BaseType



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`Space`|0|
|`OnlyStatic`|1|
|`OnlyDynamic`|2|
|`StaticAndDynamic`|3|
### Microsoft\.Mesh\.Physics\.StickyBody\.CollisionControlType



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`CollideNormally`|0|
|`NoCollision`|1|
|`NoCollisionWhenSticking`|2|
### Microsoft\.Mesh\.Physics\.StickyBody\.SettleType



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`Touching`|0|
|`Settled`|1|
### Microsoft\.Mesh\.Physics\.VelocityDirectionField\.AccelerationType



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`Instantaneous`|0|
|`ConstantAcceleration`|1|
|`SmoothApproach`|2|
### Microsoft\.Mesh\.Physics\.VelocityDirectionField\.VelocityType



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`LinearVelocity`|0|
|`AngularVelocity`|1|
### Microsoft\.Mesh\.Physics\.VelocityMagnitudeField\.AccelerationType



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`Instantaneous`|0|
|`ConstantAcceleration`|1|
|`SmoothApproach`|2|
### Microsoft\.Mesh\.Physics\.VelocityMagnitudeField\.VelocityType



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`LinearVelocity`|0|
|`AngularVelocity`|1|
### Microsoft\.Mesh\.Physics\.VelocityVectorField\.AccelerationType



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`Instantaneous`|0|
|`ConstantAcceleration`|1|
|`SmoothApproach`|2|
### Microsoft\.Mesh\.Physics\.VelocityVectorField\.VelocityType



Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`LinearVelocity`|0|
|`AngularVelocity`|1|
