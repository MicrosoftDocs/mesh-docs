---
title: Microsoft.Mesh.Physics
description: Microsoft.Mesh.Physics allowlist for Visual Scripting in Mesh.
ms.service: mesh
author: vtieto
ms.author: vinnietieto
ms.date: 10/14/2024
ms.topic: reference
keywords: Microsoft Mesh, scripting, visual scripting, nodes, allowlist
---

# Microsoft\.Mesh\.Physics

## Scene

### AlignField


Supports additional properties and methods  from UnityEngine\.Behaviour,UnityEngine\.Component,andUnityEngine\.Object.

### BouncingSurface


Supports additional properties and methods from UnityEngine\.Behaviour,UnityEngine\.Component,andUnityEngine\.Object.

|Property|Type|Read?|Write?|Share?|
|----------|------|:-----:|:------:|:------:|
| BouncingSurface\|GetBounceEffect<br>BouncingSurface\|SetBounceEffect |BouncingSurface\.BounceEffect|yes|yes|no|
| BouncingSurface\|GetFriction<br>BouncingSurface\|SetFriction |float|yes|yes|yes|
| BouncingSurface\|GetRandomizeAngle<br>BouncingSurface\|SetRandomizeAngle |float|yes|yes|yes|
| BouncingSurface\|GetTargetBody<br>BouncingSurface\|SetTargetBody |GameObject|yes|yes|no|

### BuoyancyField


Supports additional properties and methods from UnityEngine\.Behaviour,UnityEngine\.Component,andUnityEngine\.Object.

|Property|Type|Read?|Write?|Share?|
|----------|------|:-----:|:------:|:------:|
| BuoyancyField\|GetBuoyancyHullPhysicMaterialName |string|yes|no|no|
| BuoyancyField\|GetDensity<br>BuoyancyField\|SetDensity |float|yes|yes|yes|
| BuoyancyField\|GetDrag<br>BuoyancyField\|SetDrag |float|yes|yes|yes|
| BuoyancyField\|GetPreventDrift<br>BuoyancyField\|SetPreventDrift |bool|yes|yes|yes|
| BuoyancyField\|GetSkinFriction<br>BuoyancyField\|SetSkinFriction |float|yes|yes|yes|
| BuoyancyField\|GetSurfaceType<br>BuoyancyField\|SetSurfaceType |SurfaceType|yes|yes|no|

### BuoyancyFieldWaves


Supports additional properties and methods from UnityEngine\.Behaviour,UnityEngine\.Component,andUnityEngine\.Object.

### Microsoft\.Mesh\.Physics\.CenterOfMassOffset


Supports additional properties and methods from UnityEngine\.Behaviour,UnityEngine\.Component,andUnityEngine\.Object.

|Property|Type|Read?|Write?|Share?|
|----------|------|:-----:|:------:|:------:|
| CenterOfMassOffset\|GetOffsetInLocalCoordinates<br>CenterOfMassOffset\|SetOffsetInLocalCoordinates |Vector3|yes|yes|yes|

### ContainmentField


Supports additional properties and methods from Behaviour,UnityEngine\.Component,and UnityEngine\.Object.

|Property|Type|Read?|Write?|Share?|
|----------|------|:-----:|:------:|:------:|
| ContainmentField\|GetMaxDeviationFromContainment<br>ContainmentField\|SetMaxDeviationFromContainment |float|yes|yes|yes|

### DirectionalExplosion


Supports additional properties and methods from UnityEngine\.Behaviour,UnityEngine\.Component,andUnityEngine\.Object.

|Property|Type|Read?|Write?|Share?|
|----------|------|:-----:|:------:|:------:|
| DirectionalExplosion\|GetAngularImpulseScale<br>DirectionalExplosion\|SetAngularImpulseScale |float|yes|yes|yes|
| DirectionalExplosion\|GetCriticalMass<br>DirectionalExplosion\|SetCriticalMass |float|yes|yes|yes|
| DirectionalExplosion\|GetDirection<br>DirectionalExplosion\|SetDirection |Vector3|yes|yes|yes|
| DirectionalExplosion\|GetDirectionInLocalSpace<br>DirectionalExplosion\|SetDirectionInLocalSpace |bool|yes|yes|yes|
| DirectionalExplosion\|GetStrength<br>DirectionalExplosion\|SetStrength |float|yes|yes|yes|

### JointStabilization

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.


|Property|Type|Read?|Write?|Share?|
|----------|------|:-----:|:------:|:------:|
| JointStabilization\|GetJointProjection<br>JointStabilization\|SetJointProjection |bool|yes|yes|yes|
| JointStabilization\|GetProjectionDistance<br>JointStabilization\|SetProjectionDistance |float|yes|yes|yes|
| JointStabilization\|GetStabilizationFactor<br>JointStabilization\|SetStabilizationFactor |float|yes|yes|yes|

### MagneticBody

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

|Property|Type|Read?|Write?|Share?|
|----------|------|:-----:|:------:|:------:|
| MagneticBody\|GetDisableGravityOnContact<br>MagneticBody\|SetDisableGravityOnContact |bool|yes|yes|yes|
| MagneticBody\|GetDistanceOfInfluence<br>MagneticBody\|SetDistanceOfInfluence |float|yes|yes|yes|
| MagneticBody\|GetFieldType<br>MagneticBody\|SetFieldType |FieldType|yes|yes|no|
| MagneticBody\|GetMagnetPole<br>MagneticBody\|SetMagnetPole |MagneticPole|yes|yes|no|
| MagneticBody\|GetStrength<br>MagneticBody\|SetStrength |float|yes|yes|yes|

### MaxAngularVelocity

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

### OrbitalGravityField

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.


|Property|Type|Read?|Write?|Share?|
|----------|------|:-----:|:------:|:------:|
| OrbitalGravityField\|GetDefaultForceRadius<br>OrbitalGravityField\|SetDefaultForceRadius |float|yes|yes|yes|
| OrbitalGravityField\|GetDisableGlobalGravity<br>OrbitalGravityField\|SetDisableGlobalGravity |bool|yes|yes|yes|
| OrbitalGravityField\|GetForceMoonsOnCircularOrbit<br>OrbitalGravityField\|SetForceMoonsOnCircularOrbit |bool|yes|yes|yes|
| OrbitalGravityField\|GetGravity<br>OrbitalGravityField\|SetGravity |float|yes|yes|yes|
| OrbitalGravityField\|GetSetForcedRadiusWhereDropped<br>OrbitalGravityField\|SetSetForcedRadiusWhereDropped |bool|yes|yes|yes|
| OrbitalGravityField\|GetSetForcedRadiusWherePlaced<br>OrbitalGravityField\|SetSetForcedRadiusWherePlaced |bool|yes|yes|yes|
| OrbitalGravityField\|GetStrengthOfForcedOrbit<br>OrbitalGravityField\|SetStrengthOfForcedOrbit |float|yes|yes|yes|

### PreventSleep


Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.


|Property|Type|Read?|Write?|Share?|
|----------|------|:-----:|:------:|:------:|
| PreventSleep\|GetTimeThreshold<br>PreventSleep\|SetTimeThreshold |float|yes|yes|yes|

### ResetBodyTransforms


Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.


|Property|Type|Read?|Write?|Share?|
|----------|------|:-----:|:------:|:------:|
| ResetBodyTransforms\|IsResetInProgress |bool|yes|no|no|

| Node | Inputs | Outputs | 
|--------|------------|---------|
| ResetBodyTransforms\|ResetBodyTransformsNow ||void|
| ResetBodyTransforms\|SaveBodyTransformsNow ||void|

### ScaledGravityField

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

|Property|Type|Read?|Write?|Share?|
|----------|------|:-----:|:------:|:------:|
| ScaledGravityField\|GetGravityScale<br>ScaledGravityField\|SetGravityScale |float|yes|yes|yes|

### SphericalExplosion


Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

|Property|Type|Read?|Write?|Share?|
|----------|------|:-----:|:------:|:------:|
| SphericalExplosion\|GetAngularImpulseScale<br>SphericalExplosion\|SetAngularImpulseScale |float|yes|yes|yes|
| SphericalExplosion\|GetCriticalMass<br>SphericalExplosion\|SetCriticalMass |float|yes|yes|yes|
| SphericalExplosion\|GetDistanceOfInfluence<br>SphericalExplosion\|SetDistanceOfInfluence |float|yes|yes|yes|
| SphericalExplosion\|GetFieldType<br>SphericalExplosion\|SetFieldType |ExplosionType|yes|yes|no|
| SphericalExplosion\|GetOcclusion<br>SphericalExplosion\|SetOcclusion |bool|yes|yes|yes|
| SphericalExplosion\|GetStrength<br>SphericalExplosion\|SetStrength |float|yes|yes|yes|

### StickyBody


Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

|Property|Type|Read?|Write?|Share?|
|----------|------|:-----:|:------:|:------:|
| StickyBody\|CanStickToDynamic |bool|yes|no|no|
| StickyBody\|CanStickToSpace |bool|yes|no|no|
| StickyBody\|CanStickToStatic |bool|yes|no|no|
| StickyBody\|GetCollisionControl |CollisionControlType|yes|no|no|
| StickyBody\|IsSticking |bool|yes|no|no|
| StickyBody\|GetStickingTo |Rigidbody|yes|no|no|
| StickyBody\|GetStickTo<br>StickyBody\|SetStickTo |BaseType|yes|yes|no|
| StickyBody\|GetWhen<br>StickyBody\|SetWhen |SettleType|yes|yes|no|

### ThrowTrajectory


Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

### VelocityDirectionField


Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

|Property|Type|Read?|Write?|Share?|
|----------|------|:-----:|:------:|:------:|
| VelocityDirectionField\|GetAccelerationType<br>VelocityDirectionField\|SetAccelerationType |AccelerationType|yes|yes|no|
| VelocityDirectionField\|GetDirectionInLocalSpace<br>VelocityDirectionField\|SetDirectionInLocalSpace |bool|yes|yes|yes|
| VelocityDirectionField\|GetFollowGameObject<br>VelocityDirectionField\|SetFollowGameObject |bool|yes|yes|yes|
| VelocityDirectionField\|GetMaxAcceleration<br>VelocityDirectionField\|SetMaxAcceleration |float|yes|yes|yes|
| VelocityDirectionField\|GetTargetBody<br>VelocityDirectionField\|SetTargetBody |GameObject|yes|yes|no|
| VelocityDirectionField\|GetTargetDirection<br>VelocityDirectionField\|SetTargetDirection |Vector3|yes|yes|yes|
| VelocityDirectionField\|GetVelocityType<br>VelocityDirectionField\|SetVelocityType |VelocityType|yes|yes|no|

### VelocityMagnitudeField


Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

|Property|Type|Read?|Write?|Share?|
|----------|------|:-----:|:------:|:------:|
| VelocityMagnitudeField\|GetAccelerationType<br>VelocityMagnitudeField\|SetAccelerationType |AccelerationType|yes|yes|no|float|void|
| VelocityMagnitudeField\|SetMinSpeed |`minSpeed`float|void|
| VelocityMagnitudeField\|SetTargetSpeed |`targetSpeed`float|void|

### VelocityVectorField


Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

|Property|Type|Read?|Write?|Share?|
|----------|------|:-----:|:------:|:------:|
| VelocityVectorField\|GetAccelerationType<br>VelocityVectorField\|SetAccelerationType |AccelerationType|yes|yes|no|
| VelocityVectorField\|GetDirectionInLocalSpace<br>VelocityVectorField\|SetDirectionInLocalSpace |bool|yes|yes|yes|
| VelocityVectorField\|GetMaxAcceleration<br>VelocityVectorField\|SetMaxAcceleration |float|yes|yes|yes|
| VelocityVectorField\|GetTargetVelocity<br>VelocityVectorField\|SetTargetVelocity |Vector3|yes|yes|yes|
| VelocityVectorField\|GetVelocityType<br>VelocityVectorField\|SetVelocityType |VelocityType|yes|yes|no|

## Enums

### BouncingSurface\.BounceEffect


Values are mutually exclusive\.
\(Underlyingtype:int)

|Enum|Value|
|------|------:|
|`PerfectBounce`|0
|`SetVelocityMagnitude`|1
|`SetNormalVelocity`|2
|`BounceTowardsTargetBody`|3
### BuoyancyField\.SurfaceType


Values are mutually exclusive\.
\(Underlyingtype:int)

|Enum|Value|
|------|------:|
|`StaticFlat`|0
|`DynamicFlat`|1
|`DynamicFlatPerBody`|2
### MagneticBody\.FieldType


Values are mutually exclusive\.
\(Underlyingtype:int)

|Enum|Value|
|------|------:|
|`Constant`|0
|`Linear`|1
|`Inverse`|2
|`InverseSquared`|3
### MagneticBody\.MagneticPole


Values are mutually exclusive\.
\(Underlyingtype:int)

|Enum|Value|
|------|------:|
|`NorthPole`|0
|`SouthPole`|1
|`Magnetic`|2
### SphericalExplosion\.ExplosionType


Values are mutually exclusive\.
\(Underlyingtype:int)

|Enum|Value|
|------|------:|
|`Constant`|0
|`LinearDrop`|1
### StickyBody\.BaseType


Values are mutually exclusive\.
\(Underlyingtype:int)

|Enum|Value|
|------|------:|
|`Space`|0
|`OnlyStatic`|1
|`OnlyDynamic`|2
|`StaticAndDynamic`|3
### StickyBody\.CollisionControlType


Values are mutually exclusive\.
\(Underlyingtype:int)

|Enum|Value|
|------|------:|
|`CollideNormally`|0
|`NoCollision`|1
|`NoCollisionWhenSticking`|2
### StickyBody\.SettleType


Values are mutually exclusive\.
\(Underlyingtype:int)

|Enum|Value|
|------|------:|
|`Touching`|0
|`Settled`|1
### VelocityDirectionField\.AccelerationType


Values are mutually exclusive\.
\(Underlyingtype:int)

|Enum|Value|
|------|------:|
|`Instantaneous`|0
|`ConstantAcceleration`|1
|`SmoothApproach`|2
### VelocityDirectionField\.VelocityType


Values are mutually exclusive\.
\(Underlyingtype:int)

|Enum|Value|
|------|------:|
|`LinearVelocity`|0
|`AngularVelocity`|1
### VelocityMagnitudeField\.AccelerationType


Values are mutually exclusive\.
\(Underlyingtype:int)

|Enum|Value|
|------|------:|
|`Instantaneous`|0
|`ConstantAcceleration`|1
|`SmoothApproach`|2
### VelocityMagnitudeField\.VelocityType


Values are mutually exclusive\.
\(Underlyingtype:int)

|Enum|Value|
|------|------:|
|`LinearVelocity`|0
|`AngularVelocity`|1
### VelocityVectorField\.AccelerationType


Values are mutually exclusive\.
\(Underlyingtype:int)

|Enum|Value|
|------|------:|
|`Instantaneous`|0
|`ConstantAcceleration`|1
|`SmoothApproach`|2
### VelocityVectorField\.VelocityType


Values are mutually exclusive\.
\(Underlyingtype:int)

|Enum|Value|
|------|------:|
|`LinearVelocity`|0
|`AngularVelocity`|1


