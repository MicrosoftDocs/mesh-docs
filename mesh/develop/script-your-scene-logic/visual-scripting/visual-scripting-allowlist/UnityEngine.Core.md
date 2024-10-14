# UnityEngine\.Core

## Scene

### [Behaviour](https://docs.unity3d.com/ScriptReference/Behaviour.html)

Behaviours are Components that can be enabled or disabled\.

Supports additional properties and methods from UnityEngine\.Component and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? |
|----------|------|-------------|:-----:|:------:|:------:|
| Behaviour \| Get Enabled<br>Behaviour \| Set Enabled |bool|Enabled Behaviours are Updated, disabled Behaviours are not\.|yes|yes|yes|
| Behaviour \| Is Active And Enabled |bool|Reports whether a GameObject and its associated Behaviour is active and enabled\.|yes|no|no|

### [Component](https://docs.unity3d.com/ScriptReference/Component.html)

Base class for everything attached to a GameObject\.

Supports additional properties and methods from UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? |
|----------|------|-------------|:-----:|:------:|:------:|
| Component \| Get Game Object |GameObject|The GameObject this component is attached to\. A component is always attached to a GameObject\.|yes|no|no|
| Component \| Get Tag |string|The tag of this GameObject\.|yes|no|no|
| Component \| Get Transform |Transform|The Transform attached to this GameObject\.|yes|no|no|

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
| Component \| Get Component |`type` System\.Type|Component|
| Component \| Get Component In Children |`t` System\.Type|Component|
| Component \| Get Component In Children |`t` System\.Type<br>`Include Inactive` bool|Component|
| Component \| Get Component In Parent |`t` System\.Type|Component|
| Component \| Get Component In Parent |`t` System\.Type<br>`Include Inactive` bool|Component|
| Component \| Get Components |`type` System\.Type|Component Array|
| Component \| Get Components In Children |`t` System\.Type|Component Array||
| Component \| Get Components In Children |`t` System\.Type<br>`Include Inactive` bool|Component Array|
| Component \| Get Components In Parent |`t` System\.Type|Component Array||
| Component \| Get Components In Parent |`t` System\.Type<br>`Include Inactive` bool|Component Array|

### [GameObject](https://docs.unity3d.com/ScriptReference/GameObject.html)

Base class for all entities in Unity Scenes\.

Supports additional properties and methods from UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? |
|----------|------|-------------|:-----:|:------:|:------:|
| Game Object \| Get Active In Hierarchy |bool|Defines whether the GameObject is active in the Scene\.|yes|no|no|
| Game Object \| Get Active Self |bool|The local active state of this GameObject\. \(Read Only\)|yes|no|no|
| Game Object \| Is Static |bool|Gets and sets the GameObject's StaticEditorFlags\.|yes|no|no|
| Game Object \| Get Tag |string|The tag of this GameObject\.|yes|no|no|
| Game Object \| Get Transform |Transform|The Transform attached to this GameObject\.|yes|no|no|

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
| Game Object \| Get Component |`type` System\.Type|Component|
| Game Object \| Get Component In Children |`type` System\.Type|Component|
| Game Object \| Get Component In Children |`type` System\.Type<br>`Include Inactive` bool|Component|
| Game Object \| Get Component In Parent |`type` System\.Type|Component|
| Game Object \| Get Component In Parent |`type` System\.Type<br>`Include Inactive` bool|Component|
| Game Object \| Get Components |`type` System\.Type|Component Array|
| Game Object \| Get Components In Children |`type` System\.Type|Component Array|
| Game Object \| Get Components In Children |`type` System\.Type<br>`Include Inactive` bool|Component Array|
| Game Object \| Get Components In Parent |`type` System\.Type|Component Array||
| Game Object \| Get Components In Parent |`type` System\.Type<br>`Include Inactive` bool|Component Array|
| Game Object \| Set Active |`value` bool|void|ActivatesDeactivates the GameObject, depending on the given true or false/ value\.|

### [Light](https://docs.unity3d.com/ScriptReference/Light.html)

Script interface for light components.

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

### [LineRenderer](https://docs.unity3d.com/ScriptReference/LineRenderer.html)

The line renderer is used to draw free\-floating lines in 3D space\.

Supports additional properties and methods from UnityEngine\.Renderer, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? |
|----------|------|-------------|:-----:|:------:|:------:|
| Line Renderer \| Get Position Count<br>Line Renderer \| Set Position Count |int|Set/get the number of vertices\.|yes|yes|no|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Line Renderer \| Get Position |`index` int|Vector3|Get the position of a vertex in the line\.|
| Line Renderer \| Get Positions |`positions` Vector3 Array|int||
| Line Renderer \| Set Position |`index` int<br>`position` Vector3|void|Set the position of a vertex in the line\.|
| Line Renderer \| Set Positions |`positions` Vector3 Array|void|Set the positions of all vertices in the line\.|

### [MeshFilter](https://docs.unity3d.com/ScriptReference/MeshFilter.html)

A class to access the Mesh of the\.

Supports additional properties and methods from UnityEngine\.Component and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? |
|----------|------|-------------|:-----:|:------:|:------:|
| Mesh Filter \| Get Mesh<br>Mesh Filter \| Set Mesh |Mesh|Returns either a new Mesh\|mesh or a duplicate of the existing mesh, and assigns it to the mesh filter\.|yes|yes|no|
| Mesh Filter \| Get Shared Mesh |Mesh|Returns the shared mesh of the mesh filter\.|yes|no|no|

### [MeshRenderer](https://docs.unity3d.com/ScriptReference/MeshRenderer.html)

Renders meshes inserted by the MeshFilter or TextMesh\.

Supports additional properties and methods from UnityEngine\.Renderer, UnityEngine\.Component, and UnityEngine\.Object.

### [RectTransform](https://docs.unity3d.com/ScriptReference/RectTransform.html)

Position, size, anchor and pivot information for a rectangle\.

Supports additional properties and methods from UnityEngine\.Transform, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? |
|----------|------|-------------|:-----:|:------:|:------:|
| Rect Transform \| Get Anchored Position |Vector2|The position of the pivot of this RectTransform relative to the anchor reference point\.|yes|no|no|
| Rect Transform \| Get Anchored Position 3D |Vector3|The 3D position of the pivot of this RectTransform relative to the anchor reference point\.|yes|no|no|
| Rect Transform \| Get Anchor Max |Vector2|The normalized position in the parent RectTransform that the upper right corner is anchored to\.|yes|no|no|
| Rect Transform \| Get Anchor Min |Vector2|The normalized position in the parent RectTransform that the lower left corner is anchored to\.|yes|no|no|
| Rect Transform \| Get Driven By Object |Object|The object that is driving the values of this RectTransform\. Value is null if not driven\.|yes|no|no|
| Rect Transform \| Get Offset Max |Vector2|The offset of the upper right corner of the rectangle relative to the upper right anchor\.|yes|no|no|
| Rect Transform \| Get Offset Min |Vector2|The offset of the lower left corner of the rectangle relative to the lower left anchor\.|yes|no|no|
| Rect Transform \| Get Pivot |Vector2|The normalized position in this RectTransform that it rotates around\.|yes|no|no|
| Rect Transform \| Get Rect |Rect|The calculated rectangle in the local space of the Transform\.|yes|no|no|
| Rect Transform \| Get Size Delta |Vector2|The size of this RectTransform relative to the distances between the anchors\.|yes|no|no|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Rect Transform \| Force Update Rect Transforms ||void|Force the recalculation of RectTransforms internal data\.|
| Rect Transform \| Set Inset And Size From Parent Edge |`edge` RectTransform\.Edge<br>`inset` float<br>`size` float|void||
| Rect Transform \| Set Size With Current Anchors |`axis` RectTransform\.Axis<br>`size` float|void||

### [Renderer](https://docs.unity3d.com/ScriptReference/Renderer.html)

General functionality for all renderers\.

Supports additional properties and methods from UnityEngine\.Component and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? |
|----------|------|-------------|:-----:|:------:|:------:|
| Renderer \| Get Bounds<br>Renderer \| Set Bounds |Bounds|The bounding box of the renderer in world space\.|yes|yes|no|
| Renderer \| Get Enabled<br>Renderer \| Set Enabled |bool|Makes the rendered 3D object visible if enabled\.|yes|yes|yes|
| Renderer \| Is Visible |bool|Is this renderer visible in any camera? \(Read Only\)|yes|no|no|
| Renderer \| Get Local Bounds<br>Renderer \| Set Local Bounds |Bounds|The bounding box of the renderer in local space\.|yes|yes|no|
| Renderer \| Get Local To World Matrix |Matrix4x4|Matrix that transforms a point from local space into world space \(Read Only\)\.|yes|no|no|
| Renderer \| Get Material<br>Renderer \| Set Material |Material|Returns the first instantiated Material assigned to the renderer\.|yes|yes|no|
| Renderer \| Get Shared Material |Material|The shared material of this object\.|yes|no|no|
| Renderer \| Get World To Local Matrix |Matrix4x4|Matrix that transforms a point from world space into local space \(Read Only\)\.|yes|no|no|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Renderer \| Set Property Block |`properties` MaterialPropertyBlock|void|Lets you set or clear per\-renderer or per\-material parameter overrides\.|
| Renderer \| Set Property Block |`properties` MaterialPropertyBlock<br>`materialIndex` int|void|Lets you set or clear per\-renderer or per\-material parameter overrides\.|

### [TrailRenderer](https://docs.unity3d.com/ScriptReference/TrailRenderer.html)

The trail renderer is used to make trails behind objects in the Scene as they move about\.

Supports additional properties and methods from UnityEngine\.Renderer, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? |
|----------|------|-------------|:-----:|:------:|:------:|
| Trail Renderer \| Get Emitting<br>Trail Renderer \| Set Emitting |bool|Creates trails when the GameObject moves\.|yes|yes|yes|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Trail Renderer \| Add Position |`position` Vector3|void|Adds a position to the trail\.|
| Trail Renderer \| Add Positions |`positions` Vector3 Array|void|Add an array of positions to the trail\.|
| Trail Renderer \| Get Position |`index` int|Vector3|Get the position of a vertex in the trail\.|
| Trail Renderer \| Get Positions |`positions` Vector3 Array|int||
| Trail Renderer \| Set Position |`index` int<br>`position` Vector3|void|Set the position of a vertex in the trail\.|
| Trail Renderer \| Set Positions |`positions` Vector3 Array|void|Sets the positions of all vertices in the trail\.|

### [Transform](https://docs.unity3d.com/ScriptReference/Transform.html)

Position, rotation and scale of an object\.

Supports additional properties and methods from UnityEngine\.Component and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? |
|----------|------|-------------|:-----:|:------:|:------:|
| Transform \| Get Child Count |int|The number of children the parent Transform has\.|yes|no|no|
| Transform \| Get Euler Angles<br>Transform \| Set Euler Angles |Vector3|The rotation as Euler angles in degrees\.|yes|yes|yes|
| Transform \| Get Forward<br>Transform \| Set Forward |Vector3|Returns a normalized vector representing the blue axis of the transform in world space\.|yes|yes|yes|
| Transform \| Get Local Euler Angles<br>Transform \| Set Local Euler Angles |Vector3|The rotation as Euler angles in degrees relative to the parent transform's rotation\.|yes|yes|yes|
| Transform \| Get Local Position<br>Transform \| Set Local Position |Vector3|Position of the transform relative to the parent transform\.|yes|yes|yes|
| Transform \| Get Local Rotation<br>Transform \| Set Local Rotation |Quaternion|The rotation of the transform relative to the transform rotation of the parent\.|yes|yes|yes|
| Transform \| Get Local Scale<br>Transform \| Set Local Scale |Vector3|The scale of the transform relative to the GameObjects parent\.|yes|yes|yes|
| Transform \| Get Local To World Matrix |Matrix4x4|Matrix that transforms a point from local space into world space. \(Read Only\)\.|yes|no|yes|
| Transform \| Get Lossy Scale |Vector3|The global scale of the object \(Read Only\)\.|yes|no|yes|
|`parent`|Transform|The parent of the transform\.|yes|no|no|Transform \| Get Parent
| Transform \| Get Position<br>Transform \| Set Position |Vector3|The world space position of the Transform\.|yes|yes|yes|
| Transform \| Get Right<br>Transform \| Set Right |Vector3|The red axis of the transform in world space\.|yes|yes|yes|
|`root`|Transform|Returns the topmost transform in the hierarchy\.|yes|no|no|Transform \| Get Root
| Transform \| Get Rotation<br>Transform \| Set Rotation |Quaternion|A Quaternion that stores the rotation of the Transform in world space\.|yes|yes|yes|
| Transform \| Get Up<br>Transform \| Set Up |Vector3|The green axis of the transform in world space\.|yes|yes|yes|
| Transform \| Get World To Local Matrix |Matrix4x4|Matrix that transforms a point from world space into local space \(Read Only\)\.|yes|no|yes|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Transform \| Find |`n` string|Transform|Finds a child by name n and returns it\.|
| Transform \| Get Child |`index` int|Transform|Returns a transform child by index\.|
| Transform \| Get Sibling Index ||int|Gets the sibling index\.|
| Transform \| Inverse Transform Direction |`x` float<br>`y` float<br>`z` float|Vector3|Transforms the direction x, y, z from world space to local space\. The opposite of Transform\.TransformDirection\.|
| Transform \| Inverse Transform Direction |`direction` Vector3|Vector3|Transforms a direction from world space to local space\. The opposite of Transform\.TransformDirection\.|
| Transform \| Inverse Transform Point |`x` float<br>`y` float<br>`z` float|Vector3|Transforms the position x, y, z from world space to local space\.|
| Transform \| Inverse Transform Point |`position` Vector3|Vector3|Transforms position from world space to local space\.|
| Transform \| Inverse Transform Vector |`x` float<br>`y` float<br>`z` float|Vector3|Transforms the vector x, y, z from world space to local space\. The opposite of Transform\.TransformVector\.|
| Transform \| Inverse Transform Vector |`vector` Vector3|Vector3|Transforms a vector from world space to local space\. The opposite of Transform\.TransformVector\.|
| Transform \| Is Child Of |`parent` Transform|bool|Is this transform a child of parent?|
| Transform \| Look At |`target` Transform|void|Rotates the transform so the forward vector points at target's current position\.|
| Transform \| Look At |`target` Transform<br>`worldUp` Vector3|void|Rotates the transform so the forward vector points at target's current position\.|
| Transform \| Look At |`worldPosition` Vector3|void|Rotates the transform so the forward vector points at worldPosition\.|
| Transform \| Look At |`worldPosition` Vector3<br>`worldUp` Vector3|void|Rotates the transform so the forward vector points at worldPosition\.|
| Transform \| Rotate |`xAngle` float<br>`yAngle` float<br>`zAngle` float|void|The implementation of this method applies a rotation of zAngle degrees around the z axis, xAngle degrees around the x axis, and yAngle degrees around the y axis \(in that order\)\.|
| Transform \| Rotate |`xAngle` float<br>`yAngle` float<br>`zAngle` float<br>`relativeTo` Space|void|The implementation of this method applies a rotation of zAngle degrees around the z axis, xAngle degrees around the x axis, and yAngle degrees around the y axis \(in that order\)\.|
| Transform \| Rotate |`eulers` Vector3|void|Applies a rotation of eulerAngles\.z degrees around the z\-axis, eulerAngles\.x degrees around the x\-axis, and eulerAngles\.y degrees around the y\-axis \(in that order\)\.|
| Transform \| Rotate |`axis` Vector3<br>`angle` float|void|Rotates the object around the given axis by the number of degrees defined by the given angle\.|
| Transform \| Rotate |`axis` Vector3<br>`angle` float<br>`relativeTo` Space|void|Rotates the object around the given axis by the number of degrees defined by the given angle\.|
| Transform \| Rotate |`eulers` Vector3<br>`relativeTo` Space|void|Applies a rotation of eulerAngles\.z degrees around the z\-axis, eulerAngles\.x degrees around the x\-axis, and eulerAngles\.y degrees around the y\-axis \(in that order\)\.|
| Transform \| Rotate Around |`point` Vector3<br>`axis` Vector3<br>`angle` float|void|Rotates the transform about axis passing through point in world coordinates by angle degrees\.|
| Transform \| Transform Direction |`x` float<br>`y` float<br>`z` float|Vector3|Transforms direction x, y, z from local space to world space\.|
| Transform \| Transform Direction |`direction` Vector3|Vector3|Transforms direction from local space to world space\.|
| Transform \| Transform Point |`x` float<br>`y` float<br>`z` float|Vector3|Transforms the position x, y, z from local space to world space\.|
| Transform \| Transform Point |`position` Vector3|Vector3|Transforms position from local space to world space\.|
| Transform \| Transform Vector |`x` float<br>`y` float<br>`z` float|Vector3|Transforms vector x, y, z from local space to world space\.|
| Transform \| Transform Vector |`vector` Vector3|Vector3|Transforms vector from local space to world space\.|
| Transform \| Translate |`x` float<br>`y` float<br>`z` float|void|Moves the transform by x along the x axis, y along the y axis, and z along the z axis\.|
| Transform \| Translate |`x` float<br>`y` float<br>`z` float<br>`relativeTo` Space|void|Moves the transform by x along the x axis, y along the y axis, and z along the z axis\.|
| Transform \| Translate |`x` float<br>`y` float<br>`z` float<br>`relativeTo` Transform|void|Moves the transform by x along the x axis, y along the y axis, and z along the z axis\.|
| Transform \| Translate |`translation` Vector3|void|Moves the transform in the direction and distance of translation\.|
| Transform \| Translate |`translation` Vector3<br>`relativeTo` Space|void|Moves the transform in the direction and distance of translation\.|
| Transform \| Translate |`translation` Vector3<br>`relativeTo` Transform|void|Moves the transform in the direction and distance of translation\.|

## Structs

### [Bounds](https://docs.unity3d.com/ScriptReference/Bounds.html)

Represents an axis aligned bounding box\.

| Property | Type | Description | Read? | Write? |
|----------|------|-------------|:-----:|:------:|
| Bounds \| Get Center<br>Bounds \| Set Center |Vector3|The center of the bounding box\.|yes|yes|
| Bounds \| Get Extents<br>Bounds \| Set Extents |Vector3|The extents of the Bounding Box\. This is always half of the size of the Bounds\.|yes|yes|
| Bounds \| Get Max<br>Bounds \| Set Max |Vector3|The maximal point of the box\. This is always equal to center\+extents\.|yes|yes|
| Bounds \| Get Min<br>Bounds \| Set Min |Vector3|The minimal point of the box\. This is always equal to center\-extents\.|yes|yes|
| Bounds \| Get Size<br>Bounds \| Set Size |Vector3|The total size of the box\. This is always twice as large as the extents\.|yes|yes|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Bounds \| Create Bounds |`center` Vector3<br>`size` Vector3|Bounds|Creates a new Bounds\.|
| Bounds \| Closest Point |`point` Vector3|Vector3|The closest point on the bounding box\.|
| Bounds \| Contains |`point` Vector3|bool|Is point contained in the bounding box?|
| Bounds \| Encapsulate |`bounds` Bounds|void|Grow the bounds to encapsulate the bounds\.|
| Bounds \| Encapsulate |`point` Vector3|void|Grows the Bounds to include the point\.|
|`Expand`|`amount` float|void|Expand the bounds by increasing its size by amount along each side\.|Bounds \| Expand
| Bounds \| Expand |`amount` Vector3|void|Expand the bounds by increasing its size by amount along each side\.|
| Bounds \| Intersect Ray |`ray` Ray|bool|Does ray intersect this bounding box?|
| Bounds \| Intersects |`bounds` Bounds|bool|Does another bounding box intersect with this bounding box?|
| Bounds \| Set Min Max |`min` Vector3<br>`max` Vector3|void|Sets the bounds to the min and max value of the box\.|
| Bounds \| Sqr Distance |`point` Vector3|float|The smallest squared distance between the point and this bounding box\.|

### [Color](https://docs.unity3d.com/ScriptReference/Color.html)

Representation of RGBA colors\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
| Color \| Get A<br>Color \| Set A |float|Alpha component of the color \(0 is transparent, 1 is opaque\)\.|yes|yes|
| Color \| Get B<br>Color \| Set B |float|Blue component of the color\.|yes|yes|
| Color \| Get G<br>Color \| Set G |float|Green component of the color\.|yes|yes|
| Color \| Get Gamma |Color|A version of the color that has had the gamma curve applied\.|yes|no|
| Color \| Get Grayscale |float|The grayscale value of the color\. \(Read Only\)|yes|no|
| Color \| Get Linear |Color|A linear value of an sRGB color\.|yes|no|
| Color \| Get Max Color Component |float|Returns the maximum color component value: Max\(r,g,b\)\.|yes|no|
| Color \| Get R<br>Color \| Set R |float|Red component of the color\.|yes|yes|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Color \| Create Color |`r` float<br>`g` float<br>`b` float|Color|Constructs a new Color with given r,g,b components and sets a to 1\.|
| Color \| Create Color |`r` float<br>`g` float<br>`b` float<br>`a` float|Color|Constructs a new Color with given r,g,b,a components\.|
| Color \| Equals |`other` Color|bool||
| Color \| HSV To RGB |`H` float<br>`S` float<br>`V` float|Color|Creates an RGB colour from HSV input\.|
| Color \| HSV To RGB |`H` float<br>`S` float<br>`V` float<br>`hdr` bool|Color|Creates an RGB colour from HSV input\.|
| Color \| Lerp |`a` Color<br>`b` Color<br>`t` float|Color|Linearly interpolates between colors a and b by t\.|
| Color \| Lerp Unclamped |`a` Color<br>`b` Color<br>`t` float|Color|Linearly interpolates between colors a and b by t\.|

### [Mathf](https://docs.unity3d.com/ScriptReference/Mathf.html)

A collection of common math functions\.

| Property | Type | Description | Read? | Write? |
|----------|------|-------------|:-----:|:------:|
|Mathf \| Get Deg 2 Rad|float|Degrees\-to\-radians conversion constant \(Read Only\)\.|yes|no|Mathf \| Get Deg 2 Rad
| Mathf \| Get Epsilon |float|A tiny floating point value \(Read Only\)\.|yes|no|
| Mathf \| Get Infinity |float|A representation of positive infinity \(Read Only\)\.|yes|no|
| Mathf \| Get Negative Infinity |float|A representation of negative infinity \(Read Only\)\.|yes|no|
| Mathf \| Get PI |float|The well\-known 3\.14159265358979\.\.\. value \(Read Only\)\.|yes|no|
| Mathf \| Get Rad 2 Deg |float|Radians\-to\-degrees conversion constant \(Read Only\)\.|yes|no|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Mathf \| Abs |`f` float|float|Returns the absolute value of f\.|
| Mathf \| Abs |`value` int|int|Returns the absolute value of value\.|
| Mathf \| Acos |`f` float|float|Returns the arc\-cosine of f \- the angle in radians whose cosine is f\.|
| Mathf \| Approximately |`a` float<br>`b` float|bool|Compares two floating point values and returns true if they are similar\.|
| Mathf \| Asin |`f` float|float|Returns the arc\-sine of f \- the angle in radians whose sine is f\.|
| Mathf \| Atan |`f` float|float|Returns the arc\-tangent of f \- the angle in radians whose tangent is f\.|
| Mathf \| Atan 2|`y` float<br>`x` float|float|Returns the angle in radians whose Tan is y/x\.|
| Mathf \| Ceil |`f` float|float|Returns the smallest integer greater to or equal to f\.|
| Mathf \| Ceil To Int |`f` float|int|Returns the smallest integer greater to or equal to f\.|
| Mathf \| Clamp |`value` float<br>`min` float<br>`max` float|float|Clamps the given value between the given minimum float and maximum float values\. Returns the given value if it is within the minimum and maximum range\.|
| Mathf \| Clamp |`value` int<br>`min` int<br>`max` int|int|Clamps the given value between a range defined by the given minimum integer and maximum integer values\. Returns the given value if it is within min and max\.|
| Mathf \| Clamp 01|`value` float|float|Clamps value between 0 and 1 and returns value\.|
| Mathf \| Closest Power Of Two |`value` int|int|Returns the closest power of two value\.|
| Mathf \| Correlated Color Temperature To RGB |`kelvin` float|Color|Convert a color temperature in Kelvin to RGB color\.|
| Mathf \| Cos |`f` float|float|Returns the cosine of angle f\.|
| Mathf \| Delta Angle |`current` float<br>`target` float|float|Calculates the shortest difference between two given angles given in degrees\.|
| Mathf \| Exp |`power` float|float|Returns e raised to the specified power\.|
| Mathf \| Floor |`f` float|float|Returns the largest integer smaller than or equal to f\.|
| Mathf \| Floor To Int |`f` float|int|Returns the largest integer smaller to or equal to f\.|
| Mathf \| Gamma |`value` float<br>`absmax` float<br>`gamma` float|float||
| Mathf \| Gamma To Linear Space |`value` float|float|Converts the given value from gamma \(sRGB\) to linear color space\.|
| Mathf \| Inverse Lerp |`a` float<br>`b` float<br>`value` float|float|Determines where a value lies between two points\.|
| Mathf \| Is Power Of Two |`value` int|bool|Returns true if the value is power of two\.|
| Mathf \| Lerp |`a` float<br>`b` float<br>`t` float|float|Linearly interpolates between a and b by t\.|
| Mathf \| Lerp Angle |`a` float<br>`b` float<br>`t` float|float|Same as Lerp but makes sure the values interpolate correctly when they wrap around 360 degrees\.|
| Mathf \| Lerp Unclamped |`a` float<br>`b` float<br>`t` float|float|Linearly interpolates between a and b by t with no limit to t\.|
| Mathf \| Linear To Gamma Space |`value` float|float|Converts the given value from linear to gamma \(sRGB\) color space\.|
| Mathf \| Log |`f` float|float|Returns the natural \(base e\) logarithm of a specified number\.|
| Mathf \| Log |`f` float<br>`p` float|float|Returns the logarithm of a specified number in a specified base\.|
| Mathf \| Log 10|`f` float|float|Returns the base 10 logarithm of a specified number\.|
| Mathf \| Max |`a` float<br>`b` float|float|Returns largest of two or more values\.|
| Mathf \| Max |`a` int<br>`b` int|int|Returns the largest of two or more values\.|
| Mathf \| Min |`a` float<br>`b` float|float|Returns the smallest of two or more values\.|
| Mathf \| Min |`a` int<br>`b` int|int|Returns the smallest of two or more values\.|
| Mathf \| Move Towards |`current` float<br>`target` float<br>`maxDelta` float|float|Moves a value current towards target\.|
| Mathf \| Move Towards Angle |`current` float<br>`target` float<br>`maxDelta` float|float|Same as MoveTowards but makes sure the values interpolate correctly when they wrap around 360 degrees\.|
| Mathf \| Next Power Of Two |`value` int|int|Returns the next power of two that is equal to, or greater than, the argument\.|
| Mathf \| Perlin Noise |`x` float<br>`y` float|float|Generate 2D Perlin noise\.|
| Mathf \| Ping Pong |`t` float<br>`length` float|float|PingPong returns a value that will increment and decrement between the value 0 and length\.|
| Mathf \| Pow |`f` float<br>`p` float|float|Returns f raised to power p\.|
| Mathf \| Repeat |`t` float<br>`length` float|float|Loops the value t, so that it is never larger than length and never smaller than 0\.|
| Mathf \| Round |`f` float|float|Returns f rounded to the nearest integer\.|
| Mathf \| Round To Int |`f` float|int|Returns f rounded to the nearest integer\.|
| Mathf \| Sign |`f` float|float|Returns the sign of f\.|
| Mathf \| Sin |`f` float|float|Returns the sine of angle f\.|
| Mathf \| Smooth Step |`from` float<br>`to` float<br>`t` float|float|Interpolates between min and max with smoothing at the limits\.|
| Mathf \| Sqrt |`f` float|float|Returns square root of f\.|
| Mathf \| Tan |`f` float|float|Returns the tangent of angle f in radians\.|

### [Matrix4x4](https://docs.unity3d.com/ScriptReference/Matrix4x4.html)

A standard 4x4 transformation matrix\.

| Property | Type | Description | Read? | Write? 
|----------|------|-------------|:-----:|:------:|
| Matrix 4x 4 \| Get Determinant |float|The determinant of the matrix\. \(Read Only\)|yes|no|
| Matrix 4x 4 \| Get Identity |Matrix4x4|Returns the identity matrix \(Read Only\)\.|yes|no|
| Matrix 4x 4 \| Get Inverse |Matrix4x4|The inverse of this matrix\. \(Read Only\)|yes|no|
| Matrix 4x 4 \| Is Identity |bool|Checks whether this is an identity matrix\. \(Read Only\)|yes|no|
| Matrix 4x 4 \| Get Lossy Scale |Vector3|Attempts to get a scale value from the matrix\. \(Read Only\)|yes|no|
| Matrix 4x 4 \| Get M 00<br>Matrix 4x 4 \| Set M 00|float||yes|yes|
| Matrix 4x 4 \| Get M 01<br>Matrix 4x 4 \| Set M 01|float||yes|yes|
| Matrix 4x 4 \| Get M 02<br>Matrix 4x 4 \| Set M 02|float||yes|yes|
| Matrix 4x 4 \| Get M 03<br>Matrix 4x 4 \| Set M 03|float||yes|yes|
| Matrix 4x 4 \| Get M 10<br>Matrix 4x 4 \| Set M 10|float||yes|yes|
| Matrix 4x 4 \| Get M 11<br>Matrix 4x 4 \| Set M 11|float||yes|yes|
| Matrix 4x 4 \| Get M 12<br>Matrix 4x 4 \| Set M 12|float||yes|yes|
| Matrix 4x 4 \| Get M 13<br>Matrix 4x 4 \| Set M 13|float||yes|yes|
| Matrix 4x 4 \| Get M 20<br>Matrix 4x 4 \| Set M 20|float||yes|yes|
| Matrix 4x 4 \| Get M 21<br>Matrix 4x 4 \| Set M 21|float||yes|yes|
| Matrix 4x 4 \| Get M 22<br>Matrix 4x 4 \| Set M 22|float||yes|yes|
| Matrix 4x 4 \| Get M 23<br>Matrix 4x 4 \| Set M 23|float||yes|yes|
| Matrix 4x 4 \| Get M 30<br>Matrix 4x 4 \| Set M 30|float||yes|yes|
| Matrix 4x 4 \| Get M 31<br>Matrix 4x 4 \| Set M 31|float||yes|yes|
| Matrix 4x 4 \| Get M 32<br>Matrix 4x 4 \| Set M 32|float||yes|yes|
| Matrix 4x 4 \| Get M 33<br>Matrix 4x 4 \| Set M 33|float||yes|yes|
| Matrix 4x 4 \| Get Rotation |Quaternion|Attempts to get a rotation quaternion from this matrix\.|yes|no|
| Matrix 4x 4 \| Get Transpose |Matrix4x4|Returns the transpose of this matrix \(Read Only\)\.|yes|no|
| Matrix 4x 4 \| Get Zero |Matrix4x4|Returns a matrix with all elements set to zero \(Read Only\)\.|yes|no|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Matrix 4x 4 \| Create Matrix 4x 4|`column0` Vector4<br>`column1` Vector4<br>`column2` Vector4<br>`column3` Vector4|Matrix4x4||
| Matrix 4x 4 \| Determinant |`m` Matrix4x4|float||
| Matrix 4x 4 \| Frustum |`left` float<br>`right` float<br>`bottom` float<br>`top` float<br>`zNear` float<br>`zFar` float|Matrix4x4|This function returns a projection matrix with viewing frustum that has a near plane defined by the coordinates that were passed in\.|
| Matrix 4x 4 \| Get Column |`index` int|Vector4|Get a column of the matrix\.|
| Matrix 4x 4 \| Get Position ||Vector3|Get position vector from the matrix\.|
| Matrix 4x 4 \| Get Row |`index` int|Vector4|Returns a row of the matrix\.|
| Matrix 4x 4 \| Inverse |`m` Matrix4x4|Matrix4x4||
| Matrix 4x 4 \| Look At |`from` Vector3<br>`to` Vector3<br>`up` Vector3|Matrix4x4|Create a "look at" matrix\.|
| Matrix 4x 4 \| Multiply Point |`point` Vector3|Vector3|Transforms a position by this matrix \(generic\)\.|
| Matrix 4x 4 \| Multiply Point 3x 4|`point` Vector3|Vector3|Transforms a position by this matrix \(fast\)\.|
| Matrix 4x 4 \| Multiply Vector |`vector` Vector3|Vector3|Transforms a direction by this matrix\.|
| Matrix 4x 4 \| Ortho |`left` float<br>`right` float<br>`bottom` float<br>`top` float<br>`zNear` float<br>`zFar` float|Matrix4x4|Create an orthogonal projection matrix\.|
| Matrix 4x 4 \| Perspective |`fov` float<br>`aspect` float<br>`zNear` float<br>`zFar` float|Matrix4x4|Create a perspective projection matrix\.|
| Matrix 4x 4 \| Rotate |`q` Quaternion|Matrix4x4|Creates a rotation matrix\.|
| Matrix 4x 4 \| Scale |`vector` Vector3|Matrix4x4|Creates a scaling matrix\.|
| Matrix 4x 4 \| Set Column |`index` int<br>`column` Vector4|void|Sets a column of the matrix\.|
| Matrix 4x 4 \| Set Row |`index` int<br>`row` Vector4|void|Sets a row of the matrix\.|
| Matrix 4x 4 \| Set TRS |`pos` Vector3<br>`q` Quaternion<br>`s` Vector3|void|Sets this matrix to a translation, rotation and scaling matrix\.|
| Matrix 4x 4 \| Translate |`vector` Vector3|Matrix4x4|Creates a translation matrix\.|
| Matrix 4x 4 \| Transpose |`m` Matrix4x4|Matrix4x4||
| Matrix 4x 4 \| TRS |`pos` Vector3<br>`q` Quaternion<br>`s` Vector3|Matrix4x4|Creates a translation, rotation and scaling matrix\.|
| Matrix 4x 4 \| Valid TRS ||bool|Checks if this matrix is a valid transform matrix\.|

### [Quaternion](https://docs.unity3d.com/ScriptReference/Quaternion.html)

Quaternions are used to represent rotations\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
| Quaternion \| Get Euler Angles<br>Quaternion \| Set Euler Angles |Vector3|Returns or sets the euler angle representation of the rotation\.|yes|yes|
| Quaternion \| Get Identity |Quaternion|The identity rotation \(Read Only\)\.|yes|no|
| Quaternion \| Get Normalized |Quaternion|Returns this quaternion with a magnitude of 1 \(Read Only\)\.|yes|no|
| Quaternion \| Get W<br>Quaternion \| Set W |float|W component of the Quaternion\. Do not directly modify quaternions\.|yes|yes|
| Quaternion \| Get X<br>Quaternion \| Set X |float|X component of the Quaternion\. Don't modify this directly unless you know quaternions inside out\.|yes|yes|
| Quaternion \| Get Y<br>Quaternion \| Set Y |float|Y component of the Quaternion\. Don't modify this directly unless you know quaternions inside out\.|yes|yes|
| Quaternion \| Get Z<br>Quaternion \| Set Z |float|Z component of the Quaternion\. Don't modify this directly unless you know quaternions inside out\.|yes|yes|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Quaternion \| Create Quaternion |`x` float<br>`y` float<br>`z` float<br>`w` float|Quaternion|Constructs new Quaternion with given x,y,z,w components\.|
| Quaternion \| Angle |`a` Quaternion<br>`b` Quaternion|float|Returns the angle in degrees between two rotations a and b\.|
| Quaternion \| Angle Axis |`angle` float<br>`axis` Vector3|Quaternion|Creates a rotation which rotates angle degrees around axis\.|
| Quaternion \| Dot |`a` Quaternion<br>`b` Quaternion|float|The dot product between two rotations\.|
| Quaternion \| Euler |`x` float<br>`y` float<br>`z` float|Quaternion|Returns a rotation that rotates z degrees around the z axis, x degrees around the x axis, and y degrees around the y axis; applied in that order\.|
| Quaternion \| Euler |`euler` Vector3|Quaternion|Returns a rotation that rotates z degrees around the z axis, x degrees around the x axis, and y degrees around the y axis\.|
| Quaternion \| From To Rotation |`fromDirection` Vector3<br>`toDirection` Vector3|Quaternion|Creates a rotation which rotates from fromDirection to toDirection\.|
| Quaternion \| Inverse |`rotation` Quaternion|Quaternion|Returns the Inverse of rotation\.|
| Quaternion \| Lerp |`a` Quaternion<br>`b` Quaternion<br>`t` float|Quaternion|Interpolates between a and b by t and normalizes the result afterwards\. The parameter t is clamped to the range \[0, 1\]\.|
| Quaternion \| Lerp Unclamped |`a` Quaternion<br>`b` Quaternion<br>`t` float|Quaternion|Interpolates between a and b by t and normalizes the result afterwards\. The parameter t is not clamped\.|
| Quaternion \| Look Rotation |`forward` Vector3|Quaternion|Creates a rotation with the specified forward and upwards directions\.|
| Quaternion \| Look Rotation |`forward` Vector3<br>`upwards` Vector3|Quaternion|Creates a rotation with the specified forward and upwards directions\.|
| Quaternion \| Normalize |`q` Quaternion|Quaternion|Converts this quaternion to one with the same orientation but with a magnitude of 1\.|
| Quaternion \| Rotate Towards |`from` Quaternion<br>`to` Quaternion<br>`maxDegreesDelta` float|Quaternion|Rotates a rotation from towards to\.|
| Quaternion \| Set |`newX` float<br>`newY` float<br>`newZ` float<br>`newW` float|void|Set x, y, z and w components of an existing Quaternion\.|
| Quaternion \| Set From To Rotation |`fromDirection` Vector3<br>`toDirection` Vector3|void|Creates a rotation which rotates from fromDirection to toDirection\.|
| Quaternion \| Set Look Rotation |`view` Vector3|void|Creates a rotation with the specified forward and upwards directions\.|
| Quaternion \| Set Look Rotation |`view` Vector3<br>`up` Vector3|void|Creates a rotation with the specified forward and upwards directions\.|
| Quaternion \| Slerp |`a` Quaternion<br>`b` Quaternion<br>`t` float|Quaternion|Spherically interpolates between quaternions a and b by ratio t\. The parameter t is clamped to the range \[0, 1\]\.|
| Quaternion \| Slerp Unclamped |`a` Quaternion<br>`b` Quaternion<br>`t` float|Quaternion|Spherically interpolates between a and b by t\. The parameter t is not clamped\.|

### [Ray](https://docs.unity3d.com/ScriptReference/Ray.html)

Representation of rays\.

| Property | Type | Description | Read? | Write? |
|----------|------|-------------|:-----:|:------:|
| Ray \| Get Direction<br>Ray \| Set Direction |Vector3|The direction of the ray\.|yes|yes|
| Ray \| Get Origin<br>Ray \| Set Origin |Vector3|The origin point of the ray\.|yes|yes|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Ray \| Create Ray |`origin` Vector3<br>`direction` Vector3|Ray|Creates a ray starting at origin along direction\.|
| Ray \| Get Point |`distance` float|Vector3|Returns a point at distance units along the ray\.|

### [Rect](https://docs.unity3d.com/ScriptReference/Rect.html)

A 2D Rectangle defined by X and Y position, width and height\.

| Property | Type | Description | Read? | Write? |
|----------|------|-------------|:-----:|:------:|
| Rect \| Get Center<br>Rect \| Set Center |Vector2|The position of the center of the rectangle\.|yes|yes|
| Rect \| Get Height<br>Rect \| Set Height |float|The height of the rectangle, measured from the Y position\.|yes|yes|
| Rect \| Get Max<br>Rect \| Set Max |Vector2|The position of the maximum corner of the rectangle\.|yes|yes|
| Rect \| Get Min<br>Rect \| Set Min |Vector2|The position of the minimum corner of the rectangle\.|yes|yes|
| Rect \| Get Position<br>Rect \| Set Position |Vector2|The X and Y position of the rectangle\.|yes|yes|
| Rect \| Get Size<br>Rect \| Set Size |Vector2|The width and height of the rectangle\.|yes|yes|
| Rect \| Get Width<br>Rect \| Set Width |float|The width of the rectangle, measured from the X position\.|yes|yes|
| Rect \| Get X<br>Rect \| Set X |float|The X coordinate of the rectangle\.|yes|yes|
| Rect \| Get X Max<br>Rect \| Set X Max |float|The maximum X coordinate of the rectangle\.|yes|yes|
| Rect \| Get X Min<br>Rect \| Set X Min |float|The minimum X coordinate of the rectangle\.|yes|yes|
|`y`|float|The Y coordinate of the rectangle\.|yes|yes|Rect \| Get Y<br>Rect \| Set Y
| Rect \| Get Y Max<br>Rect \| Set Y Max |float|The maximum Y coordinate of the rectangle\.|yes|yes|
| Rect \| Get Y Min<br>Rect \| Set Y Min |float|The minimum Y coordinate of the rectangle\.|yes|yes|
| Rect \| Get Zero |Rect|Shorthand for writing new Rect\(0,0,0,0\)\.|yes|no|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Rect \| Create Rect |`x` float<br>`y` float<br>`width` float<br>`height` float|Rect|Creates a new rectangle\.|
| Rect \| Create Rect |`position` Vector2<br>`size` Vector2|Rect|Creates a rectangle given a size and position\.|
| Rect \| Contains |`point` Vector2|bool|Returns true if the x and y components of point is a point inside this rectangle\. If allowInverse is present and true, the width and height of the Rect are allowed to take negative values \(ie, the min value is greater than the max\), and the test will still work\.|
| Rect \| Contains |`point` Vector3|bool|Returns true if the x and y components of point is a point inside this rectangle\. If allowInverse is present and true, the width and height of the Rect are allowed to take negative values \(ie, the min value is greater than the max\), and the test will still work\.|
| Rect \| Contains |`point` Vector3<br>`allowInverse` bool|bool|Returns true if the x and y components of point is a point inside this rectangle\. If allowInverse is present and true, the width and height of the Rect are allowed to take negative values \(ie, the min value is greater than the max\), and the test will still work\.|
| Rect \| Equals |`other` Rect|bool||
| Rect \| Min Max Rect |`xmin` float<br>`ymin` float<br>`xmax` float<br>`ymax` float|Rect|Creates a rectangle from min/max coordinate values\.|
| Rect \| Normalized To Point |`rectangle` Rect<br>`normalizedRectCoordinates` Vector2|Vector2|Returns a point inside a rectangle, given normalized coordinates\.|
| Rect \| Overlaps |`other` Rect|bool|Returns true if the other rectangle overlaps this one\. If allowInverse is present and true, the widths and heights of the Rects are allowed to take negative values \(ie, the min value is greater than the max\), and the test will still work\.|
| Rect \| Overlaps |`other` Rect<br>`allowInverse` bool|bool|Returns true if the other rectangle overlaps this one\. If allowInverse is present and true, the widths and heights of the Rects are allowed to take negative values \(ie, the min value is greater than the max\), and the test will still work\.|
| Rect \| Point To Normalized |`rectangle` Rect<br>`point` Vector2|Vector2|Returns the normalized coordinates cooresponding the the point\.|
| Rect \| Set |`x` float<br>`y` float<br>`width` float<br>`height` float|void|Set components of an existing Rect\.|

### [Vector2](https://docs.unity3d.com/ScriptReference/Vector2.html)

Representation of 2D vectors and points\.

| Property | Type | Description | Read? | Write? |
|----------|------|-------------|:-----:|:------:|
| Vector 2 \| Get Down |Vector2|Shorthand for writing Vector2\(0, \-1\)\.|yes|no|
| Vector 2 \| Get Left |Vector2|Shorthand for writing Vector2\(\-1, 0\)\.|yes|no|
| Vector 2 \| Get Magnitude |float|Returns the length of this vector \(Read Only\)\.|yes|no|
| Vector 2 \| Get Negative Infinity |Vector2|Shorthand for writing Vector2\(float\.NegativeInfinity, float\.NegativeInfinity\)\.|yes|no|
| Vector 2 \| Get Normalized |Vector2|Returns this vector with a magnitude of 1 \(Read Only\)\.|yes|no|
| Vector 2 \| Get One |Vector2|Shorthand for writing Vector2\(1, 1\)\.|yes|no|
| Vector 2 \| Get Positive Infinity |Vector2|Shorthand for writing Vector2\(float\.PositiveInfinity, float\.PositiveInfinity\)\.|yes|no|
| Vector 2 \| Get Right |Vector2|Shorthand for writing Vector2\(1, 0\)\.|yes|no|
| Vector 2 \| Get Sqr Magnitude |float|Returns the squared length of this vector \(Read Only\)\.|yes|no|
| Vector 2 \| Get Up |Vector2|Shorthand for writing Vector2\(0, 1\)\.|yes|no|
| Vector 2 \| Get X<br>Vector 2 \| Set X |float|X component of the vector\.|yes|yes|
| Vector 2 \| Get Y<br>Vector 2 \| Set Y |float|Y component of the vector\.|yes|yes|
| Vector 2 \| Get Zero |Vector2|Shorthand for writing Vector2\(0, 0\)\.|yes|no|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Vector 2 \| Create Vector 2|`x` float<br>`y` float|Vector2|Constructs a new vector with given x, y components\.|
| Vector 2 \| Angle |`from` Vector2<br>`to` Vector2|float|Gets the unsigned angle in degrees between from and to\.|
| Vector 2 \| Clamp Magnitude |`vector` Vector2<br>`maxLength` float|Vector2|Returns a copy of vector with its magnitude clamped to maxLength\.|
| Vector 2 \| Distance |`a` Vector2<br>`b` Vector2|float|Returns the distance between a and b\.|
| Vector 2 \| Dot |`lhs` Vector2<br>`rhs` Vector2|float|Dot Product of two vectors\.|
| Vector 2 \| Equals |`other` Vector2|bool||
| Vector 2 \| Lerp |`a` Vector2<br>`b` Vector2<br>`t` float|Vector2|Linearly interpolates between vectors a and b by t\.|
| Vector 2 \| Lerp Unclamped |`a` Vector2<br>`b` Vector2<br>`t` float|Vector2|Linearly interpolates between vectors a and b by t\.|
| Vector 2 \| Max |`lhs` Vector2<br>`rhs` Vector2|Vector2|Returns a vector that is made from the largest components of two vectors\.|
| Vector 2 \| Min |`lhs` Vector2<br>`rhs` Vector2|Vector2|Returns a vector that is made from the smallest components of two vectors\.|
| Vector 2 \| Move Towards |`current` Vector2<br>`target` Vector2<br>`maxDistanceDelta` float|Vector2|Moves a point current towards target\.|
| Vector 2 \| Normalize ||void|Makes this vector have a magnitude of 1\.|
| Vector 2 \| Perpendicular |`inDirection` Vector2|Vector2|Returns the 2D vector perpendicular to this 2D vector\. The result is always rotated 90\-degrees in a counter\-clockwise direction for a 2D coordinate system where the positive Y axis goes up\.|
| Vector 2 \| Reflect |`inDirection` Vector2<br>`inNormal` Vector2|Vector2|Reflects a vector off the vector defined by a normal\.|
| Vector 2 \| Scale |`scale` Vector2|void|Multiplies every component of this vector by the same component of scale\.|
| Vector 2 \| Scale |`a` Vector2<br>`b` Vector2|Vector2|Multiplies two vectors component\-wise\.|
| Vector 2 \| Set |`newX` float<br>`newY` float|void|Set x and y components of an existing Vector2\.|
| Vector 2 \| Signed Angle |`from` Vector2<br>`to` Vector2|float|Gets the signed angle in degrees between from and to\.|
| Vector 2 \| Sqr Magnitude ||float||
| Vector 2 \| Sqr Magnitude |`a` Vector2|float||

### [Vector3](https://docs.unity3d.com/ScriptReference/Vector3.html)

Representation of 3D vectors and points\.

| Property | Type | Description | Read? | Write? |
|----------|------|-------------|:-----:|:------:|
| Vector 3 \| Get Back |Vector3|Shorthand for writing Vector3\(0, 0, \-1\)\.|yes|no|
| Vector 3 \| Get Down |Vector3|Shorthand for writing Vector3\(0, \-1, 0\)\.|yes|no|
| Vector 3 \| Get Forward|Vector3|Shorthand for writing Vector3\(0, 0, 1\)\.|yes|no|
| Vector 3 \| Get Left |Vector3|Shorthand for writing Vector3\(\-1, 0, 0\)\.|yes|no|
| Vector 3 \| Get Magnitude |float|Returns the length of this vector \(Read Only\)\.|yes|no|
| Vector 3 \| Get Negative Infinity |Vector3|Shorthand for writing Vector3\(float\.NegativeInfinity, float\.NegativeInfinity, float\.NegativeInfinity\)\.|yes|no|
| Vector 3 \| Get Normalized |Vector3|Returns this vector with a magnitude of 1 \(Read Only\)\.|yes|no|
| Vector 3 \| Get One |Vector3|Shorthand for writing Vector3\(1, 1, 1\)\.|yes|no|
| Vector 3 \| Get Positive Infinity |Vector3|Shorthand for writing Vector3\(float\.PositiveInfinity, float\.PositiveInfinity, float\.PositiveInfinity\)\.|yes|no|
| Vector 3 \| Get Right |Vector3|Shorthand for writing Vector3\(1, 0, 0\)\.|yes|no|
| Vector 3 \| Get Sqr Magnitude |float|Returns the squared length of this vector \(Read Only\)\.|yes|no|
| Vector 3 \| Get Up |Vector3|Shorthand for writing Vector3\(0, 1, 0\)\.|yes|no|
| Vector 3 \| Get X<br>Vector 3 \| Set X |float|X component of the vector\.|yes|yes|
| Vector 3 \| Get Y<br>Vector 3 \| Set Y |float|Y component of the vector\.|yes|yes|
| Vector 3 \| Get Z<br>Vector 3 \| Set Z |float|Z component of the vector\.|yes|yes|
| Vector 3 \| Get Zero |Vector3|Shorthand for writing Vector3\(0, 0, 0\)\.|yes|no|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Vector 3 \| Create Vector 3|`x` float<br>`y` float|Vector3|Creates a new vector with given x, y components and sets z to zero\.|
| Vector 3 \| Create Vector 3|`x` float<br>`y` float<br>`z` float|Vector3|Creates a new vector with given x, y, z components\.|
| Vector 3 \| Angle |`from` Vector3<br>`to` Vector3|float|Calculates the angle between vectors from and\.|
| Vector 3 \| Clamp Magnitude |`vector` Vector3<br>`maxLength` float|Vector3|Returns a copy of vector with its magnitude clamped to maxLength\.|
| Vector 3 \| Cross |`lhs` Vector3<br>`rhs` Vector3|Vector3|Cross Product of two vectors\.|
| Vector 3 \| Distance |`a` Vector3<br>`b` Vector3|float|Returns the distance between a and b\.|
| Vector 3 \| Dot |`lhs` Vector3<br>`rhs` Vector3|float|Dot Product of two vectors\.|
| Vector 3 \| Equals |`other` Vector3|bool||
| Vector 3 \| Lerp |`a` Vector3<br>`b` Vector3<br>`t` float|Vector3|Linearly interpolates between two points\.|
| Vector 3 \| Lerp Unclamped |`a` Vector3<br>`b` Vector3<br>`t` float|Vector3|Linearly interpolates between two vectors\.|
| Vector 3 \| Magnitude |`vector` Vector3|float||
| Vector 3 \| Max |`lhs` Vector3<br>`rhs` Vector3|Vector3|Returns a vector that is made from the largest components of two vectors\.|
| Vector 3 \| Min |`lhs` Vector3<br>`rhs` Vector3|Vector3|Returns a vector that is made from the smallest components of two vectors\.|
| Vector 3 \| Move Towards |`current` Vector3<br>`target` Vector3<br>`maxDistanceDelta` float|Vector3|Calculate a position between the points specified by current and target, moving no farther than the distance specified by maxDistanceDelta\.|
| Vector 3 \| Normalize |`value` Vector3|Vector3|Makes this vector have a magnitude of 1\.|
| Vector 3 \| Project |`vector` Vector3<br>`onNormal` Vector3|Vector3|Projects a vector onto another vector\.|
| Vector 3 \| Project On Plane |`vector` Vector3<br>`planeNormal` Vector3|Vector3|Projects a vector onto a plane defined by a normal orthogonal to the plane\.|
| Vector 3 \| Reflect |`inDirection` Vector3<br>`inNormal` Vector3|Vector3|Reflects a vector off the plane defined by a normal\.|
| Vector 3 \| Rotate Towards |`current` Vector3<br>`target` Vector3<br>`maxRadiansDelta` float<br>`maxMagnitudeDelta` float|Vector3|Rotates a vector current towards target\.|
| Vector 3 \| Scale |`scale` Vector3|void|Multiplies every component of this vector by the same component of scale\.|
| Vector 3 \| Scale |`a` Vector3<br>`b` Vector3|Vector3|Multiplies two vectors component\-wise\.|
| Vector 3 \| Set |`newX` float<br>`newY` float<br>`newZ` float|void|Set x, y and z components of an existing Vector3\.|
| Vector 3 \| Signed Angle |`from` Vector3<br>`to` Vector3<br>`axis` Vector3|float|Calculates the signed angle between vectors from and to in relation to axis\.|
| Vector 3 \| Slerp |`a` Vector3<br>`b` Vector3<br>`t` float|Vector3|Spherically interpolates between two vectors\.|
| Vector 3 \| Slerp Unclamped |`a` Vector3<br>`b` Vector3<br>`t` float|Vector3|Spherically interpolates between two vectors\.|
| Vector 3 \| Sqr Magnitude |`vector` Vector3|float||

### [Vector4](https://docs.unity3d.com/ScriptReference/Vector4.html)

Representation of four\-dimensional vectors\.

| Property | Type | Description | Read? | Write? |
|----------|------|-------------|:-----:|:------:|
| Vector 4 \| Get Magnitude |float|Returns the length of this vector \(Read Only\)\.|yes|no|
| Vector 4 \| Get Negative Infinity |Vector4|Shorthand for writing Vector4\(float\.NegativeInfinity, float\.NegativeInfinity, float\.NegativeInfinity, float\.NegativeInfinity\)\.|yes|no|
| Vector 4 \| Get Normalized |Vector4|Returns this vector with a magnitude of 1 \(Read Only\)\.|yes|no|
| Vector 4 \| Get One |Vector4|Shorthand for writing Vector4\(1,1,1,1\)\.|yes|no|
| Vector 4 \| Get Positive Infinity |Vector4|Shorthand for writing Vector4\(float\.PositiveInfinity, float\.PositiveInfinity, float\.PositiveInfinity, float\.PositiveInfinity\)\.|yes|no|
| Vector 4 \| Get Sqr Magnitude |float|Returns the squared length of this vector \(Read Only\)\.|yes|no|
| Vector 4 \| Get W<br>Vector 4 \| Set W |float|W component of the vector\.|yes|yes|
| Vector 4 \| Get X<br>Vector 4 \| Set X |float|X component of the vector\.|yes|yes|
| Vector 4 \| Get Y<br>Vector 4 \| Set Y |float|Y component of the vector\.|yes|yes|
| Vector 4 \| Get Z<br>Vector 4 \| Set Z |float|Z component of the vector\.|yes|yes|
| Vector 4 \| Get Zero |Vector4|Shorthand for writing Vector4\(0,0,0,0\)\.|yes|no|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Vector 4 \| Create Vector 4|`x` float<br>`y` float|Vector4|Creates a new vector with given x, y components and sets z and w to zero\.|
| Vector 4 \| Create Vector 4|`x` float<br>`y` float<br>`z` float|Vector4|Creates a new vector with given x, y, z components and sets w to zero\.|
| Vector 4 \| Create Vector 4|`x` float<br>`y` float<br>`z` float<br>`w` float|Vector4|Creates a new vector with given x, y, z, w components\.|
| Vector 4 \| Distance |`a` Vector4<br>`b` Vector4|float|Returns the distance between a and b\.|
| Vector 4 \| Dot |`a` Vector4<br>`b` Vector4|float|Dot Product of two vectors\.|
| Vector 4 \| Equals |`other` Vector4|bool||
| Vector 4 \| Lerp |`a` Vector4<br>`b` Vector4<br>`t` float|Vector4|Linearly interpolates between two vectors\.|
|`LerpUnclamped`|`a` Vector4<br>`b` Vector4<br>`t` float|Vector4|Linearly interpolates between two vectors\.|Vector 4 \| Lerp Unclamped
| Vector 4 \| Magnitude |`a` Vector4|float||
| Vector 4 \| Max |`lhs` Vector4<br>`rhs` Vector4|Vector4|Returns a vector that is made from the largest components of two vectors\.|
| Vector 4 \| Min |`lhs` Vector4<br>`rhs` Vector4|Vector4|Returns a vector that is made from the smallest components of two vectors\.|
| Vector 4 \| Move Towards |`current` Vector4<br>`target` Vector4<br>`maxDistanceDelta` float|Vector4|Moves a point current towards target\.|
| Vector 4 \| Normalize |`a` Vector4|Vector4||
| Vector 4 \| Project |`a` Vector4<br>`b` Vector4|Vector4|Projects a vector onto another vector\.|
| Vector 4 \| Scale |`scale` Vector4|void|Multiplies every component of this vector by the same component of scale\.|
| Vector 4 \| Scale |`a` Vector4<br>`b` Vector4|Vector4|Multiplies two vectors component\-wise\.|
| Vector 4 \| Set |`newX` float<br>`newY` float<br>`newZ` float<br>`newW` float|void|Set x, y, z and w components of an existing Vector4\.|
| Vector 4 \| Sqr Magnitude ||float||
| Vector 4 \| Sqr Magnitude |`a` Vector4|float||
| Vector 4 \| To String |`format` string|string|Returns a formatted string for this vector\.|

## Other

### [AnimationCurve](https://docs.unity3d.com/ScriptReference/AnimationCurve.html)

Store a collection of Keyframes that can be evaluated over time\.

### [Debug](https://docs.unity3d.com/ScriptReference/Debug.html)

Class containing methods to ease debugging while developing a game\.

| Property | Type | Description | Read? | Write? |
|----------|------|-------------|:-----:|:------:|
| Debug \| Is Debug Build |bool|In the Build Settings dialog there is a check box called "Development Build"\.|yes|no|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Debug \| Draw Line |`start` Vector3<br>`end` Vector3|void|Draws a line between specified start and end points\.|
| Debug \| Draw Line |`start` Vector3<br>`end` Vector3<br>`color` Color|void|Draws a line between specified start and end points\.|
| Debug \| Draw Line |`start` Vector3<br>`end` Vector3<br>`color` Color<br>`duration` float|void|Draws a line between specified start and end points\.|
| Debug \| Draw Line |`start` Vector3<br>`end` Vector3<br>`color` Color<br>`duration` float<br>`depthTest` bool|void|Draws a line between specified start and end points\.|
| Debug \| Draw Ray |`start` Vector3<br>`dir` Vector3|void|Draws a line from start to start \+ dir in world coordinates\.|
| Debug \| Draw Ray |`start` Vector3<br>`dir` Vector3<br>`color` Color|void|Draws a line from start to start \+ dir in world coordinates\.|
| Debug \| Draw Ray |`start` Vector3<br>`dir` Vector3<br>`color` Color<br>`duration` float|void|Draws a line from start to start \+ dir in world coordinates\.|
| Debug \| Draw Ray |`start` Vector3<br>`dir` Vector3<br>`color` Color<br>`duration` float<br>`depthTest` bool|void|Draws a line from start to start \+ dir in world coordinates\.|
| Debug \| Log |`message` object|void|Logs a message to the Unity Console\.|
| Debug \| Log |`message` object<br>`context` Object|void|Logs a message to the Unity Console\.|
| Debug \| Log Error |`message` object|void|A variant of Debug\.Log that logs an error message to the console\.|
| Debug \| Log Error |`message` object<br>`context` Object|void|A variant of Debug\.Log that logs an error message to the console\.|
| Debug \| Log Warning |`message` object|void|A variant of Debug\.Log that logs a warning message to the console\.|
| Debug \| Log Warning |`message` object<br>`context` Object|void|A variant of Debug\.Log that logs a warning message to the console\.|

### [DynamicGI](https://docs.unity3d.com/ScriptReference/DynamicGI.html)

Allows to control the dynamic Global Illumination\.

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Dynamic GI \| Update Environment ||void|Schedules an update of the environment cubemap\.|

### [Material](https://docs.unity3d.com/ScriptReference/Material.html)

The material class\.

Supports additional properties and methods from UnityEngine\.Object.

| Property | Type | Description | Read? | Write? |
|----------|------|-------------|:-----:|:------:|
| Material \| Get Color<br>Material \| Set Color |Color|The main color of the Material\.|yes|yes|
| Material \| Get Main Texture Offset<br>Material \| Set Main Texture Offset |Vector2|The offset of the main texture\.|yes|yes|
| Material \| Get Main Texture Scale<br>Material \| Set Main Texture Scale |Vector2|The scale of the main texture\.|yes|yes|
| Material \| Get Shader<br>Material \| Set Shader |Shader|The shader used by the material\.|yes|yes|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Material \| Disable Keyword |`keyword` string|void|Disables a local shader keyword for this material\.|
| Material \| Enable Keyword |`keyword` string|void|Enables a local shader keyword for this material\.|
| Material \| Get Color |`name` string|Color|Get a named color value\.|
| Material \| Get Float |`name` string|float|Get a named float value\.|
| Material \| Get Integer |`name` string|int|Get a named integer value\.|
| Material \| Get Matrix |`name` string|Matrix4x4|Get a named matrix value from the shader\.|
| Material \| Get Texture |`name` string|Texture|Get a named texture\.|
| Material \| Get Texture Offset |`name` string|Vector2|Gets the placement offset of texture propertyName\.|
| Material \| Get Texture Scale |`name` string|Vector2|Gets the placement scale of texture propertyName\.|
| Material \| Get Vector |`name` string|Vector4|Get a named vector value\.|
| Material \| Has Color |`name` string|bool|Checks if the ShaderLab file assigned to the Material has a Color property with the given name\.|
| Material \| Has Float |`name` string|bool|Checks if the ShaderLab file assigned to the Material has a Float property with the given name\. This also works with the Float Array property\.|
| Material \| Has Integer |`name` string|bool|Checks if the ShaderLab file assigned to the Material has an Integer property with the given name\.|
| Material \| Has Matrix |`name` string|bool|Checks if the ShaderLab file assigned to the Material has a Matrix property with the given name\. This also works with the Matrix Array property\.|
| Material \| Has Property |`name` string|bool|Checks if the ShaderLab file assigned to the Material has a property with the given name\.|
|`HasTexture`|`name` string|bool|Checks if the ShaderLab file assigned to the Material has a Texture property with the given name\.|Material \| Has Texture
| Material \| Has Vector |`name` string|bool|Checks if the ShaderLab file assigned to the Material has a Vector property with the given name\. This also works with the Vector Array property\.|
| Material \| Is Keyword Enabled |`keyword` string|bool|Checks whether a local shader keyword is enabled for this material\.|
| Material \| Lerp |`start` Material<br>`end` Material<br>`t` float|void|Interpolate properties between two materials\.|
| Material \| Set Color |`name` string<br>`value` Color|void|Sets a color value\.|
| Material \| Set Float |`name` string<br>`value` float|void|Sets a named float value\.|
| Material \| Set Integer |`name` string<br>`value` int|void|Sets a named integer value\.|
| Material \| Set Matrix |`name` string<br>`value` Matrix4x4|void|Sets a named matrix for the shader\.|
| Material \| Set Override Tag |`tag` string<br>`val` string|void|Sets an override tag/value on the material\.|
| Material \| Set Texture |`name` string<br>`value` Texture|void|Sets a named texture\.|
| Material \| Set Texture Offset |`name` string<br>`value` Vector2|void|Sets the placement offset of a given texture\. The name parameter is defined in the shader\. This method creates a new Material instance\.|
| Material \| Set Texture Scale |`name` string<br>`value` Vector2|void|Sets the placement scale of texture propertyName\.|
| Material \| Set Vector |`name` string<br>`value` Vector4|void|Sets a named vector value\.|

### [MaterialPropertyBlock](https://docs.unity3d.com/ScriptReference/MaterialPropertyBlock.html)

A block of material values to apply\.

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
| Material Property Block \| Create Material Property Block ||MaterialPropertyBlock|

### [Mesh](https://docs.unity3d.com/ScriptReference/Mesh.html)

A class that allows you to create or modify meshes\.

Supports additional properties and methods from UnityEngine\.Object.

| Property | Type | Description | Read? | Write? |
|----------|------|-------------|:-----:|:------:|
| Mesh \| Get Bounds |Bounds|The bounding volume of the Mesh\.|yes|no|
| Mesh \| Is Readable |bool|Returns true if the Mesh is read/write enabled, or false if it is not\.|yes|no|
| Mesh \| Get Vertex Count |int|Returns the number of vertices in the Mesh \(Read Only\)\.|yes|no|

### [Object](https://docs.unity3d.com/ScriptReference/Object.html)

Base class for all objects Unity can reference\.

| Property | Type | Description | Read? | Write? |
|----------|------|-------------|:-----:|:------:|
| Unity Object \| Get Name |string|The name of the object\.|yes|no|

### [Random](https://docs.unity3d.com/ScriptReference/Random.html)

Easily generate random data for games\.

| Property | Type | Description | Read? | Write? |
|----------|------|-------------|:-----:|:------:|
| Random \| Get Inside Unit Circle |Vector2|Returns a random point inside or on a circle with radius 1\.0 \(Read Only\)\.|yes|no|
| Random \| Get Inside Unit Sphere |Vector3|Returns a random point inside or on a sphere with radius 1\.0 \(Read Only\)\.|yes|no|
| Random \| Get On Unit Sphere |Vector3|Returns a random point on the surface of a sphere with radius 1\.0 \(Read Only\)\.|yes|no|
| Random \| Get Rotation |Quaternion|Returns a random rotation \(Read Only\)\.|yes|no|
| Random \| Get Rotation Uniform |Quaternion|Returns a random rotation with uniform distribution \(Read Only\)\.|yes|no|
| Random \| Get Value |float|Returns a random float within \[0\.0\.\.1\.0\] \(range is inclusive\) \(Read Only\)\.|yes|no|

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Random \| Color HSV ||Color|Generates a random color from HSV and alpha ranges\.|
| Random \| Color HSV |`hueMin` float<br>`hueMax` float|Color|Generates a random color from HSV and alpha ranges\.|
| Random \| Color HSV |`hueMin` float<br>`hueMax` float<br>`saturationMin` float<br>`saturationMax` float|Color|Generates a random color from HSV and alpha ranges\.|
| Random \| Color HSV |`hueMin` float<br>`hueMax` float<br>`saturationMin` float<br>`saturationMax` float<br>`valueMin` float<br>`valueMax` float|Color|Generates a random color from HSV and alpha ranges\.|
| Random \| Color HSV |`hueMin` float<br>`hueMax` float<br>`saturationMin` float<br>`saturationMax` float<br>`valueMin` float<br>`valueMax` float<br>`alphaMin` float<br>`alphaMax` float|Color|Generates a random color from HSV and alpha ranges\.|
| Random \| Init State |`seed` int|void|Initializes the random number generator state with a seed\.|
| Random \| Range |`minInclusive` float<br>`maxInclusive` float|float|Returns a random float within \[minInclusive\.\.maxInclusive\] \(range is inclusive\)\.|
| Random \| Range |`minInclusive` int<br>`maxExclusive` int|int|Return a random int within \[minInclusive\.\.maxExclusive\) \(Read Only\)\.|

### [RenderSettings](https://docs.unity3d.com/ScriptReference/Experimental.GlobalIllumination.RenderSettings.html)

The Render Settings contain values for a range of visual elements in your Scene, like fog and ambient light\.

Supports additional properties and methods from UnityEngine\.Object.

| Property | Type | Description | Read? | Write? |
|----------|------|-------------|:-----:|:------:|
| Render Settings \| Get Ambient Equator Color<br>Render Settings \| Set Ambient Equator Color |Color|Ambient lighting coming from the sides\.|yes|yes|
| Render Settings \| Get Ambient Ground Color<br>Render Settings \| Set Ambient Ground Color |Color|Ambient lighting coming from below\.|yes|yes|
| Render Settings \| Get Ambient Intensity<br>Render Settings \| Set Ambient Intensity |float|How much the light from the Ambient Source affects the Scene\.|yes|yes|
| Render Settings \| Get Ambient Light<br>Render Settings \| Set Ambient Light |Color|Flat ambient lighting color\.|yes|yes|
| Render Settings \| Get Ambient Sky Color<br>Render Settings \| Set Ambient Sky Color |Color|Ambient lighting coming from above\.|yes|yes|
| Render Settings \| Get Skybox<br>Render Settings \| Set Skybox |Material|The global skybox to use\.|yes|yes|

### [Shader](https://docs.unity3d.com/ScriptReference/Shader.html)

Shader scripts used for all rendering\.

Supports additional properties and methods from UnityEngine\.Object.

| Nodes | Inputs | Outputs | Description |
|--------|------------|---------|-------------|
| Shader \| Disable Keyword |`keyword` string|void|Disables a global shader keyword\.|
| Shader \| Enable Keyword |`keyword` string|void|Enables a global shader keyword\.|
| Shader \| Find |`name` string|Shader|Finds a shader with the given name\. Returns null if the shader is not found\.|
| Shader \| Get Global Color |`name` string|Color|Gets a global color property for all shaders previously set using SetGlobalColor\.|
| Shader \| Get Global Float |`name` string|float|Gets a global float property for all shaders previously set using SetGlobalFloat\.|
| Shader \| Get Global Integer |`name` string|int|Gets a global integer property for all shaders previously set using SetGlobalInteger\.|
| Shader \| Get Global Matrix |`name` string|Matrix4x4|Gets a global matrix property for all shaders previously set using SetGlobalMatrix\.|
| Shader \| Get Global Texture |`name` string|Texture|Gets a global texture property for all shaders previously set using SetGlobalTexture\.|
| Shader \| Get Global Vector |`name` string|Vector4|Gets a global vector property for all shaders previously set using SetGlobalVector\.|
| Shader \| Is Keyword Enabled |`keyword` string|bool|Checks whether a global shader keyword is enabled\.|
| Shader \| Set Global Color |`name` string<br>`value` Color|void|Sets a global color property for all shaders\.|
| Shader \| Set Global Float |`name` string<br>`value` float|void|Sets a global float property for all shaders\.|
| Shader \| Set Global Integer |`name` string<br>`value` int|void|Sets a global integer property for all shaders\.|
| Shader \| Set Global Matrix |`name` string<br>`value` Matrix4x4|void|Sets a global matrix property for all shaders\.|
| Shader \| Set Global Texture |`name` string<br>`value` Texture|void|Sets a global texture property for all shaders\.|
| Shader \| Set Global Vector |`name` string<br>`value` Vector4|void|Sets a global vector property for all shaders\.|

### [TextAsset](https://docs.unity3d.com/ScriptReference/TextAsset.html)

Represents a raw text or binary file asset\.

Supports additional properties and methods from UnityEngine\.Object.

### [Texture](https://docs.unity3d.com/ScriptReference/Texture.html)

Base class for Texture handling\.

Supports additional properties and methods from UnityEngine\.Object.

### [Time](https://docs.unity3d.com/ScriptReference/Time.html)

Provides an interface to get time information from Unity\.

| Property | Type | Description | Read? | Write? |
|----------|------|-------------|:-----:|:------:|
| Time \| Get Delta Time |float|The interval in seconds from the last frame to the current one \(Read Only\)\.|yes|no|
| Time \| Get Fixed Delta Time |float|The interval in seconds at which physics and other fixed frame rate updates \(like MonoBehaviour's MonoBehaviour\.FixedUpdate\) are performed\.|yes|no|
| Time \| Get Fixed Time |float|The time since the last MonoBehaviour\.FixedUpdate started \(Read Only\)\. This is the time in seconds since the start of the game\.|yes|no|
| Time \| Get Fixed Unscaled Delta Time |float|The timeScale\-independent interval in seconds from the last MonoBehaviour\.FixedUpdate phase to the current one \(Read Only\)\.|yes|no|
| Time \| Get Fixed Unscaled Time |float|The timeScale\-independent time at the beginning of the last MonoBehaviour\.FixedUpdate phase \(Read Only\)\. This is the time in seconds since the start of the game\.|yes|no|
| Time \| Get Frame Count |int|The total number of frames since the start of the game \(Read Only\)\.|yes|no|
| Time \| Get In Fixed Time Step |bool|Returns true if called inside a fixed time step callback \(like MonoBehaviour's MonoBehaviour\.FixedUpdate\), otherwise returns false\.|yes|no|
| Time \| Get Realtime Since Startup |float|The real time in seconds since the game started \(Read Only\)\.|yes|no|
| Time \| Get Rendered Frame Count |int||yes|no|
| Time \| Get Smooth Delta Time |float|A smoothed out Time\.deltaTime \(Read Only\)\.|yes|no|
| Time \| Get Time |float|The time at the beginning of this frame \(Read Only\)\.|yes|no|
| Time \| Get Time Scale |float|The scale at which time passes\.|yes|no|
| Time \| Get Unscaled Delta Time |float|The timeScale\-independent interval in seconds from the last frame to the current one \(Read Only\)\.|yes|no|Time \| Get Unscaled Delta Time
| Time \| Get Unscaled Time |float|The timeScale\-independent time for this frame \(Read Only\)\. This is the time in seconds since the start of the game\.|yes|no|

## Enums

### RectTransform\.Axis

Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value |
|------|------:|
|`Horizontal`|0
|`Vertical`|1

### [RectTransform\.Edge](https://docs.unity3d.com/ScriptReference/RectTransform.Edge.html)

Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value |
|------|------:|
|`Left`|0
|`Right`|1
|`Top`|2
|`Bottom`|3

### [Space](https://docs.unity3d.com/ScriptReference/Space.html)

The coordinate space in which to operate\.

Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`World`|0|Applies transformation relative to the world coordinate system\.
|`Self`|1|Applies transformation relative to the local coordinate system\.

