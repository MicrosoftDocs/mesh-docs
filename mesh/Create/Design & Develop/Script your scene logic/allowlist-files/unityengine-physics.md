---
title: UnityEngine Physics
description: UnityEngine Physics
author: typride
ms.author: vinnietieto
ms.date: 9/13/2023
ms.topic: Guide
keywords: Microsoft Mesh, UnityEngine Physics, allowlist, physics
---

# UnityEngine Physics

## Scene

### UnityEngine\.BoxCollider

A box\-shaped primitive collider\.

Supports additional properties and methods from UnityEngine\.Collider, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`center`|UnityEngine\.Vector3|The center of the box, measured in the object's local space\.|yes|yes|yes|Box Collider \| Get Center<br>Box Collider \| Set Center
|`size`|UnityEngine\.Vector3|The size of the box, measured in the object's local space\.|yes|yes|yes|Box Collider \| Get Size<br>Box Collider \| Set Size

### UnityEngine\.CapsuleCollider

A capsule\-shaped primitive collider\.

Supports additional properties and methods from UnityEngine\.Collider, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`center`|UnityEngine\.Vector3|The center of the capsule, measured in the object's local space\.|yes|yes|yes|Capsule Collider \| Get Center<br>Capsule Collider \| Set Center
|`direction`|int|The direction of the capsule\.|yes|yes|yes|Capsule Collider \| Get Direction<br>Capsule Collider \| Set Direction
|`height`|float|The height of the capsule measured in the object's local space\.|yes|yes|yes|Capsule Collider \| Get Height<br>Capsule Collider \| Set Height
|`radius`|float|The radius of the sphere, measured in the object's local space\.|yes|yes|yes|Capsule Collider \| Get Radius<br>Capsule Collider \| Set Radius

### UnityEngine\.CharacterJoint

Character Joints are mainly used for Ragdoll effects\.

Supports additional properties and methods from UnityEngine\.Joint, UnityEngine\.Component, and UnityEngine\.Object.

### UnityEngine\.Collider

A base class of all colliders\.

Supports additional properties and methods from UnityEngine\.Component and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`attachedRigidbody`|UnityEngine\.Rigidbody|The rigidbody the collider is attached to\.|yes|no|no|Collider \| Get Attached Rigidbody
|`bounds`|UnityEngine\.Bounds|The world space bounding volume of the collider \(Read Only\)\.|yes|no|no|Collider \| Get Bounds
|`enabled`|bool|Enabled Colliders will collide with other Colliders, disabled Colliders won't\.|yes|yes|yes|Collider \| Get Enabled<br>Collider \| Set Enabled
|`isTrigger`|bool|Specify if this collider is configured as a trigger\.|yes|no|no|Collider \| Is Trigger

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`ClosestPoint`|`position` UnityEngine\.Vector3|UnityEngine\.Vector3|Returns a point on the collider that is closest to a given location\.|Collider \| Closest Point
|`ClosestPointOnBounds`|`position` UnityEngine\.Vector3|UnityEngine\.Vector3|The closest point to the bounding box of the attached collider\.|Collider \| Closest Point On Bounds

### UnityEngine\.ConfigurableJoint

The configurable joint is an extremely flexible joint giving you complete control over rotation and linear motion\.

Supports additional properties and methods from UnityEngine\.Joint, UnityEngine\.Component, and UnityEngine\.Object.

### UnityEngine\.ConstantForce

A force applied constantly\.

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`force`|UnityEngine\.Vector3|The force applied to the rigidbody every frame\.|yes|yes|yes|Constant Force \| Get Force<br>Constant Force \| Set Force
|`relativeForce`|UnityEngine\.Vector3|The force \- relative to the rigid bodies coordinate system \- applied every frame\.|yes|yes|yes|Constant Force \| Get Relative Force<br>Constant Force \| Set Relative Force
|`relativeTorque`|UnityEngine\.Vector3|The torque \- relative to the rigid bodies coordinate system \- applied every frame\.|yes|yes|yes|Constant Force \| Get Relative Torque<br>Constant Force \| Set Relative Torque
|`torque`|UnityEngine\.Vector3|The torque applied to the rigidbody every frame\.|yes|yes|yes|Constant Force \| Get Torque<br>Constant Force \| Set Torque

### UnityEngine\.FixedJoint

The Fixed joint groups together 2 rigidbodies, making them stick together in their bound position\.

Supports additional properties and methods from UnityEngine\.Joint, UnityEngine\.Component, and UnityEngine\.Object.

### UnityEngine\.HingeJoint

The HingeJoint groups together 2 rigid bodies, constraining them to move like connected by a hinge\.

Supports additional properties and methods from UnityEngine\.Joint, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`angle`|float|The current angle in degrees of the joint relative to its rest position\. \(Read Only\)|yes|no|no|Hinge Joint \| Get Angle
|`limits`|UnityEngine\.JointLimits|Limit of angular rotation \(in degrees\) on the hinge joint\.|yes|yes|no|Hinge Joint \| Get Limits<br>Hinge Joint \| Set Limits
|`motor`|UnityEngine\.JointMotor|The motor will apply a force up to a maximum force to achieve the target velocity in degrees per second\.|yes|yes|no|Hinge Joint \| Get Motor<br>Hinge Joint \| Set Motor
|`spring`|UnityEngine\.JointSpring|The spring attempts to reach a target angle by adding spring and damping forces\.|yes|yes|no|Hinge Joint \| Get Spring<br>Hinge Joint \| Set Spring
|`useMotor`|bool|Enables the joint's motor\. Disabled by default\.|yes|yes|yes|Hinge Joint \| Get Use Motor<br>Hinge Joint \| Set Use Motor
|`useSpring`|bool|Enables the joint's spring\. Disabled by default\.|yes|yes|yes|Hinge Joint \| Get Use Spring<br>Hinge Joint \| Set Use Spring
|`velocity`|float|The angular velocity of the joint in degrees per second\. \(Read Only\)|yes|no|no|Hinge Joint \| Get Velocity

### UnityEngine\.Joint

Joint is the base class for all joints\.

Supports additional properties and methods from UnityEngine\.Component and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`anchor`|UnityEngine\.Vector3|The Position of the anchor around which the joints motion is constrained\.|yes|no|no|Joint \| Get Anchor
|`axis`|UnityEngine\.Vector3|The Direction of the axis around which the body is constrained\.|yes|no|no|Joint \| Get Axis
|`breakForce`|float|The force that needs to be applied for this joint to break\.|yes|yes|yes|Joint \| Get Break Force<br>Joint \| Set Break Force
|`breakTorque`|float|The torque that needs to be applied for this joint to break\. To be able to break, a joint must be \_Locked\_ or \_Limited\_ on the axis of rotation where the torque is being applied\. This means that some joints cannot break, such as an unconstrained Configurable Joint\.|yes|yes|yes|Joint \| Get Break Torque<br>Joint \| Set Break Torque
|`connectedAnchor`|UnityEngine\.Vector3|Position of the anchor relative to the connected Rigidbody\.|yes|no|no|Joint \| Get Connected Anchor
|`connectedBody`|UnityEngine\.Rigidbody|A reference to another rigidbody this joint connects to\.|yes|no|no|Joint \| Get Connected Body
|`currentForce`|UnityEngine\.Vector3|The force applied by the solver to satisfy all constraints\.|yes|no|no|Joint \| Get Current Force
|`currentTorque`|UnityEngine\.Vector3|The torque applied by the solver to satisfy all constraints\.|yes|no|no|Joint \| Get Current Torque

### UnityEngine\.MeshCollider

A mesh collider allows you to do between meshes and primitives\.

Supports additional properties and methods from UnityEngine\.Collider, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`convex`|bool|Use a convex collider from the mesh\.|yes|no|no|Mesh Collider \| Get Convex

### UnityEngine\.Rigidbody

Control of an object's position through physics simulation\.

Supports additional properties and methods from UnityEngine\.Component and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`angularDrag`|float|The angular drag of the object\.|yes|yes|yes|Rigidbody \| Get Angular Drag<br>Rigidbody \| Set Angular Drag
|`angularVelocity`|UnityEngine\.Vector3|The angular velocity vector of the rigidbody measured in radians per second\.|yes|yes|yes|Rigidbody \| Get Angular Velocity<br>Rigidbody \| Set Angular Velocity
|`centerOfMass`|UnityEngine\.Vector3|The center of mass relative to the transform's origin\.|yes|no|no|Rigidbody \| Get Center Of Mass
|`drag`|float|The drag of the object\.|yes|yes|yes|Rigidbody \| Get Drag<br>Rigidbody \| Set Drag
|`mass`|float|The mass of the rigidbody\.|yes|yes|yes|Rigidbody \| Get Mass<br>Rigidbody \| Set Mass
|`maxAngularVelocity`|float|The maximum angular velocity of the rigidbody measured in radians per second\. \(Default 7\) range \{ 0, infinity \}\.|yes|yes|yes|Rigidbody \| Get Max Angular Velocity<br>Rigidbody \| Set Max Angular Velocity
|`position`|UnityEngine\.Vector3|The position of the rigidbody\.|yes|yes|yes|Rigidbody \| Get Position<br>Rigidbody \| Set Position
|`rotation`|UnityEngine\.Quaternion|The rotation of the Rigidbody\.|yes|yes|yes|Rigidbody \| Get Rotation<br>Rigidbody \| Set Rotation
|`sleepThreshold`|float|The mass\-normalized energy threshold, below which objects start going to sleep\.|yes|yes|yes|Rigidbody \| Get Sleep Threshold<br>Rigidbody \| Set Sleep Threshold
|`useGravity`|bool|Controls whether gravity affects this rigidbody\.|yes|yes|yes|Rigidbody \| Get Use Gravity<br>Rigidbody \| Set Use Gravity
|`velocity`|UnityEngine\.Vector3|The velocity vector of the rigidbody\. It represents the rate of change of Rigidbody position\.|yes|yes|yes|Rigidbody \| Get Velocity<br>Rigidbody \| Set Velocity
|`worldCenterOfMass`|UnityEngine\.Vector3|The center of mass of the rigidbody in world space \(Read Only\)\.|yes|no|no|Rigidbody \| Get World Center Of Mass

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`AddExplosionForce`|`explosionForce` float<br>`explosionPosition` UnityEngine\.Vector3<br>`explosionRadius` float|void|Applies a force to a rigidbody that simulates explosion effects\.|Rigidbody \| Add Explosion Force
|`AddExplosionForce`|`explosionForce` float<br>`explosionPosition` UnityEngine\.Vector3<br>`explosionRadius` float<br>`upwardsModifier` float|void|Applies a force to a rigidbody that simulates explosion effects\.|Rigidbody \| Add Explosion Force
|`AddExplosionForce`|`explosionForce` float<br>`explosionPosition` UnityEngine\.Vector3<br>`explosionRadius` float<br>`upwardsModifier` float<br>`mode` UnityEngine\.ForceMode|void|Applies a force to a rigidbody that simulates explosion effects\.|Rigidbody \| Add Explosion Force
|`AddForce`|`x` float<br>`y` float<br>`z` float|void|Adds a force to the Rigidbody\.|Rigidbody \| Add Force
|`AddForce`|`x` float<br>`y` float<br>`z` float<br>`mode` UnityEngine\.ForceMode|void|Adds a force to the Rigidbody\.|Rigidbody \| Add Force
|`AddForce`|`force` UnityEngine\.Vector3|void|Adds a force to the Rigidbody\.|Rigidbody \| Add Force
|`AddForce`|`force` UnityEngine\.Vector3<br>`mode` UnityEngine\.ForceMode|void|Adds a force to the Rigidbody\.|Rigidbody \| Add Force
|`AddForceAtPosition`|`force` UnityEngine\.Vector3<br>`position` UnityEngine\.Vector3|void|Applies force at position\. As a result this will apply a torque and force on the object\.|Rigidbody \| Add Force At Position
|`AddForceAtPosition`|`force` UnityEngine\.Vector3<br>`position` UnityEngine\.Vector3<br>`mode` UnityEngine\.ForceMode|void|Applies force at position\. As a result this will apply a torque and force on the object\.|Rigidbody \| Add Force At Position
|`AddRelativeForce`|`x` float<br>`y` float<br>`z` float|void|Adds a force to the rigidbody relative to its coordinate system\.|Rigidbody \| Add Relative Force
|`AddRelativeForce`|`x` float<br>`y` float<br>`z` float<br>`mode` UnityEngine\.ForceMode|void|Adds a force to the rigidbody relative to its coordinate system\.|Rigidbody \| Add Relative Force
|`AddRelativeForce`|`force` UnityEngine\.Vector3|void|Adds a force to the rigidbody relative to its coordinate system\.|Rigidbody \| Add Relative Force
|`AddRelativeForce`|`force` UnityEngine\.Vector3<br>`mode` UnityEngine\.ForceMode|void|Adds a force to the rigidbody relative to its coordinate system\.|Rigidbody \| Add Relative Force
|`AddRelativeTorque`|`x` float<br>`y` float<br>`z` float|void|Adds a torque to the rigidbody relative to its coordinate system\.|Rigidbody \| Add Relative Torque
|`AddRelativeTorque`|`x` float<br>`y` float<br>`z` float<br>`mode` UnityEngine\.ForceMode|void|Adds a torque to the rigidbody relative to its coordinate system\.|Rigidbody \| Add Relative Torque
|`AddRelativeTorque`|`torque` UnityEngine\.Vector3|void|Adds a torque to the rigidbody relative to its coordinate system\.|Rigidbody \| Add Relative Torque
|`AddRelativeTorque`|`torque` UnityEngine\.Vector3<br>`mode` UnityEngine\.ForceMode|void|Adds a torque to the rigidbody relative to its coordinate system\.|Rigidbody \| Add Relative Torque
|`AddTorque`|`x` float<br>`y` float<br>`z` float|void|Adds a torque to the rigidbody\.|Rigidbody \| Add Torque
|`AddTorque`|`x` float<br>`y` float<br>`z` float<br>`mode` UnityEngine\.ForceMode|void|Adds a torque to the rigidbody\.|Rigidbody \| Add Torque
|`AddTorque`|`torque` UnityEngine\.Vector3|void|Adds a torque to the rigidbody\.|Rigidbody \| Add Torque
|`AddTorque`|`torque` UnityEngine\.Vector3<br>`mode` UnityEngine\.ForceMode|void|Adds a torque to the rigidbody\.|Rigidbody \| Add Torque
|`ClosestPointOnBounds`|`position` UnityEngine\.Vector3|UnityEngine\.Vector3|The closest point to the bounding box of the attached colliders\.|Rigidbody \| Closest Point On Bounds
|`GetPointVelocity`|`worldPoint` UnityEngine\.Vector3|UnityEngine\.Vector3|The velocity of the rigidbody at the point worldPoint in global space\.|Rigidbody \| Get Point Velocity
|`GetRelativePointVelocity`|`relativePoint` UnityEngine\.Vector3|UnityEngine\.Vector3|The velocity relative to the rigidbody at the point relativePoint\.|Rigidbody \| Get Relative Point Velocity
|`IsSleeping`||bool|Is the rigidbody sleeping?|Rigidbody \| Is Sleeping
|`MovePosition`|`position` UnityEngine\.Vector3|void|Moves the kinematic Rigidbody towards position\.|Rigidbody \| Move Position
|`MoveRotation`|`rot` UnityEngine\.Quaternion|void|Rotates the rigidbody to rotation\.|Rigidbody \| Move Rotation
|`ResetCenterOfMass`||void|Reset the center of mass of the rigidbody\.|Rigidbody \| Reset Center Of Mass

### UnityEngine\.SphereCollider

A sphere\-shaped primitive collider\.

Supports additional properties and methods from UnityEngine\.Collider, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`center`|UnityEngine\.Vector3|The center of the sphere in the object's local space\.|yes|yes|yes|Sphere Collider \| Get Center<br>Sphere Collider \| Set Center
|`radius`|float|The radius of the sphere measured in the object's local space\.|yes|yes|yes|Sphere Collider \| Get Radius<br>Sphere Collider \| Set Radius

### UnityEngine\.SpringJoint

The spring joint ties together 2 rigid bodies, spring forces will be automatically applied to keep the object at the given distance\.

Supports additional properties and methods from UnityEngine\.Joint, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`damper`|float|The damper force used to dampen the spring force\.|yes|yes|yes|Spring Joint \| Get Damper<br>Spring Joint \| Set Damper
|`maxDistance`|float|The maximum distance between the bodies relative to their initial distance\.|yes|yes|yes|Spring Joint \| Get Max Distance<br>Spring Joint \| Set Max Distance
|`minDistance`|float|The minimum distance between the bodies relative to their initial distance\.|yes|yes|yes|Spring Joint \| Get Min Distance<br>Spring Joint \| Set Min Distance
|`spring`|float|The spring force used to keep the two objects together\.|yes|yes|yes|Spring Joint \| Get Spring<br>Spring Joint \| Set Spring
|`tolerance`|float|The maximum allowed error between the current spring length and the length defined by minDistance and maxDistance\.|yes|yes|yes|Spring Joint \| Get Tolerance<br>Spring Joint \| Set Tolerance

## Structs

### UnityEngine\.ContactPoint

Describes a contact point where the collision occurs\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`normal`|UnityEngine\.Vector3|Normal of the contact point\.|yes|no|Contact Point \| Get Normal
|`otherCollider`|UnityEngine\.Collider|The other collider in contact at the point\.|yes|no|Contact Point \| Get Other Collider
|`point`|UnityEngine\.Vector3|The point of contact\.|yes|no|Contact Point \| Get Point
|`separation`|float|The distance between the colliders at the contact point\.|yes|no|Contact Point \| Get Separation
|`thisCollider`|UnityEngine\.Collider|The first collider in contact at the point\.|yes|no|Contact Point \| Get This Collider

### UnityEngine\.JointDrive

How the joint's movement will behave along its local X axis\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`maximumForce`|float|Amount of force applied to push the object toward the defined direction\.|yes|yes|Joint Drive \| Get Maximum Force<br>Joint Drive \| Set Maximum Force
|`positionDamper`|float|Resistance strength against the Position Spring\. Only used if mode includes Position\.|yes|yes|Joint Drive \| Get Position Damper<br>Joint Drive \| Set Position Damper
|`positionSpring`|float|Strength of a rubber\-band pull toward the defined direction\. Only used if mode includes Position\.|yes|yes|Joint Drive \| Get Position Spring<br>Joint Drive \| Set Position Spring

### UnityEngine\.JointLimits

JointLimits is used by the HingeJoint to limit the joints angle\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`bounceMinVelocity`|float|The minimum impact velocity which will cause the joint to bounce\.|yes|yes|Joint Limits \| Get Bounce Min Velocity<br>Joint Limits \| Set Bounce Min Velocity
|`bounciness`|float|Determines the size of the bounce when the joint hits it's limit\. Also known as restitution\.|yes|yes|Joint Limits \| Get Bounciness<br>Joint Limits \| Set Bounciness
|`contactDistance`|float|Distance inside the limit value at which the limit will be considered to be active by the solver\.|yes|yes|Joint Limits \| Get Contact Distance<br>Joint Limits \| Set Contact Distance
|`max`|float|The upper angular limit \(in degrees\) of the joint\.|yes|yes|Joint Limits \| Get Max<br>Joint Limits \| Set Max
|`min`|float|The lower angular limit \(in degrees\) of the joint\.|yes|yes|Joint Limits \| Get Min<br>Joint Limits \| Set Min

### UnityEngine\.JointMotor

The JointMotor is used to motorize a joint\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`force`|float|The motor will apply a force\.|yes|yes|Joint Motor \| Get Force<br>Joint Motor \| Set Force
|`freeSpin`|bool|If freeSpin is enabled the motor will only accelerate but never slow down\.|yes|yes|Joint Motor \| Get Free Spin<br>Joint Motor \| Set Free Spin
|`targetVelocity`|float|The motor will apply a force up to force to achieve targetVelocity\.|yes|yes|Joint Motor \| Get Target Velocity<br>Joint Motor \| Set Target Velocity

### UnityEngine\.JointSpring

JointSpring is used add a spring force to HingeJoint and PhysicMaterial\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`damper`|float|The damper force uses to dampen the spring\.|yes|yes|Joint Spring \| Get Damper<br>Joint Spring \| Set Damper
|`spring`|float|The spring forces used to reach the target position\.|yes|yes|Joint Spring \| Get Spring<br>Joint Spring \| Set Spring
|`targetPosition`|float|The target position the joint attempts to reach\.|yes|yes|Joint Spring \| Get Target Position<br>Joint Spring \| Set Target Position

### UnityEngine\.RaycastHit

Structure used to get information back from a raycast\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`barycentricCoordinate`|UnityEngine\.Vector3|The barycentric coordinate of the triangle we hit\.|yes|no|Raycast Hit \| Get Barycentric Coordinate
|`collider`|UnityEngine\.Collider|The Collider that was hit\.|yes|no|Raycast Hit \| Get Collider
|`colliderInstanceID`|int|Instance ID of the Collider that was hit\.|yes|no|Raycast Hit \| Get Collider Instance ID
|`distance`|float|The distance from the ray's origin to the impact point\.|yes|no|Raycast Hit \| Get Distance
|`lightmapCoord`|UnityEngine\.Vector2|The uv lightmap coordinate at the impact point\.|yes|no|Raycast Hit \| Get Lightmap Coord
|`normal`|UnityEngine\.Vector3|The normal of the surface the ray hit\.|yes|no|Raycast Hit \| Get Normal
|`point`|UnityEngine\.Vector3|The impact point in world space where the ray hit the collider\.|yes|no|Raycast Hit \| Get Point
|`rigidbody`|UnityEngine\.Rigidbody|The Rigidbody of the collider that was hit\. If the collider is not attached to a rigidbody then it is null\.|yes|no|Raycast Hit \| Get Rigidbody
|`textureCoord`|UnityEngine\.Vector2|The uv texture coordinate at the collision location\.|yes|no|Raycast Hit \| Get Texture Coord
|`textureCoord2`|UnityEngine\.Vector2|The secondary uv texture coordinate at the impact point\.|yes|no|Raycast Hit \| Get Texture Coord 2
|`transform`|UnityEngine\.Transform|The Transform of the rigidbody or collider that was hit\.|yes|no|Raycast Hit \| Get Transform
|`triangleIndex`|int|The index of the triangle that was hit\.|yes|no|Raycast Hit \| Get Triangle Index

### UnityEngine\.SoftJointLimit

The limits defined by the CharacterJoint\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`bounciness`|float|When the joint hits the limit, it can be made to bounce off it\.|yes|yes|Soft Joint Limit \| Get Bounciness<br>Soft Joint Limit \| Set Bounciness
|`contactDistance`|float|Determines how far ahead in space the solver can "see" the joint limit\.|yes|yes|Soft Joint Limit \| Get Contact Distance<br>Soft Joint Limit \| Set Contact Distance
|`limit`|float|The limit position/angle of the joint \(in degrees\)\.|yes|yes|Soft Joint Limit \| Get Limit<br>Soft Joint Limit \| Set Limit

### UnityEngine\.SoftJointLimitSpring

The configuration of the spring attached to the joint's limits: linear and angular\. Used by CharacterJoint and ConfigurableJoint\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`damper`|float|The damping of the spring limit\. In effect when the stiffness of the sprint limit is not zero\.|yes|yes|Soft Joint Limit Spring \| Get Damper<br>Soft Joint Limit Spring \| Set Damper
|`spring`|float|The stiffness of the spring limit\. When stiffness is zero the limit is hard, otherwise soft\.|yes|yes|Soft Joint Limit Spring \| Get Spring<br>Soft Joint Limit Spring \| Set Spring

## Other

### UnityEngine\.Physics

Global physics properties and helper methods\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`bounceThreshold`|float|Two colliding objects with a relative velocity below this will not bounce \(default 2\)\. Must be positive\.|yes|no|Physics \| Get Bounce Threshold
|`defaultContactOffset`|float|The default contact offset of the newly created colliders\.|yes|no|Physics \| Get Default Contact Offset
|`defaultMaxAngularSpeed`|float|Default maximum angular speed of the dynamic Rigidbody, in radians \(default 50\)\.|yes|no|Physics \| Get Default Max Angular Speed
|`defaultMaxDepenetrationVelocity`|float|The maximum default velocity needed to move a Rigidbody's collider out of another collider's surface penetration\. Must be positive\.|yes|no|Physics \| Get Default Max Depenetration Velocity
|`gravity`|UnityEngine\.Vector3|The gravity applied to all rigid bodies in the Scene\.|yes|no|Physics \| Get Gravity
|`sleepThreshold`|float|The mass\-normalized energy threshold, below which objects start going to sleep\.|yes|no|Physics \| Get Sleep Threshold

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`BoxCast`|`center` UnityEngine\.Vector3<br>`halfExtents` UnityEngine\.Vector3<br>`direction` UnityEngine\.Vector3|bool||Physics \| Box Cast
|`BoxCast`|`center` UnityEngine\.Vector3<br>`halfExtents` UnityEngine\.Vector3<br>`direction` UnityEngine\.Vector3<br>`orientation` UnityEngine\.Quaternion|bool||Physics \| Box Cast
|`BoxCast`|`center` UnityEngine\.Vector3<br>`halfExtents` UnityEngine\.Vector3<br>`direction` UnityEngine\.Vector3<br>`orientation` UnityEngine\.Quaternion<br>`maxDistance` float|bool||Physics \| Box Cast
|`BoxCast`|`center` UnityEngine\.Vector3<br>`halfExtents` UnityEngine\.Vector3<br>`direction` UnityEngine\.Vector3<br>`orientation` UnityEngine\.Quaternion<br>`maxDistance` float<br>`layerMask` int|bool||Physics \| Box Cast
|`BoxCast`|`center` UnityEngine\.Vector3<br>`halfExtents` UnityEngine\.Vector3<br>`direction` UnityEngine\.Vector3<br>`orientation` UnityEngine\.Quaternion<br>`maxDistance` float<br>`layerMask` int<br>`queryTriggerInteraction` UnityEngine\.QueryTriggerInteraction|bool|Casts the box along a ray and returns detailed information on what was hit\.|Physics \| Box Cast
|`CapsuleCast`|`point1` UnityEngine\.Vector3<br>`point2` UnityEngine\.Vector3<br>`radius` float<br>`direction` UnityEngine\.Vector3|bool||Physics \| Capsule Cast
|`CapsuleCast`|`point1` UnityEngine\.Vector3<br>`point2` UnityEngine\.Vector3<br>`radius` float<br>`direction` UnityEngine\.Vector3<br>`maxDistance` float|bool||Physics \| Capsule Cast
|`CapsuleCast`|`point1` UnityEngine\.Vector3<br>`point2` UnityEngine\.Vector3<br>`radius` float<br>`direction` UnityEngine\.Vector3<br>`maxDistance` float<br>`layerMask` int|bool||Physics \| Capsule Cast
|`CapsuleCast`|`point1` UnityEngine\.Vector3<br>`point2` UnityEngine\.Vector3<br>`radius` float<br>`direction` UnityEngine\.Vector3<br>`maxDistance` float<br>`layerMask` int<br>`queryTriggerInteraction` UnityEngine\.QueryTriggerInteraction|bool|Casts a capsule against all colliders in the Scene and returns detailed information on what was hit\.|Physics \| Capsule Cast
|`CheckBox`|`center` UnityEngine\.Vector3<br>`halfExtents` UnityEngine\.Vector3|bool||Physics \| Check Box
|`CheckBox`|`center` UnityEngine\.Vector3<br>`halfExtents` UnityEngine\.Vector3<br>`orientation` UnityEngine\.Quaternion|bool||Physics \| Check Box
|`CheckBox`|`center` UnityEngine\.Vector3<br>`halfExtents` UnityEngine\.Vector3<br>`orientation` UnityEngine\.Quaternion<br>`layerMask` int|bool||Physics \| Check Box
|`CheckBox`|`center` UnityEngine\.Vector3<br>`halfExtents` UnityEngine\.Vector3<br>`orientation` UnityEngine\.Quaternion<br>`layermask` int<br>`queryTriggerInteraction` UnityEngine\.QueryTriggerInteraction|bool|Check whether the given box overlaps with other colliders or not\.|Physics \| Check Box
|`CheckCapsule`|`start` UnityEngine\.Vector3<br>`end` UnityEngine\.Vector3<br>`radius` float|bool||Physics \| Check Capsule
|`CheckCapsule`|`start` UnityEngine\.Vector3<br>`end` UnityEngine\.Vector3<br>`radius` float<br>`layerMask` int|bool||Physics \| Check Capsule
|`CheckCapsule`|`start` UnityEngine\.Vector3<br>`end` UnityEngine\.Vector3<br>`radius` float<br>`layerMask` int<br>`queryTriggerInteraction` UnityEngine\.QueryTriggerInteraction|bool|Checks if any colliders overlap a capsule\-shaped volume in world space\.|Physics \| Check Capsule
|`CheckSphere`|`position` UnityEngine\.Vector3<br>`radius` float|bool||Physics \| Check Sphere
|`CheckSphere`|`position` UnityEngine\.Vector3<br>`radius` float<br>`layerMask` int|bool||Physics \| Check Sphere
|`CheckSphere`|`position` UnityEngine\.Vector3<br>`radius` float<br>`layerMask` int<br>`queryTriggerInteraction` UnityEngine\.QueryTriggerInteraction|bool|Returns true if there are any colliders overlapping the sphere defined by position and radius in world coordinates\.|Physics \| Check Sphere
|`ClosestPoint`|`point` UnityEngine\.Vector3<br>`collider` UnityEngine\.Collider<br>`position` UnityEngine\.Vector3<br>`rotation` UnityEngine\.Quaternion|UnityEngine\.Vector3|Returns a point on the given collider that is closest to the specified location\.|Physics \| Closest Point
|`GetIgnoreCollision`|`collider1` UnityEngine\.Collider<br>`collider2` UnityEngine\.Collider|bool|Checks whether the collision detection system will ignore all collisionstriggers between collider1 and collider2/ or not\.|Physics \| Get Ignore Collision
|`IgnoreCollision`|`collider1` UnityEngine\.Collider<br>`collider2` UnityEngine\.Collider|void||Physics \| Ignore Collision
|`IgnoreCollision`|`collider1` UnityEngine\.Collider<br>`collider2` UnityEngine\.Collider<br>`ignore` bool|void|Makes the collision detection system ignore all collisions between collider1 and collider2\.|Physics \| Ignore Collision
|`Linecast`|`start` UnityEngine\.Vector3<br>`end` UnityEngine\.Vector3|bool||Physics \| Linecast
|`Linecast`|`start` UnityEngine\.Vector3<br>`end` UnityEngine\.Vector3<br>`layerMask` int|bool||Physics \| Linecast
|`Linecast`|`start` UnityEngine\.Vector3<br>`end` UnityEngine\.Vector3<br>`layerMask` int<br>`queryTriggerInteraction` UnityEngine\.QueryTriggerInteraction|bool|Returns true if there is any collider intersecting the line between start and end\.|Physics \| Linecast
|`Raycast`|`ray` UnityEngine\.Ray|bool||Physics \| Raycast
|`Raycast`|`ray` UnityEngine\.Ray<br>`maxDistance` float|bool||Physics \| Raycast
|`Raycast`|`ray` UnityEngine\.Ray<br>`maxDistance` float<br>`layerMask` int|bool||Physics \| Raycast
|`Raycast`|`ray` UnityEngine\.Ray<br>`maxDistance` float<br>`layerMask` int<br>`queryTriggerInteraction` UnityEngine\.QueryTriggerInteraction|bool|Same as above using ray\.origin and ray\.direction instead of origin and direction\.|Physics \| Raycast
|`Raycast`|`origin` UnityEngine\.Vector3<br>`direction` UnityEngine\.Vector3|bool||Physics \| Raycast
|`Raycast`|`origin` UnityEngine\.Vector3<br>`direction` UnityEngine\.Vector3<br>`maxDistance` float|bool||Physics \| Raycast
|`Raycast`|`origin` UnityEngine\.Vector3<br>`direction` UnityEngine\.Vector3<br>`maxDistance` float<br>`layerMask` int|bool||Physics \| Raycast
|`Raycast`|`origin` UnityEngine\.Vector3<br>`direction` UnityEngine\.Vector3<br>`maxDistance` float<br>`layerMask` int<br>`queryTriggerInteraction` UnityEngine\.QueryTriggerInteraction|bool|Casts a ray, from point origin, in direction direction, of length maxDistance, against all colliders in the Scene\.|Physics \| Raycast
|`SphereCast`|`ray` UnityEngine\.Ray<br>`radius` float|bool||Physics \| Sphere Cast
|`SphereCast`|`ray` UnityEngine\.Ray<br>`radius` float<br>`maxDistance` float|bool||Physics \| Sphere Cast
|`SphereCast`|`ray` UnityEngine\.Ray<br>`radius` float<br>`maxDistance` float<br>`layerMask` int|bool||Physics \| Sphere Cast
|`SphereCast`|`ray` UnityEngine\.Ray<br>`radius` float<br>`maxDistance` float<br>`layerMask` int<br>`queryTriggerInteraction` UnityEngine\.QueryTriggerInteraction|bool|Casts a sphere along a ray and returns detailed information on what was hit\.|Physics \| Sphere Cast

## Enums

### UnityEngine\.ForceMode

Use ForceMode to specify how to apply a force using Rigidbody\.AddForce or ArticulationBody\.AddForce\.

Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`Force`|0|Add a continuous force to the rigidbody, using its mass\.
|`Impulse`|1|Add an instant force impulse to the rigidbody, using its mass\.
|`VelocityChange`|2|Add an instant velocity change to the rigidbody, ignoring its mass\.
|`Acceleration`|5|Add a continuous acceleration to the rigidbody, ignoring its mass\.
### UnityEngine\.QueryTriggerInteraction

Overrides the global Physics\.queriesHitTriggers\.

Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`UseGlobal`|0|Queries use the global Physics\.queriesHitTriggers setting\.
|`Ignore`|1|Queries never report Trigger hits\.
|`Collide`|2|Queries always report Trigger hits\.
