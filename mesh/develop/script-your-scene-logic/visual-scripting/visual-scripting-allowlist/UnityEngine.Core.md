# UnityEngine\.Core

## Scene

### [UnityEngine\.Behaviour](https://docs.unity3d.com/ScriptReference/Behaviour.html)

Behaviours are Components that can be enabled or disabled\.

Supports additional properties and methods from UnityEngine\.Component and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`enabled`|bool|Enabled Behaviours are Updated, disabled Behaviours are not\.|yes|yes|yes|Behaviour \| Get Enabled<br>Behaviour \| Set Enabled
|`isActiveAndEnabled`|bool|Reports whether a GameObject and its associated Behaviour is active and enabled\.|yes|no|no|Behaviour \| Is Active And Enabled

### [UnityEngine\.Component](https://docs.unity3d.com/ScriptReference/Component.html)

Base class for everything attached to a GameObject\.

Supports additional properties and methods from UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`gameObject`|UnityEngine\.GameObject|The GameObject this component is attached to\. A component is always attached to a GameObject\.|yes|no|no|Component \| Get Game Object
|`tag`|string|The tag of this GameObject\.|yes|no|no|Component \| Get Tag
|`transform`|UnityEngine\.Transform|The Transform attached to this GameObject\.|yes|no|no|Component \| Get Transform

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`GetComponent`|`type` System\.Type|UnityEngine\.Component|The non\-generic version of this method\.|Component \| Get Component
|`GetComponentInChildren`|`t` System\.Type|UnityEngine\.Component|This is the non\-generic version of this method\.|Component \| Get Component In Children
|`GetComponentInChildren`|`t` System\.Type<br>`includeInactive` bool|UnityEngine\.Component|This is the non\-generic version of this method\.|Component \| Get Component In Children
|`GetComponentInParent`|`t` System\.Type|UnityEngine\.Component|The non\-generic version of this method\.|Component \| Get Component In Parent
|`GetComponentInParent`|`t` System\.Type<br>`includeInactive` bool|UnityEngine\.Component|The non\-generic version of this method\.|Component \| Get Component In Parent
|`GetComponents`|`type` System\.Type|UnityEngine\.Component\[\]|The non\-generic version of this method\.|Component \| Get Components
|`GetComponentsInChildren`|`t` System\.Type|UnityEngine\.Component\[\]||Component \| Get Components In Children
|`GetComponentsInChildren`|`t` System\.Type<br>`includeInactive` bool|UnityEngine\.Component\[\]|The non\-generic version of this method\.|Component \| Get Components In Children
|`GetComponentsInParent`|`t` System\.Type|UnityEngine\.Component\[\]||Component \| Get Components In Parent
|`GetComponentsInParent`|`t` System\.Type<br>`includeInactive` bool|UnityEngine\.Component\[\]|The non\-generic version of this method\.|Component \| Get Components In Parent

### [UnityEngine\.GameObject](https://docs.unity3d.com/ScriptReference/GameObject.html)

Base class for all entities in Unity Scenes\.

Supports additional properties and methods from UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`activeInHierarchy`|bool|Defines whether the GameObject is active in the Scene\.|yes|no|no|Game Object \| Get Active In Hierarchy
|`activeSelf`|bool|The local active state of this GameObject\. \(Read Only\)|yes|no|no|Game Object \| Get Active Self
|`isStatic`|bool|Gets and sets the GameObject's StaticEditorFlags\.|yes|no|no|Game Object \| Is Static
|`tag`|string|The tag of this GameObject\.|yes|no|no|Game Object \| Get Tag
|`transform`|UnityEngine\.Transform|The Transform attached to this GameObject\.|yes|no|no|Game Object \| Get Transform

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`GetComponent`|`type` System\.Type|UnityEngine\.Component|The non\-generic version of this method\.|Game Object \| Get Component
|`GetComponentInChildren`|`type` System\.Type|UnityEngine\.Component|This is the non\-generic version of this method\.|Game Object \| Get Component In Children
|`GetComponentInChildren`|`type` System\.Type<br>`includeInactive` bool|UnityEngine\.Component|This is the non\-generic version of this method\.|Game Object \| Get Component In Children
|`GetComponentInParent`|`type` System\.Type|UnityEngine\.Component|The non\-generic version of this method\.|Game Object \| Get Component In Parent
|`GetComponentInParent`|`type` System\.Type<br>`includeInactive` bool|UnityEngine\.Component|The non\-generic version of this method\.|Game Object \| Get Component In Parent
|`GetComponents`|`type` System\.Type|UnityEngine\.Component\[\]|The non\-generic version of this method\.|Game Object \| Get Components
|`GetComponentsInChildren`|`type` System\.Type|UnityEngine\.Component\[\]|The non\-generic version of this method\.|Game Object \| Get Components In Children
|`GetComponentsInChildren`|`type` System\.Type<br>`includeInactive` bool|UnityEngine\.Component\[\]|The non\-generic version of this method\.|Game Object \| Get Components In Children
|`GetComponentsInParent`|`type` System\.Type|UnityEngine\.Component\[\]||Game Object \| Get Components In Parent
|`GetComponentsInParent`|`type` System\.Type<br>`includeInactive` bool|UnityEngine\.Component\[\]|The non\-generic version of this method\.|Game Object \| Get Components In Parent
|`SetActive`|`value` bool|void|ActivatesDeactivates the GameObject, depending on the given true or false/ value\.|Game Object \| Set Active

### [UnityEngine\.Light](https://docs.unity3d.com/ScriptReference/Light.html)

Script interface for light components.

Supports additional properties and methods from UnityEngine\.Behaviour, UnityEngine\.Component, and UnityEngine\.Object.

### [UnityEngine\.LineRenderer](https://docs.unity3d.com/ScriptReference/LineRenderer.html)

The line renderer is used to draw free\-floating lines in 3D space\.

Supports additional properties and methods from UnityEngine\.Renderer, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`positionCount`|int|Set/get the number of vertices\.|yes|yes|no|Line Renderer \| Get Position Count<br>Line Renderer \| Set Position Count

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`GetPosition`|`index` int|UnityEngine\.Vector3|Get the position of a vertex in the line\.|Line Renderer \| Get Position
|`GetPositions`|`positions` UnityEngine\.Vector3\[\]|int||Line Renderer \| Get Positions
|`SetPosition`|`index` int<br>`position` UnityEngine\.Vector3|void|Set the position of a vertex in the line\.|Line Renderer \| Set Position
|`SetPositions`|`positions` UnityEngine\.Vector3\[\]|void|Set the positions of all vertices in the line\.|Line Renderer \| Set Positions

### [UnityEngine\.MeshFilter](https://docs.unity3d.com/ScriptReference/MeshFilter.html)

A class to access the Mesh of the\.

Supports additional properties and methods from UnityEngine\.Component and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`mesh`|UnityEngine\.Mesh|Returns either a new Mesh\|mesh or a duplicate of the existing mesh, and assigns it to the mesh filter\.|yes|yes|no|Mesh Filter \| Get Mesh<br>Mesh Filter \| Set Mesh
|`sharedMesh`|UnityEngine\.Mesh|Returns the shared mesh of the mesh filter\.|yes|no|no|Mesh Filter \| Get Shared Mesh

### [UnityEngine\.MeshRenderer](https://docs.unity3d.com/ScriptReference/MeshRenderer.html)

Renders meshes inserted by the MeshFilter or TextMesh\.

Supports additional properties and methods from UnityEngine\.Renderer, UnityEngine\.Component, and UnityEngine\.Object.

### [UnityEngine\.RectTransform](https://docs.unity3d.com/ScriptReference/RectTransform.html)

Position, size, anchor and pivot information for a rectangle\.

Supports additional properties and methods from UnityEngine\.Transform, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`anchoredPosition`|UnityEngine\.Vector2|The position of the pivot of this RectTransform relative to the anchor reference point\.|yes|no|no|Rect Transform \| Get Anchored Position
|`anchoredPosition3D`|UnityEngine\.Vector3|The 3D position of the pivot of this RectTransform relative to the anchor reference point\.|yes|no|no|Rect Transform \| Get Anchored Position 3D
|`anchorMax`|UnityEngine\.Vector2|The normalized position in the parent RectTransform that the upper right corner is anchored to\.|yes|no|no|Rect Transform \| Get Anchor Max
|`anchorMin`|UnityEngine\.Vector2|The normalized position in the parent RectTransform that the lower left corner is anchored to\.|yes|no|no|Rect Transform \| Get Anchor Min
|`drivenByObject`|UnityEngine\.Object|The object that is driving the values of this RectTransform\. Value is null if not driven\.|yes|no|no|Rect Transform \| Get Driven By Object
|`offsetMax`|UnityEngine\.Vector2|The offset of the upper right corner of the rectangle relative to the upper right anchor\.|yes|no|no|Rect Transform \| Get Offset Max
|`offsetMin`|UnityEngine\.Vector2|The offset of the lower left corner of the rectangle relative to the lower left anchor\.|yes|no|no|Rect Transform \| Get Offset Min
|`pivot`|UnityEngine\.Vector2|The normalized position in this RectTransform that it rotates around\.|yes|no|no|Rect Transform \| Get Pivot
|`rect`|UnityEngine\.Rect|The calculated rectangle in the local space of the Transform\.|yes|no|no|Rect Transform \| Get Rect
|`sizeDelta`|UnityEngine\.Vector2|The size of this RectTransform relative to the distances between the anchors\.|yes|no|no|Rect Transform \| Get Size Delta

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`ForceUpdateRectTransforms`||void|Force the recalculation of RectTransforms internal data\.|Rect Transform \| Force Update Rect Transforms
|`SetInsetAndSizeFromParentEdge`|`edge` UnityEngine\.RectTransform\.Edge<br>`inset` float<br>`size` float|void||Rect Transform \| Set Inset And Size From Parent Edge
|`SetSizeWithCurrentAnchors`|`axis` UnityEngine\.RectTransform\.Axis<br>`size` float|void||Rect Transform \| Set Size With Current Anchors

### [UnityEngine\.Renderer](https://docs.unity3d.com/ScriptReference/Renderer.html)

General functionality for all renderers\.

Supports additional properties and methods from UnityEngine\.Component and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`bounds`|UnityEngine\.Bounds|The bounding box of the renderer in world space\.|yes|yes|no|Renderer \| Get Bounds<br>Renderer \| Set Bounds
|`enabled`|bool|Makes the rendered 3D object visible if enabled\.|yes|yes|yes|Renderer \| Get Enabled<br>Renderer \| Set Enabled
|`isVisible`|bool|Is this renderer visible in any camera? \(Read Only\)|yes|no|no|Renderer \| Is Visible
|`localBounds`|UnityEngine\.Bounds|The bounding box of the renderer in local space\.|yes|yes|no|Renderer \| Get Local Bounds<br>Renderer \| Set Local Bounds
|`localToWorldMatrix`|UnityEngine\.Matrix4x4|Matrix that transforms a point from local space into world space \(Read Only\)\.|yes|no|no|Renderer \| Get Local To World Matrix
|`material`|UnityEngine\.Material|Returns the first instantiated Material assigned to the renderer\.|yes|yes|no|Renderer \| Get Material<br>Renderer \| Set Material
|`sharedMaterial`|UnityEngine\.Material|The shared material of this object\.|yes|no|no|Renderer \| Get Shared Material
|`worldToLocalMatrix`|UnityEngine\.Matrix4x4|Matrix that transforms a point from world space into local space \(Read Only\)\.|yes|no|no|Renderer \| Get World To Local Matrix

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`SetPropertyBlock`|`properties` UnityEngine\.MaterialPropertyBlock|void|Lets you set or clear per\-renderer or per\-material parameter overrides\.|Renderer \| Set Property Block
|`SetPropertyBlock`|`properties` UnityEngine\.MaterialPropertyBlock<br>`materialIndex` int|void|Lets you set or clear per\-renderer or per\-material parameter overrides\.|Renderer \| Set Property Block

### [UnityEngine\.TrailRenderer](https://docs.unity3d.com/ScriptReference/TrailRenderer.html)

The trail renderer is used to make trails behind objects in the Scene as they move about\.

Supports additional properties and methods from UnityEngine\.Renderer, UnityEngine\.Component, and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`emitting`|bool|Creates trails when the GameObject moves\.|yes|yes|yes|Trail Renderer \| Get Emitting<br>Trail Renderer \| Set Emitting

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`AddPosition`|`position` UnityEngine\.Vector3|void|Adds a position to the trail\.|Trail Renderer \| Add Position
|`AddPositions`|`positions` UnityEngine\.Vector3\[\]|void|Add an array of positions to the trail\.|Trail Renderer \| Add Positions
|`GetPosition`|`index` int|UnityEngine\.Vector3|Get the position of a vertex in the trail\.|Trail Renderer \| Get Position
|`GetPositions`|`positions` UnityEngine\.Vector3\[\]|int||Trail Renderer \| Get Positions
|`SetPosition`|`index` int<br>`position` UnityEngine\.Vector3|void|Set the position of a vertex in the trail\.|Trail Renderer \| Set Position
|`SetPositions`|`positions` UnityEngine\.Vector3\[\]|void|Sets the positions of all vertices in the trail\.|Trail Renderer \| Set Positions

### [UnityEngine\.Transform](https://docs.unity3d.com/ScriptReference/Transform.html)

Position, rotation and scale of an object\.

Supports additional properties and methods from UnityEngine\.Component and UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Share? | Script |
|----------|------|-------------|:-----:|:------:|:------:|--------|
|`childCount`|int|The number of children the parent Transform has\.|yes|no|no|Transform \| Get Child Count
|`eulerAngles`|UnityEngine\.Vector3|The rotation as Euler angles in degrees\.|yes|yes|yes|Transform \| Get Euler Angles<br>Transform \| Set Euler Angles
|`forward`|UnityEngine\.Vector3|Returns a normalized vector representing the blue axis of the transform in world space\.|yes|yes|yes|Transform \| Get Forward<br>Transform \| Set Forward
|`localEulerAngles`|UnityEngine\.Vector3|The rotation as Euler angles in degrees relative to the parent transform's rotation\.|yes|yes|yes|Transform \| Get Local Euler Angles<br>Transform \| Set Local Euler Angles
|`localPosition`|UnityEngine\.Vector3|Position of the transform relative to the parent transform\.|yes|yes|yes|Transform \| Get Local Position<br>Transform \| Set Local Position
|`localRotation`|UnityEngine\.Quaternion|The rotation of the transform relative to the transform rotation of the parent\.|yes|yes|yes|Transform \| Get Local Rotation<br>Transform \| Set Local Rotation
|`localScale`|UnityEngine\.Vector3|The scale of the transform relative to the GameObjects parent\.|yes|yes|yes|Transform \| Get Local Scale<br>Transform \| Set Local Scale
|`localToWorldMatrix`|UnityEngine\.Matrix4x4|Matrix that transforms a point from local space into world space. \(Read Only\)\.|yes|no|yes|Transform \| Get Local To World Matrix
|`lossyScale`|UnityEngine\.Vector3|The global scale of the object \(Read Only\)\.|yes|no|yes|Transform \| Get Lossy Scale
|`parent`|UnityEngine\.Transform|The parent of the transform\.|yes|no|no|Transform \| Get Parent
|`position`|UnityEngine\.Vector3|The world space position of the Transform\.|yes|yes|yes|Transform \| Get Position<br>Transform \| Set Position
|`right`|UnityEngine\.Vector3|The red axis of the transform in world space\.|yes|yes|yes|Transform \| Get Right<br>Transform \| Set Right
|`root`|UnityEngine\.Transform|Returns the topmost transform in the hierarchy\.|yes|no|no|Transform \| Get Root
|`rotation`|UnityEngine\.Quaternion|A Quaternion that stores the rotation of the Transform in world space\.|yes|yes|yes|Transform \| Get Rotation<br>Transform \| Set Rotation
|`up`|UnityEngine\.Vector3|The green axis of the transform in world space\.|yes|yes|yes|Transform \| Get Up<br>Transform \| Set Up
|`worldToLocalMatrix`|UnityEngine\.Matrix4x4|Matrix that transforms a point from world space into local space \(Read Only\)\.|yes|no|yes|Transform \| Get World To Local Matrix

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`Find`|`n` string|UnityEngine\.Transform|Finds a child by name n and returns it\.|Transform \| Find
|`GetChild`|`index` int|UnityEngine\.Transform|Returns a transform child by index\.|Transform \| Get Child
|`GetSiblingIndex`||int|Gets the sibling index\.|Transform \| Get Sibling Index
|`InverseTransformDirection`|`x` float<br>`y` float<br>`z` float|UnityEngine\.Vector3|Transforms the direction x, y, z from world space to local space\. The opposite of Transform\.TransformDirection\.|Transform \| Inverse Transform Direction
|`InverseTransformDirection`|`direction` UnityEngine\.Vector3|UnityEngine\.Vector3|Transforms a direction from world space to local space\. The opposite of Transform\.TransformDirection\.|Transform \| Inverse Transform Direction
|`InverseTransformPoint`|`x` float<br>`y` float<br>`z` float|UnityEngine\.Vector3|Transforms the position x, y, z from world space to local space\.|Transform \| Inverse Transform Point
|`InverseTransformPoint`|`position` UnityEngine\.Vector3|UnityEngine\.Vector3|Transforms position from world space to local space\.|Transform \| Inverse Transform Point
|`InverseTransformVector`|`x` float<br>`y` float<br>`z` float|UnityEngine\.Vector3|Transforms the vector x, y, z from world space to local space\. The opposite of Transform\.TransformVector\.|Transform \| Inverse Transform Vector
|`InverseTransformVector`|`vector` UnityEngine\.Vector3|UnityEngine\.Vector3|Transforms a vector from world space to local space\. The opposite of Transform\.TransformVector\.|Transform \| Inverse Transform Vector
|`IsChildOf`|`parent` UnityEngine\.Transform|bool|Is this transform a child of parent?|Transform \| Is Child Of
|`LookAt`|`target` UnityEngine\.Transform|void|Rotates the transform so the forward vector points at target's current position\.|Transform \| Look At
|`LookAt`|`target` UnityEngine\.Transform<br>`worldUp` UnityEngine\.Vector3|void|Rotates the transform so the forward vector points at target's current position\.|Transform \| Look At
|`LookAt`|`worldPosition` UnityEngine\.Vector3|void|Rotates the transform so the forward vector points at worldPosition\.|Transform \| Look At
|`LookAt`|`worldPosition` UnityEngine\.Vector3<br>`worldUp` UnityEngine\.Vector3|void|Rotates the transform so the forward vector points at worldPosition\.|Transform \| Look At
|`Rotate`|`xAngle` float<br>`yAngle` float<br>`zAngle` float|void|The implementation of this method applies a rotation of zAngle degrees around the z axis, xAngle degrees around the x axis, and yAngle degrees around the y axis \(in that order\)\.|Transform \| Rotate
|`Rotate`|`xAngle` float<br>`yAngle` float<br>`zAngle` float<br>`relativeTo` UnityEngine\.Space|void|The implementation of this method applies a rotation of zAngle degrees around the z axis, xAngle degrees around the x axis, and yAngle degrees around the y axis \(in that order\)\.|Transform \| Rotate
|`Rotate`|`eulers` UnityEngine\.Vector3|void|Applies a rotation of eulerAngles\.z degrees around the z\-axis, eulerAngles\.x degrees around the x\-axis, and eulerAngles\.y degrees around the y\-axis \(in that order\)\.|Transform \| Rotate
|`Rotate`|`axis` UnityEngine\.Vector3<br>`angle` float|void|Rotates the object around the given axis by the number of degrees defined by the given angle\.|Transform \| Rotate
|`Rotate`|`axis` UnityEngine\.Vector3<br>`angle` float<br>`relativeTo` UnityEngine\.Space|void|Rotates the object around the given axis by the number of degrees defined by the given angle\.|Transform \| Rotate
|`Rotate`|`eulers` UnityEngine\.Vector3<br>`relativeTo` UnityEngine\.Space|void|Applies a rotation of eulerAngles\.z degrees around the z\-axis, eulerAngles\.x degrees around the x\-axis, and eulerAngles\.y degrees around the y\-axis \(in that order\)\.|Transform \| Rotate
|`RotateAround`|`point` UnityEngine\.Vector3<br>`axis` UnityEngine\.Vector3<br>`angle` float|void|Rotates the transform about axis passing through point in world coordinates by angle degrees\.|Transform \| Rotate Around
|`TransformDirection`|`x` float<br>`y` float<br>`z` float|UnityEngine\.Vector3|Transforms direction x, y, z from local space to world space\.|Transform \| Transform Direction
|`TransformDirection`|`direction` UnityEngine\.Vector3|UnityEngine\.Vector3|Transforms direction from local space to world space\.|Transform \| Transform Direction
|`TransformPoint`|`x` float<br>`y` float<br>`z` float|UnityEngine\.Vector3|Transforms the position x, y, z from local space to world space\.|Transform \| Transform Point
|`TransformPoint`|`position` UnityEngine\.Vector3|UnityEngine\.Vector3|Transforms position from local space to world space\.|Transform \| Transform Point
|`TransformVector`|`x` float<br>`y` float<br>`z` float|UnityEngine\.Vector3|Transforms vector x, y, z from local space to world space\.|Transform \| Transform Vector
|`TransformVector`|`vector` UnityEngine\.Vector3|UnityEngine\.Vector3|Transforms vector from local space to world space\.|Transform \| Transform Vector
|`Translate`|`x` float<br>`y` float<br>`z` float|void|Moves the transform by x along the x axis, y along the y axis, and z along the z axis\.|Transform \| Translate
|`Translate`|`x` float<br>`y` float<br>`z` float<br>`relativeTo` UnityEngine\.Space|void|Moves the transform by x along the x axis, y along the y axis, and z along the z axis\.|Transform \| Translate
|`Translate`|`x` float<br>`y` float<br>`z` float<br>`relativeTo` UnityEngine\.Transform|void|Moves the transform by x along the x axis, y along the y axis, and z along the z axis\.|Transform \| Translate
|`Translate`|`translation` UnityEngine\.Vector3|void|Moves the transform in the direction and distance of translation\.|Transform \| Translate
|`Translate`|`translation` UnityEngine\.Vector3<br>`relativeTo` UnityEngine\.Space|void|Moves the transform in the direction and distance of translation\.|Transform \| Translate
|`Translate`|`translation` UnityEngine\.Vector3<br>`relativeTo` UnityEngine\.Transform|void|Moves the transform in the direction and distance of translation\.|Transform \| Translate

## Structs

### [UnityEngine\.Bounds](https://docs.unity3d.com/ScriptReference/Bounds.html)

Represents an axis aligned bounding box\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`center`|UnityEngine\.Vector3|The center of the bounding box\.|yes|yes|Bounds \| Get Center<br>Bounds \| Set Center
|`extents`|UnityEngine\.Vector3|The extents of the Bounding Box\. This is always half of the size of the Bounds\.|yes|yes|Bounds \| Get Extents<br>Bounds \| Set Extents
|`max`|UnityEngine\.Vector3|The maximal point of the box\. This is always equal to center\+extents\.|yes|yes|Bounds \| Get Max<br>Bounds \| Set Max
|`min`|UnityEngine\.Vector3|The minimal point of the box\. This is always equal to center\-extents\.|yes|yes|Bounds \| Get Min<br>Bounds \| Set Min
|`size`|UnityEngine\.Vector3|The total size of the box\. This is always twice as large as the extents\.|yes|yes|Bounds \| Get Size<br>Bounds \| Set Size

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`Bounds`|`center` UnityEngine\.Vector3<br>`size` UnityEngine\.Vector3|UnityEngine\.Bounds|Creates a new Bounds\.|Bounds \| Create Bounds
|`ClosestPoint`|`point` UnityEngine\.Vector3|UnityEngine\.Vector3|The closest point on the bounding box\.|Bounds \| Closest Point
|`Contains`|`point` UnityEngine\.Vector3|bool|Is point contained in the bounding box?|Bounds \| Contains
|`Encapsulate`|`bounds` UnityEngine\.Bounds|void|Grow the bounds to encapsulate the bounds\.|Bounds \| Encapsulate
|`Encapsulate`|`point` UnityEngine\.Vector3|void|Grows the Bounds to include the point\.|Bounds \| Encapsulate
|`Expand`|`amount` float|void|Expand the bounds by increasing its size by amount along each side\.|Bounds \| Expand
|`Expand`|`amount` UnityEngine\.Vector3|void|Expand the bounds by increasing its size by amount along each side\.|Bounds \| Expand
|`IntersectRay`|`ray` UnityEngine\.Ray|bool|Does ray intersect this bounding box?|Bounds \| Intersect Ray
|`Intersects`|`bounds` UnityEngine\.Bounds|bool|Does another bounding box intersect with this bounding box?|Bounds \| Intersects
|`SetMinMax`|`min` UnityEngine\.Vector3<br>`max` UnityEngine\.Vector3|void|Sets the bounds to the min and max value of the box\.|Bounds \| Set Min Max
|`SqrDistance`|`point` UnityEngine\.Vector3|float|The smallest squared distance between the point and this bounding box\.|Bounds \| Sqr Distance

### [UnityEngine\.Color](https://docs.unity3d.com/ScriptReference/Color.html)

Representation of RGBA colors\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`a`|float|Alpha component of the color \(0 is transparent, 1 is opaque\)\.|yes|yes|Color \| Get A<br>Color \| Set A
|`b`|float|Blue component of the color\.|yes|yes|Color \| Get B<br>Color \| Set B
|`g`|float|Green component of the color\.|yes|yes|Color \| Get G<br>Color \| Set G
|`gamma`|UnityEngine\.Color|A version of the color that has had the gamma curve applied\.|yes|no|Color \| Get Gamma
|`grayscale`|float|The grayscale value of the color\. \(Read Only\)|yes|no|Color \| Get Grayscale
|`linear`|UnityEngine\.Color|A linear value of an sRGB color\.|yes|no|Color \| Get Linear
|`maxColorComponent`|float|Returns the maximum color component value: Max\(r,g,b\)\.|yes|no|Color \| Get Max Color Component
|`r`|float|Red component of the color\.|yes|yes|Color \| Get R<br>Color \| Set R

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`Color`|`r` float<br>`g` float<br>`b` float|UnityEngine\.Color|Constructs a new Color with given r,g,b components and sets a to 1\.|Color \| Create Color
|`Color`|`r` float<br>`g` float<br>`b` float<br>`a` float|UnityEngine\.Color|Constructs a new Color with given r,g,b,a components\.|Color \| Create Color
|`Equals`|`other` UnityEngine\.Color|bool||Color \| Equals
|`HSVToRGB`|`H` float<br>`S` float<br>`V` float|UnityEngine\.Color|Creates an RGB colour from HSV input\.|Color \| HSV To RGB
|`HSVToRGB`|`H` float<br>`S` float<br>`V` float<br>`hdr` bool|UnityEngine\.Color|Creates an RGB colour from HSV input\.|Color \| HSV To RGB
|`Lerp`|`a` UnityEngine\.Color<br>`b` UnityEngine\.Color<br>`t` float|UnityEngine\.Color|Linearly interpolates between colors a and b by t\.|Color \| Lerp
|`LerpUnclamped`|`a` UnityEngine\.Color<br>`b` UnityEngine\.Color<br>`t` float|UnityEngine\.Color|Linearly interpolates between colors a and b by t\.|Color \| Lerp Unclamped

### [UnityEngine\.Mathf](https://docs.unity3d.com/ScriptReference/Mathf.html)

A collection of common math functions\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`Deg2Rad`|float|Degrees\-to\-radians conversion constant \(Read Only\)\.|yes|no|Mathf \| Get Deg 2 Rad
|`Epsilon`|float|A tiny floating point value \(Read Only\)\.|yes|no|Mathf \| Get Epsilon
|`Infinity`|float|A representation of positive infinity \(Read Only\)\.|yes|no|Mathf \| Get Infinity
|`NegativeInfinity`|float|A representation of negative infinity \(Read Only\)\.|yes|no|Mathf \| Get Negative Infinity
|`PI`|float|The well\-known 3\.14159265358979\.\.\. value \(Read Only\)\.|yes|no|Mathf \| Get PI
|`Rad2Deg`|float|Radians\-to\-degrees conversion constant \(Read Only\)\.|yes|no|Mathf \| Get Rad 2 Deg

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`Abs`|`f` float|float|Returns the absolute value of f\.|Mathf \| Abs
|`Abs`|`value` int|int|Returns the absolute value of value\.|Mathf \| Abs
|`Acos`|`f` float|float|Returns the arc\-cosine of f \- the angle in radians whose cosine is f\.|Mathf \| Acos
|`Approximately`|`a` float<br>`b` float|bool|Compares two floating point values and returns true if they are similar\.|Mathf \| Approximately
|`Asin`|`f` float|float|Returns the arc\-sine of f \- the angle in radians whose sine is f\.|Mathf \| Asin
|`Atan`|`f` float|float|Returns the arc\-tangent of f \- the angle in radians whose tangent is f\.|Mathf \| Atan
|`Atan2`|`y` float<br>`x` float|float|Returns the angle in radians whose Tan is y/x\.|Mathf \| Atan 2
|`Ceil`|`f` float|float|Returns the smallest integer greater to or equal to f\.|Mathf \| Ceil
|`CeilToInt`|`f` float|int|Returns the smallest integer greater to or equal to f\.|Mathf \| Ceil To Int
|`Clamp`|`value` float<br>`min` float<br>`max` float|float|Clamps the given value between the given minimum float and maximum float values\. Returns the given value if it is within the minimum and maximum range\.|Mathf \| Clamp
|`Clamp`|`value` int<br>`min` int<br>`max` int|int|Clamps the given value between a range defined by the given minimum integer and maximum integer values\. Returns the given value if it is within min and max\.|Mathf \| Clamp
|`Clamp01`|`value` float|float|Clamps value between 0 and 1 and returns value\.|Mathf \| Clamp 01
|`ClosestPowerOfTwo`|`value` int|int|Returns the closest power of two value\.|Mathf \| Closest Power Of Two
|`CorrelatedColorTemperatureToRGB`|`kelvin` float|UnityEngine\.Color|Convert a color temperature in Kelvin to RGB color\.|Mathf \| Correlated Color Temperature To RGB
|`Cos`|`f` float|float|Returns the cosine of angle f\.|Mathf \| Cos
|`DeltaAngle`|`current` float<br>`target` float|float|Calculates the shortest difference between two given angles given in degrees\.|Mathf \| Delta Angle
|`Exp`|`power` float|float|Returns e raised to the specified power\.|Mathf \| Exp
|`Floor`|`f` float|float|Returns the largest integer smaller than or equal to f\.|Mathf \| Floor
|`FloorToInt`|`f` float|int|Returns the largest integer smaller to or equal to f\.|Mathf \| Floor To Int
|`Gamma`|`value` float<br>`absmax` float<br>`gamma` float|float||Mathf \| Gamma
|`GammaToLinearSpace`|`value` float|float|Converts the given value from gamma \(sRGB\) to linear color space\.|Mathf \| Gamma To Linear Space
|`InverseLerp`|`a` float<br>`b` float<br>`value` float|float|Determines where a value lies between two points\.|Mathf \| Inverse Lerp
|`IsPowerOfTwo`|`value` int|bool|Returns true if the value is power of two\.|Mathf \| Is Power Of Two
|`Lerp`|`a` float<br>`b` float<br>`t` float|float|Linearly interpolates between a and b by t\.|Mathf \| Lerp
|`LerpAngle`|`a` float<br>`b` float<br>`t` float|float|Same as Lerp but makes sure the values interpolate correctly when they wrap around 360 degrees\.|Mathf \| Lerp Angle
|`LerpUnclamped`|`a` float<br>`b` float<br>`t` float|float|Linearly interpolates between a and b by t with no limit to t\.|Mathf \| Lerp Unclamped
|`LinearToGammaSpace`|`value` float|float|Converts the given value from linear to gamma \(sRGB\) color space\.|Mathf \| Linear To Gamma Space
|`Log`|`f` float|float|Returns the natural \(base e\) logarithm of a specified number\.|Mathf \| Log
|`Log`|`f` float<br>`p` float|float|Returns the logarithm of a specified number in a specified base\.|Mathf \| Log
|`Log10`|`f` float|float|Returns the base 10 logarithm of a specified number\.|Mathf \| Log 10
|`Max`|`a` float<br>`b` float|float|Returns largest of two or more values\.|Mathf \| Max
|`Max`|`a` int<br>`b` int|int|Returns the largest of two or more values\.|Mathf \| Max
|`Min`|`a` float<br>`b` float|float|Returns the smallest of two or more values\.|Mathf \| Min
|`Min`|`a` int<br>`b` int|int|Returns the smallest of two or more values\.|Mathf \| Min
|`MoveTowards`|`current` float<br>`target` float<br>`maxDelta` float|float|Moves a value current towards target\.|Mathf \| Move Towards
|`MoveTowardsAngle`|`current` float<br>`target` float<br>`maxDelta` float|float|Same as MoveTowards but makes sure the values interpolate correctly when they wrap around 360 degrees\.|Mathf \| Move Towards Angle
|`NextPowerOfTwo`|`value` int|int|Returns the next power of two that is equal to, or greater than, the argument\.|Mathf \| Next Power Of Two
|`PerlinNoise`|`x` float<br>`y` float|float|Generate 2D Perlin noise\.|Mathf \| Perlin Noise
|`PingPong`|`t` float<br>`length` float|float|PingPong returns a value that will increment and decrement between the value 0 and length\.|Mathf \| Ping Pong
|`Pow`|`f` float<br>`p` float|float|Returns f raised to power p\.|Mathf \| Pow
|`Repeat`|`t` float<br>`length` float|float|Loops the value t, so that it is never larger than length and never smaller than 0\.|Mathf \| Repeat
|`Round`|`f` float|float|Returns f rounded to the nearest integer\.|Mathf \| Round
|`RoundToInt`|`f` float|int|Returns f rounded to the nearest integer\.|Mathf \| Round To Int
|`Sign`|`f` float|float|Returns the sign of f\.|Mathf \| Sign
|`Sin`|`f` float|float|Returns the sine of angle f\.|Mathf \| Sin
|`SmoothStep`|`from` float<br>`to` float<br>`t` float|float|Interpolates between min and max with smoothing at the limits\.|Mathf \| Smooth Step
|`Sqrt`|`f` float|float|Returns square root of f\.|Mathf \| Sqrt
|`Tan`|`f` float|float|Returns the tangent of angle f in radians\.|Mathf \| Tan

### [UnityEngine\.Matrix4x4](https://docs.unity3d.com/ScriptReference/Matrix4x4.html)

A standard 4x4 transformation matrix\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`determinant`|float|The determinant of the matrix\. \(Read Only\)|yes|no|Matrix 4x 4 \| Get Determinant
|`identity`|UnityEngine\.Matrix4x4|Returns the identity matrix \(Read Only\)\.|yes|no|Matrix 4x 4 \| Get Identity
|`inverse`|UnityEngine\.Matrix4x4|The inverse of this matrix\. \(Read Only\)|yes|no|Matrix 4x 4 \| Get Inverse
|`isIdentity`|bool|Checks whether this is an identity matrix\. \(Read Only\)|yes|no|Matrix 4x 4 \| Is Identity
|`lossyScale`|UnityEngine\.Vector3|Attempts to get a scale value from the matrix\. \(Read Only\)|yes|no|Matrix 4x 4 \| Get Lossy Scale
|`m00`|float||yes|yes|Matrix 4x 4 \| Get M 00<br>Matrix 4x 4 \| Set M 00
|`m01`|float||yes|yes|Matrix 4x 4 \| Get M 01<br>Matrix 4x 4 \| Set M 01
|`m02`|float||yes|yes|Matrix 4x 4 \| Get M 02<br>Matrix 4x 4 \| Set M 02
|`m03`|float||yes|yes|Matrix 4x 4 \| Get M 03<br>Matrix 4x 4 \| Set M 03
|`m10`|float||yes|yes|Matrix 4x 4 \| Get M 10<br>Matrix 4x 4 \| Set M 10
|`m11`|float||yes|yes|Matrix 4x 4 \| Get M 11<br>Matrix 4x 4 \| Set M 11
|`m12`|float||yes|yes|Matrix 4x 4 \| Get M 12<br>Matrix 4x 4 \| Set M 12
|`m13`|float||yes|yes|Matrix 4x 4 \| Get M 13<br>Matrix 4x 4 \| Set M 13
|`m20`|float||yes|yes|Matrix 4x 4 \| Get M 20<br>Matrix 4x 4 \| Set M 20
|`m21`|float||yes|yes|Matrix 4x 4 \| Get M 21<br>Matrix 4x 4 \| Set M 21
|`m22`|float||yes|yes|Matrix 4x 4 \| Get M 22<br>Matrix 4x 4 \| Set M 22
|`m23`|float||yes|yes|Matrix 4x 4 \| Get M 23<br>Matrix 4x 4 \| Set M 23
|`m30`|float||yes|yes|Matrix 4x 4 \| Get M 30<br>Matrix 4x 4 \| Set M 30
|`m31`|float||yes|yes|Matrix 4x 4 \| Get M 31<br>Matrix 4x 4 \| Set M 31
|`m32`|float||yes|yes|Matrix 4x 4 \| Get M 32<br>Matrix 4x 4 \| Set M 32
|`m33`|float||yes|yes|Matrix 4x 4 \| Get M 33<br>Matrix 4x 4 \| Set M 33
|`rotation`|UnityEngine\.Quaternion|Attempts to get a rotation quaternion from this matrix\.|yes|no|Matrix 4x 4 \| Get Rotation
|`transpose`|UnityEngine\.Matrix4x4|Returns the transpose of this matrix \(Read Only\)\.|yes|no|Matrix 4x 4 \| Get Transpose
|`zero`|UnityEngine\.Matrix4x4|Returns a matrix with all elements set to zero \(Read Only\)\.|yes|no|Matrix 4x 4 \| Get Zero

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`Matrix4x4`|`column0` UnityEngine\.Vector4<br>`column1` UnityEngine\.Vector4<br>`column2` UnityEngine\.Vector4<br>`column3` UnityEngine\.Vector4|UnityEngine\.Matrix4x4||Matrix 4x 4 \| Create Matrix 4x 4
|`Determinant`|`m` UnityEngine\.Matrix4x4|float||Matrix 4x 4 \| Determinant
|`Frustum`|`left` float<br>`right` float<br>`bottom` float<br>`top` float<br>`zNear` float<br>`zFar` float|UnityEngine\.Matrix4x4|This function returns a projection matrix with viewing frustum that has a near plane defined by the coordinates that were passed in\.|Matrix 4x 4 \| Frustum
|`GetColumn`|`index` int|UnityEngine\.Vector4|Get a column of the matrix\.|Matrix 4x 4 \| Get Column
|`GetPosition`||UnityEngine\.Vector3|Get position vector from the matrix\.|Matrix 4x 4 \| Get Position
|`GetRow`|`index` int|UnityEngine\.Vector4|Returns a row of the matrix\.|Matrix 4x 4 \| Get Row
|`Inverse`|`m` UnityEngine\.Matrix4x4|UnityEngine\.Matrix4x4||Matrix 4x 4 \| Inverse
|`LookAt`|`from` UnityEngine\.Vector3<br>`to` UnityEngine\.Vector3<br>`up` UnityEngine\.Vector3|UnityEngine\.Matrix4x4|Create a "look at" matrix\.|Matrix 4x 4 \| Look At
|`MultiplyPoint`|`point` UnityEngine\.Vector3|UnityEngine\.Vector3|Transforms a position by this matrix \(generic\)\.|Matrix 4x 4 \| Multiply Point
|`MultiplyPoint3x4`|`point` UnityEngine\.Vector3|UnityEngine\.Vector3|Transforms a position by this matrix \(fast\)\.|Matrix 4x 4 \| Multiply Point 3x 4
|`MultiplyVector`|`vector` UnityEngine\.Vector3|UnityEngine\.Vector3|Transforms a direction by this matrix\.|Matrix 4x 4 \| Multiply Vector
|`Ortho`|`left` float<br>`right` float<br>`bottom` float<br>`top` float<br>`zNear` float<br>`zFar` float|UnityEngine\.Matrix4x4|Create an orthogonal projection matrix\.|Matrix 4x 4 \| Ortho
|`Perspective`|`fov` float<br>`aspect` float<br>`zNear` float<br>`zFar` float|UnityEngine\.Matrix4x4|Create a perspective projection matrix\.|Matrix 4x 4 \| Perspective
|`Rotate`|`q` UnityEngine\.Quaternion|UnityEngine\.Matrix4x4|Creates a rotation matrix\.|Matrix 4x 4 \| Rotate
|`Scale`|`vector` UnityEngine\.Vector3|UnityEngine\.Matrix4x4|Creates a scaling matrix\.|Matrix 4x 4 \| Scale
|`SetColumn`|`index` int<br>`column` UnityEngine\.Vector4|void|Sets a column of the matrix\.|Matrix 4x 4 \| Set Column
|`SetRow`|`index` int<br>`row` UnityEngine\.Vector4|void|Sets a row of the matrix\.|Matrix 4x 4 \| Set Row
|`SetTRS`|`pos` UnityEngine\.Vector3<br>`q` UnityEngine\.Quaternion<br>`s` UnityEngine\.Vector3|void|Sets this matrix to a translation, rotation and scaling matrix\.|Matrix 4x 4 \| Set TRS
|`Translate`|`vector` UnityEngine\.Vector3|UnityEngine\.Matrix4x4|Creates a translation matrix\.|Matrix 4x 4 \| Translate
|`Transpose`|`m` UnityEngine\.Matrix4x4|UnityEngine\.Matrix4x4||Matrix 4x 4 \| Transpose
|`TRS`|`pos` UnityEngine\.Vector3<br>`q` UnityEngine\.Quaternion<br>`s` UnityEngine\.Vector3|UnityEngine\.Matrix4x4|Creates a translation, rotation and scaling matrix\.|Matrix 4x 4 \| TRS
|`ValidTRS`||bool|Checks if this matrix is a valid transform matrix\.|Matrix 4x 4 \| Valid TRS

### [UnityEngine\.Quaternion](https://docs.unity3d.com/ScriptReference/Quaternion.html)

Quaternions are used to represent rotations\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`eulerAngles`|UnityEngine\.Vector3|Returns or sets the euler angle representation of the rotation\.|yes|yes|Quaternion \| Get Euler Angles<br>Quaternion \| Set Euler Angles
|`identity`|UnityEngine\.Quaternion|The identity rotation \(Read Only\)\.|yes|no|Quaternion \| Get Identity
|`normalized`|UnityEngine\.Quaternion|Returns this quaternion with a magnitude of 1 \(Read Only\)\.|yes|no|Quaternion \| Get Normalized
|`w`|float|W component of the Quaternion\. Do not directly modify quaternions\.|yes|yes|Quaternion \| Get W<br>Quaternion \| Set W
|`x`|float|X component of the Quaternion\. Don't modify this directly unless you know quaternions inside out\.|yes|yes|Quaternion \| Get X<br>Quaternion \| Set X
|`y`|float|Y component of the Quaternion\. Don't modify this directly unless you know quaternions inside out\.|yes|yes|Quaternion \| Get Y<br>Quaternion \| Set Y
|`z`|float|Z component of the Quaternion\. Don't modify this directly unless you know quaternions inside out\.|yes|yes|Quaternion \| Get Z<br>Quaternion \| Set Z

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`Quaternion`|`x` float<br>`y` float<br>`z` float<br>`w` float|UnityEngine\.Quaternion|Constructs new Quaternion with given x,y,z,w components\.|Quaternion \| Create Quaternion
|`Angle`|`a` UnityEngine\.Quaternion<br>`b` UnityEngine\.Quaternion|float|Returns the angle in degrees between two rotations a and b\.|Quaternion \| Angle
|`AngleAxis`|`angle` float<br>`axis` UnityEngine\.Vector3|UnityEngine\.Quaternion|Creates a rotation which rotates angle degrees around axis\.|Quaternion \| Angle Axis
|`Dot`|`a` UnityEngine\.Quaternion<br>`b` UnityEngine\.Quaternion|float|The dot product between two rotations\.|Quaternion \| Dot
|`Euler`|`x` float<br>`y` float<br>`z` float|UnityEngine\.Quaternion|Returns a rotation that rotates z degrees around the z axis, x degrees around the x axis, and y degrees around the y axis; applied in that order\.|Quaternion \| Euler
|`Euler`|`euler` UnityEngine\.Vector3|UnityEngine\.Quaternion|Returns a rotation that rotates z degrees around the z axis, x degrees around the x axis, and y degrees around the y axis\.|Quaternion \| Euler
|`FromToRotation`|`fromDirection` UnityEngine\.Vector3<br>`toDirection` UnityEngine\.Vector3|UnityEngine\.Quaternion|Creates a rotation which rotates from fromDirection to toDirection\.|Quaternion \| From To Rotation
|`Inverse`|`rotation` UnityEngine\.Quaternion|UnityEngine\.Quaternion|Returns the Inverse of rotation\.|Quaternion \| Inverse
|`Lerp`|`a` UnityEngine\.Quaternion<br>`b` UnityEngine\.Quaternion<br>`t` float|UnityEngine\.Quaternion|Interpolates between a and b by t and normalizes the result afterwards\. The parameter t is clamped to the range \[0, 1\]\.|Quaternion \| Lerp
|`LerpUnclamped`|`a` UnityEngine\.Quaternion<br>`b` UnityEngine\.Quaternion<br>`t` float|UnityEngine\.Quaternion|Interpolates between a and b by t and normalizes the result afterwards\. The parameter t is not clamped\.|Quaternion \| Lerp Unclamped
|`LookRotation`|`forward` UnityEngine\.Vector3|UnityEngine\.Quaternion|Creates a rotation with the specified forward and upwards directions\.|Quaternion \| Look Rotation
|`LookRotation`|`forward` UnityEngine\.Vector3<br>`upwards` UnityEngine\.Vector3|UnityEngine\.Quaternion|Creates a rotation with the specified forward and upwards directions\.|Quaternion \| Look Rotation
|`Normalize`|`q` UnityEngine\.Quaternion|UnityEngine\.Quaternion|Converts this quaternion to one with the same orientation but with a magnitude of 1\.|Quaternion \| Normalize
|`RotateTowards`|`from` UnityEngine\.Quaternion<br>`to` UnityEngine\.Quaternion<br>`maxDegreesDelta` float|UnityEngine\.Quaternion|Rotates a rotation from towards to\.|Quaternion \| Rotate Towards
|`Set`|`newX` float<br>`newY` float<br>`newZ` float<br>`newW` float|void|Set x, y, z and w components of an existing Quaternion\.|Quaternion \| Set
|`SetFromToRotation`|`fromDirection` UnityEngine\.Vector3<br>`toDirection` UnityEngine\.Vector3|void|Creates a rotation which rotates from fromDirection to toDirection\.|Quaternion \| Set From To Rotation
|`SetLookRotation`|`view` UnityEngine\.Vector3|void|Creates a rotation with the specified forward and upwards directions\.|Quaternion \| Set Look Rotation
|`SetLookRotation`|`view` UnityEngine\.Vector3<br>`up` UnityEngine\.Vector3|void|Creates a rotation with the specified forward and upwards directions\.|Quaternion \| Set Look Rotation
|`Slerp`|`a` UnityEngine\.Quaternion<br>`b` UnityEngine\.Quaternion<br>`t` float|UnityEngine\.Quaternion|Spherically interpolates between quaternions a and b by ratio t\. The parameter t is clamped to the range \[0, 1\]\.|Quaternion \| Slerp
|`SlerpUnclamped`|`a` UnityEngine\.Quaternion<br>`b` UnityEngine\.Quaternion<br>`t` float|UnityEngine\.Quaternion|Spherically interpolates between a and b by t\. The parameter t is not clamped\.|Quaternion \| Slerp Unclamped

### [UnityEngine\.Ray](https://docs.unity3d.com/ScriptReference/Ray.html)

Representation of rays\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`direction`|UnityEngine\.Vector3|The direction of the ray\.|yes|yes|Ray \| Get Direction<br>Ray \| Set Direction
|`origin`|UnityEngine\.Vector3|The origin point of the ray\.|yes|yes|Ray \| Get Origin<br>Ray \| Set Origin

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`Ray`|`origin` UnityEngine\.Vector3<br>`direction` UnityEngine\.Vector3|UnityEngine\.Ray|Creates a ray starting at origin along direction\.|Ray \| Create Ray
|`GetPoint`|`distance` float|UnityEngine\.Vector3|Returns a point at distance units along the ray\.|Ray \| Get Point

### [UnityEngine\.Rect](https://docs.unity3d.com/ScriptReference/Rect.html)

A 2D Rectangle defined by X and Y position, width and height\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`center`|UnityEngine\.Vector2|The position of the center of the rectangle\.|yes|yes|Rect \| Get Center<br>Rect \| Set Center
|`height`|float|The height of the rectangle, measured from the Y position\.|yes|yes|Rect \| Get Height<br>Rect \| Set Height
|`max`|UnityEngine\.Vector2|The position of the maximum corner of the rectangle\.|yes|yes|Rect \| Get Max<br>Rect \| Set Max
|`min`|UnityEngine\.Vector2|The position of the minimum corner of the rectangle\.|yes|yes|Rect \| Get Min<br>Rect \| Set Min
|`position`|UnityEngine\.Vector2|The X and Y position of the rectangle\.|yes|yes|Rect \| Get Position<br>Rect \| Set Position
|`size`|UnityEngine\.Vector2|The width and height of the rectangle\.|yes|yes|Rect \| Get Size<br>Rect \| Set Size
|`width`|float|The width of the rectangle, measured from the X position\.|yes|yes|Rect \| Get Width<br>Rect \| Set Width
|`x`|float|The X coordinate of the rectangle\.|yes|yes|Rect \| Get X<br>Rect \| Set X
|`xMax`|float|The maximum X coordinate of the rectangle\.|yes|yes|Rect \| Get X Max<br>Rect \| Set X Max
|`xMin`|float|The minimum X coordinate of the rectangle\.|yes|yes|Rect \| Get X Min<br>Rect \| Set X Min
|`y`|float|The Y coordinate of the rectangle\.|yes|yes|Rect \| Get Y<br>Rect \| Set Y
|`yMax`|float|The maximum Y coordinate of the rectangle\.|yes|yes|Rect \| Get Y Max<br>Rect \| Set Y Max
|`yMin`|float|The minimum Y coordinate of the rectangle\.|yes|yes|Rect \| Get Y Min<br>Rect \| Set Y Min
|`zero`|UnityEngine\.Rect|Shorthand for writing new Rect\(0,0,0,0\)\.|yes|no|Rect \| Get Zero

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`Rect`|`x` float<br>`y` float<br>`width` float<br>`height` float|UnityEngine\.Rect|Creates a new rectangle\.|Rect \| Create Rect
|`Rect`|`position` UnityEngine\.Vector2<br>`size` UnityEngine\.Vector2|UnityEngine\.Rect|Creates a rectangle given a size and position\.|Rect \| Create Rect
|`Contains`|`point` UnityEngine\.Vector2|bool|Returns true if the x and y components of point is a point inside this rectangle\. If allowInverse is present and true, the width and height of the Rect are allowed to take negative values \(ie, the min value is greater than the max\), and the test will still work\.|Rect \| Contains
|`Contains`|`point` UnityEngine\.Vector3|bool|Returns true if the x and y components of point is a point inside this rectangle\. If allowInverse is present and true, the width and height of the Rect are allowed to take negative values \(ie, the min value is greater than the max\), and the test will still work\.|Rect \| Contains
|`Contains`|`point` UnityEngine\.Vector3<br>`allowInverse` bool|bool|Returns true if the x and y components of point is a point inside this rectangle\. If allowInverse is present and true, the width and height of the Rect are allowed to take negative values \(ie, the min value is greater than the max\), and the test will still work\.|Rect \| Contains
|`Equals`|`other` UnityEngine\.Rect|bool||Rect \| Equals
|`MinMaxRect`|`xmin` float<br>`ymin` float<br>`xmax` float<br>`ymax` float|UnityEngine\.Rect|Creates a rectangle from min/max coordinate values\.|Rect \| Min Max Rect
|`NormalizedToPoint`|`rectangle` UnityEngine\.Rect<br>`normalizedRectCoordinates` UnityEngine\.Vector2|UnityEngine\.Vector2|Returns a point inside a rectangle, given normalized coordinates\.|Rect \| Normalized To Point
|`Overlaps`|`other` UnityEngine\.Rect|bool|Returns true if the other rectangle overlaps this one\. If allowInverse is present and true, the widths and heights of the Rects are allowed to take negative values \(ie, the min value is greater than the max\), and the test will still work\.|Rect \| Overlaps
|`Overlaps`|`other` UnityEngine\.Rect<br>`allowInverse` bool|bool|Returns true if the other rectangle overlaps this one\. If allowInverse is present and true, the widths and heights of the Rects are allowed to take negative values \(ie, the min value is greater than the max\), and the test will still work\.|Rect \| Overlaps
|`PointToNormalized`|`rectangle` UnityEngine\.Rect<br>`point` UnityEngine\.Vector2|UnityEngine\.Vector2|Returns the normalized coordinates cooresponding the the point\.|Rect \| Point To Normalized
|`Set`|`x` float<br>`y` float<br>`width` float<br>`height` float|void|Set components of an existing Rect\.|Rect \| Set

### [UnityEngine\.Vector2](https://docs.unity3d.com/ScriptReference/Vector2.html)

Representation of 2D vectors and points\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`down`|UnityEngine\.Vector2|Shorthand for writing Vector2\(0, \-1\)\.|yes|no|Vector 2 \| Get Down
|`left`|UnityEngine\.Vector2|Shorthand for writing Vector2\(\-1, 0\)\.|yes|no|Vector 2 \| Get Left
|`magnitude`|float|Returns the length of this vector \(Read Only\)\.|yes|no|Vector 2 \| Get Magnitude
|`negativeInfinity`|UnityEngine\.Vector2|Shorthand for writing Vector2\(float\.NegativeInfinity, float\.NegativeInfinity\)\.|yes|no|Vector 2 \| Get Negative Infinity
|`normalized`|UnityEngine\.Vector2|Returns this vector with a magnitude of 1 \(Read Only\)\.|yes|no|Vector 2 \| Get Normalized
|`one`|UnityEngine\.Vector2|Shorthand for writing Vector2\(1, 1\)\.|yes|no|Vector 2 \| Get One
|`positiveInfinity`|UnityEngine\.Vector2|Shorthand for writing Vector2\(float\.PositiveInfinity, float\.PositiveInfinity\)\.|yes|no|Vector 2 \| Get Positive Infinity
|`right`|UnityEngine\.Vector2|Shorthand for writing Vector2\(1, 0\)\.|yes|no|Vector 2 \| Get Right
|`sqrMagnitude`|float|Returns the squared length of this vector \(Read Only\)\.|yes|no|Vector 2 \| Get Sqr Magnitude
|`up`|UnityEngine\.Vector2|Shorthand for writing Vector2\(0, 1\)\.|yes|no|Vector 2 \| Get Up
|`x`|float|X component of the vector\.|yes|yes|Vector 2 \| Get X<br>Vector 2 \| Set X
|`y`|float|Y component of the vector\.|yes|yes|Vector 2 \| Get Y<br>Vector 2 \| Set Y
|`zero`|UnityEngine\.Vector2|Shorthand for writing Vector2\(0, 0\)\.|yes|no|Vector 2 \| Get Zero

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`Vector2`|`x` float<br>`y` float|UnityEngine\.Vector2|Constructs a new vector with given x, y components\.|Vector 2 \| Create Vector 2
|`Angle`|`from` UnityEngine\.Vector2<br>`to` UnityEngine\.Vector2|float|Gets the unsigned angle in degrees between from and to\.|Vector 2 \| Angle
|`ClampMagnitude`|`vector` UnityEngine\.Vector2<br>`maxLength` float|UnityEngine\.Vector2|Returns a copy of vector with its magnitude clamped to maxLength\.|Vector 2 \| Clamp Magnitude
|`Distance`|`a` UnityEngine\.Vector2<br>`b` UnityEngine\.Vector2|float|Returns the distance between a and b\.|Vector 2 \| Distance
|`Dot`|`lhs` UnityEngine\.Vector2<br>`rhs` UnityEngine\.Vector2|float|Dot Product of two vectors\.|Vector 2 \| Dot
|`Equals`|`other` UnityEngine\.Vector2|bool||Vector 2 \| Equals
|`Lerp`|`a` UnityEngine\.Vector2<br>`b` UnityEngine\.Vector2<br>`t` float|UnityEngine\.Vector2|Linearly interpolates between vectors a and b by t\.|Vector 2 \| Lerp
|`LerpUnclamped`|`a` UnityEngine\.Vector2<br>`b` UnityEngine\.Vector2<br>`t` float|UnityEngine\.Vector2|Linearly interpolates between vectors a and b by t\.|Vector 2 \| Lerp Unclamped
|`Max`|`lhs` UnityEngine\.Vector2<br>`rhs` UnityEngine\.Vector2|UnityEngine\.Vector2|Returns a vector that is made from the largest components of two vectors\.|Vector 2 \| Max
|`Min`|`lhs` UnityEngine\.Vector2<br>`rhs` UnityEngine\.Vector2|UnityEngine\.Vector2|Returns a vector that is made from the smallest components of two vectors\.|Vector 2 \| Min
|`MoveTowards`|`current` UnityEngine\.Vector2<br>`target` UnityEngine\.Vector2<br>`maxDistanceDelta` float|UnityEngine\.Vector2|Moves a point current towards target\.|Vector 2 \| Move Towards
|`Normalize`||void|Makes this vector have a magnitude of 1\.|Vector 2 \| Normalize
|`Perpendicular`|`inDirection` UnityEngine\.Vector2|UnityEngine\.Vector2|Returns the 2D vector perpendicular to this 2D vector\. The result is always rotated 90\-degrees in a counter\-clockwise direction for a 2D coordinate system where the positive Y axis goes up\.|Vector 2 \| Perpendicular
|`Reflect`|`inDirection` UnityEngine\.Vector2<br>`inNormal` UnityEngine\.Vector2|UnityEngine\.Vector2|Reflects a vector off the vector defined by a normal\.|Vector 2 \| Reflect
|`Scale`|`scale` UnityEngine\.Vector2|void|Multiplies every component of this vector by the same component of scale\.|Vector 2 \| Scale
|`Scale`|`a` UnityEngine\.Vector2<br>`b` UnityEngine\.Vector2|UnityEngine\.Vector2|Multiplies two vectors component\-wise\.|Vector 2 \| Scale
|`Set`|`newX` float<br>`newY` float|void|Set x and y components of an existing Vector2\.|Vector 2 \| Set
|`SignedAngle`|`from` UnityEngine\.Vector2<br>`to` UnityEngine\.Vector2|float|Gets the signed angle in degrees between from and to\.|Vector 2 \| Signed Angle
|`SqrMagnitude`||float||Vector 2 \| Sqr Magnitude
|`SqrMagnitude`|`a` UnityEngine\.Vector2|float||Vector 2 \| Sqr Magnitude

### [UnityEngine\.Vector3](https://docs.unity3d.com/ScriptReference/Vector3.html)

Representation of 3D vectors and points\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`back`|UnityEngine\.Vector3|Shorthand for writing Vector3\(0, 0, \-1\)\.|yes|no|Vector 3 \| Get Back
|`down`|UnityEngine\.Vector3|Shorthand for writing Vector3\(0, \-1, 0\)\.|yes|no|Vector 3 \| Get Down
|`forward`|UnityEngine\.Vector3|Shorthand for writing Vector3\(0, 0, 1\)\.|yes|no|Vector 3 \| Get Forward
|`left`|UnityEngine\.Vector3|Shorthand for writing Vector3\(\-1, 0, 0\)\.|yes|no|Vector 3 \| Get Left
|`magnitude`|float|Returns the length of this vector \(Read Only\)\.|yes|no|Vector 3 \| Get Magnitude
|`negativeInfinity`|UnityEngine\.Vector3|Shorthand for writing Vector3\(float\.NegativeInfinity, float\.NegativeInfinity, float\.NegativeInfinity\)\.|yes|no|Vector 3 \| Get Negative Infinity
|`normalized`|UnityEngine\.Vector3|Returns this vector with a magnitude of 1 \(Read Only\)\.|yes|no|Vector 3 \| Get Normalized
|`one`|UnityEngine\.Vector3|Shorthand for writing Vector3\(1, 1, 1\)\.|yes|no|Vector 3 \| Get One
|`positiveInfinity`|UnityEngine\.Vector3|Shorthand for writing Vector3\(float\.PositiveInfinity, float\.PositiveInfinity, float\.PositiveInfinity\)\.|yes|no|Vector 3 \| Get Positive Infinity
|`right`|UnityEngine\.Vector3|Shorthand for writing Vector3\(1, 0, 0\)\.|yes|no|Vector 3 \| Get Right
|`sqrMagnitude`|float|Returns the squared length of this vector \(Read Only\)\.|yes|no|Vector 3 \| Get Sqr Magnitude
|`up`|UnityEngine\.Vector3|Shorthand for writing Vector3\(0, 1, 0\)\.|yes|no|Vector 3 \| Get Up
|`x`|float|X component of the vector\.|yes|yes|Vector 3 \| Get X<br>Vector 3 \| Set X
|`y`|float|Y component of the vector\.|yes|yes|Vector 3 \| Get Y<br>Vector 3 \| Set Y
|`z`|float|Z component of the vector\.|yes|yes|Vector 3 \| Get Z<br>Vector 3 \| Set Z
|`zero`|UnityEngine\.Vector3|Shorthand for writing Vector3\(0, 0, 0\)\.|yes|no|Vector 3 \| Get Zero

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`Vector3`|`x` float<br>`y` float|UnityEngine\.Vector3|Creates a new vector with given x, y components and sets z to zero\.|Vector 3 \| Create Vector 3
|`Vector3`|`x` float<br>`y` float<br>`z` float|UnityEngine\.Vector3|Creates a new vector with given x, y, z components\.|Vector 3 \| Create Vector 3
|`Angle`|`from` UnityEngine\.Vector3<br>`to` UnityEngine\.Vector3|float|Calculates the angle between vectors from and\.|Vector 3 \| Angle
|`ClampMagnitude`|`vector` UnityEngine\.Vector3<br>`maxLength` float|UnityEngine\.Vector3|Returns a copy of vector with its magnitude clamped to maxLength\.|Vector 3 \| Clamp Magnitude
|`Cross`|`lhs` UnityEngine\.Vector3<br>`rhs` UnityEngine\.Vector3|UnityEngine\.Vector3|Cross Product of two vectors\.|Vector 3 \| Cross
|`Distance`|`a` UnityEngine\.Vector3<br>`b` UnityEngine\.Vector3|float|Returns the distance between a and b\.|Vector 3 \| Distance
|`Dot`|`lhs` UnityEngine\.Vector3<br>`rhs` UnityEngine\.Vector3|float|Dot Product of two vectors\.|Vector 3 \| Dot
|`Equals`|`other` UnityEngine\.Vector3|bool||Vector 3 \| Equals
|`Lerp`|`a` UnityEngine\.Vector3<br>`b` UnityEngine\.Vector3<br>`t` float|UnityEngine\.Vector3|Linearly interpolates between two points\.|Vector 3 \| Lerp
|`LerpUnclamped`|`a` UnityEngine\.Vector3<br>`b` UnityEngine\.Vector3<br>`t` float|UnityEngine\.Vector3|Linearly interpolates between two vectors\.|Vector 3 \| Lerp Unclamped
|`Magnitude`|`vector` UnityEngine\.Vector3|float||Vector 3 \| Magnitude
|`Max`|`lhs` UnityEngine\.Vector3<br>`rhs` UnityEngine\.Vector3|UnityEngine\.Vector3|Returns a vector that is made from the largest components of two vectors\.|Vector 3 \| Max
|`Min`|`lhs` UnityEngine\.Vector3<br>`rhs` UnityEngine\.Vector3|UnityEngine\.Vector3|Returns a vector that is made from the smallest components of two vectors\.|Vector 3 \| Min
|`MoveTowards`|`current` UnityEngine\.Vector3<br>`target` UnityEngine\.Vector3<br>`maxDistanceDelta` float|UnityEngine\.Vector3|Calculate a position between the points specified by current and target, moving no farther than the distance specified by maxDistanceDelta\.|Vector 3 \| Move Towards
|`Normalize`|`value` UnityEngine\.Vector3|UnityEngine\.Vector3|Makes this vector have a magnitude of 1\.|Vector 3 \| Normalize
|`Project`|`vector` UnityEngine\.Vector3<br>`onNormal` UnityEngine\.Vector3|UnityEngine\.Vector3|Projects a vector onto another vector\.|Vector 3 \| Project
|`ProjectOnPlane`|`vector` UnityEngine\.Vector3<br>`planeNormal` UnityEngine\.Vector3|UnityEngine\.Vector3|Projects a vector onto a plane defined by a normal orthogonal to the plane\.|Vector 3 \| Project On Plane
|`Reflect`|`inDirection` UnityEngine\.Vector3<br>`inNormal` UnityEngine\.Vector3|UnityEngine\.Vector3|Reflects a vector off the plane defined by a normal\.|Vector 3 \| Reflect
|`RotateTowards`|`current` UnityEngine\.Vector3<br>`target` UnityEngine\.Vector3<br>`maxRadiansDelta` float<br>`maxMagnitudeDelta` float|UnityEngine\.Vector3|Rotates a vector current towards target\.|Vector 3 \| Rotate Towards
|`Scale`|`scale` UnityEngine\.Vector3|void|Multiplies every component of this vector by the same component of scale\.|Vector 3 \| Scale
|`Scale`|`a` UnityEngine\.Vector3<br>`b` UnityEngine\.Vector3|UnityEngine\.Vector3|Multiplies two vectors component\-wise\.|Vector 3 \| Scale
|`Set`|`newX` float<br>`newY` float<br>`newZ` float|void|Set x, y and z components of an existing Vector3\.|Vector 3 \| Set
|`SignedAngle`|`from` UnityEngine\.Vector3<br>`to` UnityEngine\.Vector3<br>`axis` UnityEngine\.Vector3|float|Calculates the signed angle between vectors from and to in relation to axis\.|Vector 3 \| Signed Angle
|`Slerp`|`a` UnityEngine\.Vector3<br>`b` UnityEngine\.Vector3<br>`t` float|UnityEngine\.Vector3|Spherically interpolates between two vectors\.|Vector 3 \| Slerp
|`SlerpUnclamped`|`a` UnityEngine\.Vector3<br>`b` UnityEngine\.Vector3<br>`t` float|UnityEngine\.Vector3|Spherically interpolates between two vectors\.|Vector 3 \| Slerp Unclamped
|`SqrMagnitude`|`vector` UnityEngine\.Vector3|float||Vector 3 \| Sqr Magnitude

### [UnityEngine\.Vector4](https://docs.unity3d.com/ScriptReference/Vector4.html)

Representation of four\-dimensional vectors\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`magnitude`|float|Returns the length of this vector \(Read Only\)\.|yes|no|Vector 4 \| Get Magnitude
|`negativeInfinity`|UnityEngine\.Vector4|Shorthand for writing Vector4\(float\.NegativeInfinity, float\.NegativeInfinity, float\.NegativeInfinity, float\.NegativeInfinity\)\.|yes|no|Vector 4 \| Get Negative Infinity
|`normalized`|UnityEngine\.Vector4|Returns this vector with a magnitude of 1 \(Read Only\)\.|yes|no|Vector 4 \| Get Normalized
|`one`|UnityEngine\.Vector4|Shorthand for writing Vector4\(1,1,1,1\)\.|yes|no|Vector 4 \| Get One
|`positiveInfinity`|UnityEngine\.Vector4|Shorthand for writing Vector4\(float\.PositiveInfinity, float\.PositiveInfinity, float\.PositiveInfinity, float\.PositiveInfinity\)\.|yes|no|Vector 4 \| Get Positive Infinity
|`sqrMagnitude`|float|Returns the squared length of this vector \(Read Only\)\.|yes|no|Vector 4 \| Get Sqr Magnitude
|`w`|float|W component of the vector\.|yes|yes|Vector 4 \| Get W<br>Vector 4 \| Set W
|`x`|float|X component of the vector\.|yes|yes|Vector 4 \| Get X<br>Vector 4 \| Set X
|`y`|float|Y component of the vector\.|yes|yes|Vector 4 \| Get Y<br>Vector 4 \| Set Y
|`z`|float|Z component of the vector\.|yes|yes|Vector 4 \| Get Z<br>Vector 4 \| Set Z
|`zero`|UnityEngine\.Vector4|Shorthand for writing Vector4\(0,0,0,0\)\.|yes|no|Vector 4 \| Get Zero

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`Vector4`|`x` float<br>`y` float|UnityEngine\.Vector4|Creates a new vector with given x, y components and sets z and w to zero\.|Vector 4 \| Create Vector 4
|`Vector4`|`x` float<br>`y` float<br>`z` float|UnityEngine\.Vector4|Creates a new vector with given x, y, z components and sets w to zero\.|Vector 4 \| Create Vector 4
|`Vector4`|`x` float<br>`y` float<br>`z` float<br>`w` float|UnityEngine\.Vector4|Creates a new vector with given x, y, z, w components\.|Vector 4 \| Create Vector 4
|`Distance`|`a` UnityEngine\.Vector4<br>`b` UnityEngine\.Vector4|float|Returns the distance between a and b\.|Vector 4 \| Distance
|`Dot`|`a` UnityEngine\.Vector4<br>`b` UnityEngine\.Vector4|float|Dot Product of two vectors\.|Vector 4 \| Dot
|`Equals`|`other` UnityEngine\.Vector4|bool||Vector 4 \| Equals
|`Lerp`|`a` UnityEngine\.Vector4<br>`b` UnityEngine\.Vector4<br>`t` float|UnityEngine\.Vector4|Linearly interpolates between two vectors\.|Vector 4 \| Lerp
|`LerpUnclamped`|`a` UnityEngine\.Vector4<br>`b` UnityEngine\.Vector4<br>`t` float|UnityEngine\.Vector4|Linearly interpolates between two vectors\.|Vector 4 \| Lerp Unclamped
|`Magnitude`|`a` UnityEngine\.Vector4|float||Vector 4 \| Magnitude
|`Max`|`lhs` UnityEngine\.Vector4<br>`rhs` UnityEngine\.Vector4|UnityEngine\.Vector4|Returns a vector that is made from the largest components of two vectors\.|Vector 4 \| Max
|`Min`|`lhs` UnityEngine\.Vector4<br>`rhs` UnityEngine\.Vector4|UnityEngine\.Vector4|Returns a vector that is made from the smallest components of two vectors\.|Vector 4 \| Min
|`MoveTowards`|`current` UnityEngine\.Vector4<br>`target` UnityEngine\.Vector4<br>`maxDistanceDelta` float|UnityEngine\.Vector4|Moves a point current towards target\.|Vector 4 \| Move Towards
|`Normalize`|`a` UnityEngine\.Vector4|UnityEngine\.Vector4||Vector 4 \| Normalize
|`Project`|`a` UnityEngine\.Vector4<br>`b` UnityEngine\.Vector4|UnityEngine\.Vector4|Projects a vector onto another vector\.|Vector 4 \| Project
|`Scale`|`scale` UnityEngine\.Vector4|void|Multiplies every component of this vector by the same component of scale\.|Vector 4 \| Scale
|`Scale`|`a` UnityEngine\.Vector4<br>`b` UnityEngine\.Vector4|UnityEngine\.Vector4|Multiplies two vectors component\-wise\.|Vector 4 \| Scale
|`Set`|`newX` float<br>`newY` float<br>`newZ` float<br>`newW` float|void|Set x, y, z and w components of an existing Vector4\.|Vector 4 \| Set
|`SqrMagnitude`||float||Vector 4 \| Sqr Magnitude
|`SqrMagnitude`|`a` UnityEngine\.Vector4|float||Vector 4 \| Sqr Magnitude
|`ToString`|`format` string|string|Returns a formatted string for this vector\.|Vector 4 \| To String

## Other

### [UnityEngine\.AnimationCurve](https://docs.unity3d.com/ScriptReference/AnimationCurve.html)

Store a collection of Keyframes that can be evaluated over time\.

### [UnityEngine\.Debug](https://docs.unity3d.com/ScriptReference/Debug.html)

Class containing methods to ease debugging while developing a game\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`isDebugBuild`|bool|In the Build Settings dialog there is a check box called "Development Build"\.|yes|no|Debug \| Is Debug Build

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`DrawLine`|`start` UnityEngine\.Vector3<br>`end` UnityEngine\.Vector3|void|Draws a line between specified start and end points\.|Debug \| Draw Line
|`DrawLine`|`start` UnityEngine\.Vector3<br>`end` UnityEngine\.Vector3<br>`color` UnityEngine\.Color|void|Draws a line between specified start and end points\.|Debug \| Draw Line
|`DrawLine`|`start` UnityEngine\.Vector3<br>`end` UnityEngine\.Vector3<br>`color` UnityEngine\.Color<br>`duration` float|void|Draws a line between specified start and end points\.|Debug \| Draw Line
|`DrawLine`|`start` UnityEngine\.Vector3<br>`end` UnityEngine\.Vector3<br>`color` UnityEngine\.Color<br>`duration` float<br>`depthTest` bool|void|Draws a line between specified start and end points\.|Debug \| Draw Line
|`DrawRay`|`start` UnityEngine\.Vector3<br>`dir` UnityEngine\.Vector3|void|Draws a line from start to start \+ dir in world coordinates\.|Debug \| Draw Ray
|`DrawRay`|`start` UnityEngine\.Vector3<br>`dir` UnityEngine\.Vector3<br>`color` UnityEngine\.Color|void|Draws a line from start to start \+ dir in world coordinates\.|Debug \| Draw Ray
|`DrawRay`|`start` UnityEngine\.Vector3<br>`dir` UnityEngine\.Vector3<br>`color` UnityEngine\.Color<br>`duration` float|void|Draws a line from start to start \+ dir in world coordinates\.|Debug \| Draw Ray
|`DrawRay`|`start` UnityEngine\.Vector3<br>`dir` UnityEngine\.Vector3<br>`color` UnityEngine\.Color<br>`duration` float<br>`depthTest` bool|void|Draws a line from start to start \+ dir in world coordinates\.|Debug \| Draw Ray
|`Log`|`message` object|void|Logs a message to the Unity Console\.|Debug \| Log
|`Log`|`message` object<br>`context` UnityEngine\.Object|void|Logs a message to the Unity Console\.|Debug \| Log
|`LogError`|`message` object|void|A variant of Debug\.Log that logs an error message to the console\.|Debug \| Log Error
|`LogError`|`message` object<br>`context` UnityEngine\.Object|void|A variant of Debug\.Log that logs an error message to the console\.|Debug \| Log Error
|`LogWarning`|`message` object|void|A variant of Debug\.Log that logs a warning message to the console\.|Debug \| Log Warning
|`LogWarning`|`message` object<br>`context` UnityEngine\.Object|void|A variant of Debug\.Log that logs a warning message to the console\.|Debug \| Log Warning

### [UnityEngine\.DynamicGI](https://docs.unity3d.com/ScriptReference/DynamicGI.html)

Allows to control the dynamic Global Illumination\.

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`UpdateEnvironment`||void|Schedules an update of the environment cubemap\.|Dynamic GI \| Update Environment

### [UnityEngine\.Material](https://docs.unity3d.com/ScriptReference/Material.html)

The material class\.

Supports additional properties and methods from UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`color`|UnityEngine\.Color|The main color of the Material\.|yes|yes|Material \| Get Color<br>Material \| Set Color
|`mainTextureOffset`|UnityEngine\.Vector2|The offset of the main texture\.|yes|yes|Material \| Get Main Texture Offset<br>Material \| Set Main Texture Offset
|`mainTextureScale`|UnityEngine\.Vector2|The scale of the main texture\.|yes|yes|Material \| Get Main Texture Scale<br>Material \| Set Main Texture Scale
|`shader`|UnityEngine\.Shader|The shader used by the material\.|yes|yes|Material \| Get Shader<br>Material \| Set Shader

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`DisableKeyword`|`keyword` string|void|Disables a local shader keyword for this material\.|Material \| Disable Keyword
|`EnableKeyword`|`keyword` string|void|Enables a local shader keyword for this material\.|Material \| Enable Keyword
|`GetColor`|`name` string|UnityEngine\.Color|Get a named color value\.|Material \| Get Color
|`GetFloat`|`name` string|float|Get a named float value\.|Material \| Get Float
|`GetInteger`|`name` string|int|Get a named integer value\.|Material \| Get Integer
|`GetMatrix`|`name` string|UnityEngine\.Matrix4x4|Get a named matrix value from the shader\.|Material \| Get Matrix
|`GetTexture`|`name` string|UnityEngine\.Texture|Get a named texture\.|Material \| Get Texture
|`GetTextureOffset`|`name` string|UnityEngine\.Vector2|Gets the placement offset of texture propertyName\.|Material \| Get Texture Offset
|`GetTextureScale`|`name` string|UnityEngine\.Vector2|Gets the placement scale of texture propertyName\.|Material \| Get Texture Scale
|`GetVector`|`name` string|UnityEngine\.Vector4|Get a named vector value\.|Material \| Get Vector
|`HasColor`|`name` string|bool|Checks if the ShaderLab file assigned to the Material has a Color property with the given name\.|Material \| Has Color
|`HasFloat`|`name` string|bool|Checks if the ShaderLab file assigned to the Material has a Float property with the given name\. This also works with the Float Array property\.|Material \| Has Float
|`HasInteger`|`name` string|bool|Checks if the ShaderLab file assigned to the Material has an Integer property with the given name\.|Material \| Has Integer
|`HasMatrix`|`name` string|bool|Checks if the ShaderLab file assigned to the Material has a Matrix property with the given name\. This also works with the Matrix Array property\.|Material \| Has Matrix
|`HasProperty`|`name` string|bool|Checks if the ShaderLab file assigned to the Material has a property with the given name\.|Material \| Has Property
|`HasTexture`|`name` string|bool|Checks if the ShaderLab file assigned to the Material has a Texture property with the given name\.|Material \| Has Texture
|`HasVector`|`name` string|bool|Checks if the ShaderLab file assigned to the Material has a Vector property with the given name\. This also works with the Vector Array property\.|Material \| Has Vector
|`IsKeywordEnabled`|`keyword` string|bool|Checks whether a local shader keyword is enabled for this material\.|Material \| Is Keyword Enabled
|`Lerp`|`start` UnityEngine\.Material<br>`end` UnityEngine\.Material<br>`t` float|void|Interpolate properties between two materials\.|Material \| Lerp
|`SetColor`|`name` string<br>`value` UnityEngine\.Color|void|Sets a color value\.|Material \| Set Color
|`SetFloat`|`name` string<br>`value` float|void|Sets a named float value\.|Material \| Set Float
|`SetInteger`|`name` string<br>`value` int|void|Sets a named integer value\.|Material \| Set Integer
|`SetMatrix`|`name` string<br>`value` UnityEngine\.Matrix4x4|void|Sets a named matrix for the shader\.|Material \| Set Matrix
|`SetOverrideTag`|`tag` string<br>`val` string|void|Sets an override tag/value on the material\.|Material \| Set Override Tag
|`SetTexture`|`name` string<br>`value` UnityEngine\.Texture|void|Sets a named texture\.|Material \| Set Texture
|`SetTextureOffset`|`name` string<br>`value` UnityEngine\.Vector2|void|Sets the placement offset of a given texture\. The name parameter is defined in the shader\. This method creates a new Material instance\.|Material \| Set Texture Offset
|`SetTextureScale`|`name` string<br>`value` UnityEngine\.Vector2|void|Sets the placement scale of texture propertyName\.|Material \| Set Texture Scale
|`SetVector`|`name` string<br>`value` UnityEngine\.Vector4|void|Sets a named vector value\.|Material \| Set Vector

### [UnityEngine\.MaterialPropertyBlock](https://docs.unity3d.com/ScriptReference/MaterialPropertyBlock.html)

A block of material values to apply\.

| Method | Parameters | Returns | Script |
|--------|------------|---------|--------|
|`MaterialPropertyBlock`||UnityEngine\.MaterialPropertyBlock|Material Property Block \| Create Material Property Block

### [UnityEngine\.Mesh](https://docs.unity3d.com/ScriptReference/Mesh.html)

A class that allows you to create or modify meshes\.

Supports additional properties and methods from UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`bounds`|UnityEngine\.Bounds|The bounding volume of the Mesh\.|yes|no|Mesh \| Get Bounds
|`isReadable`|bool|Returns true if the Mesh is read/write enabled, or false if it is not\.|yes|no|Mesh \| Is Readable
|`vertexCount`|int|Returns the number of vertices in the Mesh \(Read Only\)\.|yes|no|Mesh \| Get Vertex Count

### [UnityEngine\.Object](https://docs.unity3d.com/ScriptReference/Object.html)

Base class for all objects Unity can reference\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`name`|string|The name of the object\.|yes|no|Unity Object \| Get Name

### [UnityEngine\.Random](https://docs.unity3d.com/ScriptReference/Random.html)

Easily generate random data for games\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`insideUnitCircle`|UnityEngine\.Vector2|Returns a random point inside or on a circle with radius 1\.0 \(Read Only\)\.|yes|no|Random \| Get Inside Unit Circle
|`insideUnitSphere`|UnityEngine\.Vector3|Returns a random point inside or on a sphere with radius 1\.0 \(Read Only\)\.|yes|no|Random \| Get Inside Unit Sphere
|`onUnitSphere`|UnityEngine\.Vector3|Returns a random point on the surface of a sphere with radius 1\.0 \(Read Only\)\.|yes|no|Random \| Get On Unit Sphere
|`rotation`|UnityEngine\.Quaternion|Returns a random rotation \(Read Only\)\.|yes|no|Random \| Get Rotation
|`rotationUniform`|UnityEngine\.Quaternion|Returns a random rotation with uniform distribution \(Read Only\)\.|yes|no|Random \| Get Rotation Uniform
|`value`|float|Returns a random float within \[0\.0\.\.1\.0\] \(range is inclusive\) \(Read Only\)\.|yes|no|Random \| Get Value

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`ColorHSV`||UnityEngine\.Color|Generates a random color from HSV and alpha ranges\.|Random \| Color HSV
|`ColorHSV`|`hueMin` float<br>`hueMax` float|UnityEngine\.Color|Generates a random color from HSV and alpha ranges\.|Random \| Color HSV
|`ColorHSV`|`hueMin` float<br>`hueMax` float<br>`saturationMin` float<br>`saturationMax` float|UnityEngine\.Color|Generates a random color from HSV and alpha ranges\.|Random \| Color HSV
|`ColorHSV`|`hueMin` float<br>`hueMax` float<br>`saturationMin` float<br>`saturationMax` float<br>`valueMin` float<br>`valueMax` float|UnityEngine\.Color|Generates a random color from HSV and alpha ranges\.|Random \| Color HSV
|`ColorHSV`|`hueMin` float<br>`hueMax` float<br>`saturationMin` float<br>`saturationMax` float<br>`valueMin` float<br>`valueMax` float<br>`alphaMin` float<br>`alphaMax` float|UnityEngine\.Color|Generates a random color from HSV and alpha ranges\.|Random \| Color HSV
|`InitState`|`seed` int|void|Initializes the random number generator state with a seed\.|Random \| Init State
|`Range`|`minInclusive` float<br>`maxInclusive` float|float|Returns a random float within \[minInclusive\.\.maxInclusive\] \(range is inclusive\)\.|Random \| Range
|`Range`|`minInclusive` int<br>`maxExclusive` int|int|Return a random int within \[minInclusive\.\.maxExclusive\) \(Read Only\)\.|Random \| Range

### [UnityEngine\.RenderSettings](https://docs.unity3d.com/ScriptReference/Experimental.GlobalIllumination.RenderSettings.html)

The Render Settings contain values for a range of visual elements in your Scene, like fog and ambient light\.

Supports additional properties and methods from UnityEngine\.Object.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`ambientEquatorColor`|UnityEngine\.Color|Ambient lighting coming from the sides\.|yes|yes|Render Settings \| Get Ambient Equator Color<br>Render Settings \| Set Ambient Equator Color
|`ambientGroundColor`|UnityEngine\.Color|Ambient lighting coming from below\.|yes|yes|Render Settings \| Get Ambient Ground Color<br>Render Settings \| Set Ambient Ground Color
|`ambientIntensity`|float|How much the light from the Ambient Source affects the Scene\.|yes|yes|Render Settings \| Get Ambient Intensity<br>Render Settings \| Set Ambient Intensity
|`ambientLight`|UnityEngine\.Color|Flat ambient lighting color\.|yes|yes|Render Settings \| Get Ambient Light<br>Render Settings \| Set Ambient Light
|`ambientSkyColor`|UnityEngine\.Color|Ambient lighting coming from above\.|yes|yes|Render Settings \| Get Ambient Sky Color<br>Render Settings \| Set Ambient Sky Color
|`skybox`|UnityEngine\.Material|The global skybox to use\.|yes|yes|Render Settings \| Get Skybox<br>Render Settings \| Set Skybox

### [UnityEngine\.Shader](https://docs.unity3d.com/ScriptReference/Shader.html)

Shader scripts used for all rendering\.

Supports additional properties and methods from UnityEngine\.Object.

| Method | Parameters | Returns | Description | Script |
|--------|------------|---------|-------------|--------|
|`DisableKeyword`|`keyword` string|void|Disables a global shader keyword\.|Shader \| Disable Keyword
|`EnableKeyword`|`keyword` string|void|Enables a global shader keyword\.|Shader \| Enable Keyword
|`Find`|`name` string|UnityEngine\.Shader|Finds a shader with the given name\. Returns null if the shader is not found\.|Shader \| Find
|`GetGlobalColor`|`name` string|UnityEngine\.Color|Gets a global color property for all shaders previously set using SetGlobalColor\.|Shader \| Get Global Color
|`GetGlobalFloat`|`name` string|float|Gets a global float property for all shaders previously set using SetGlobalFloat\.|Shader \| Get Global Float
|`GetGlobalInteger`|`name` string|int|Gets a global integer property for all shaders previously set using SetGlobalInteger\.|Shader \| Get Global Integer
|`GetGlobalMatrix`|`name` string|UnityEngine\.Matrix4x4|Gets a global matrix property for all shaders previously set using SetGlobalMatrix\.|Shader \| Get Global Matrix
|`GetGlobalTexture`|`name` string|UnityEngine\.Texture|Gets a global texture property for all shaders previously set using SetGlobalTexture\.|Shader \| Get Global Texture
|`GetGlobalVector`|`name` string|UnityEngine\.Vector4|Gets a global vector property for all shaders previously set using SetGlobalVector\.|Shader \| Get Global Vector
|`IsKeywordEnabled`|`keyword` string|bool|Checks whether a global shader keyword is enabled\.|Shader \| Is Keyword Enabled
|`SetGlobalColor`|`name` string<br>`value` UnityEngine\.Color|void|Sets a global color property for all shaders\.|Shader \| Set Global Color
|`SetGlobalFloat`|`name` string<br>`value` float|void|Sets a global float property for all shaders\.|Shader \| Set Global Float
|`SetGlobalInteger`|`name` string<br>`value` int|void|Sets a global integer property for all shaders\.|Shader \| Set Global Integer
|`SetGlobalMatrix`|`name` string<br>`value` UnityEngine\.Matrix4x4|void|Sets a global matrix property for all shaders\.|Shader \| Set Global Matrix
|`SetGlobalTexture`|`name` string<br>`value` UnityEngine\.Texture|void|Sets a global texture property for all shaders\.|Shader \| Set Global Texture
|`SetGlobalVector`|`name` string<br>`value` UnityEngine\.Vector4|void|Sets a global vector property for all shaders\.|Shader \| Set Global Vector

### [UnityEngine\.TextAsset](https://docs.unity3d.com/ScriptReference/TextAsset.html)

Represents a raw text or binary file asset\.

Supports additional properties and methods from UnityEngine\.Object.

### [UnityEngine\.Texture](https://docs.unity3d.com/ScriptReference/Texture.html)

Base class for Texture handling\.

Supports additional properties and methods from UnityEngine\.Object.

### [UnityEngine\.Time](https://docs.unity3d.com/ScriptReference/Time.html)

Provides an interface to get time information from Unity\.

| Property | Type | Description | Read? | Write? | Script |
|----------|------|-------------|:-----:|:------:|--------|
|`deltaTime`|float|The interval in seconds from the last frame to the current one \(Read Only\)\.|yes|no|Time \| Get Delta Time
|`fixedDeltaTime`|float|The interval in seconds at which physics and other fixed frame rate updates \(like MonoBehaviour's MonoBehaviour\.FixedUpdate\) are performed\.|yes|no|Time \| Get Fixed Delta Time
|`fixedTime`|float|The time since the last MonoBehaviour\.FixedUpdate started \(Read Only\)\. This is the time in seconds since the start of the game\.|yes|no|Time \| Get Fixed Time
|`fixedUnscaledDeltaTime`|float|The timeScale\-independent interval in seconds from the last MonoBehaviour\.FixedUpdate phase to the current one \(Read Only\)\.|yes|no|Time \| Get Fixed Unscaled Delta Time
|`fixedUnscaledTime`|float|The timeScale\-independent time at the beginning of the last MonoBehaviour\.FixedUpdate phase \(Read Only\)\. This is the time in seconds since the start of the game\.|yes|no|Time \| Get Fixed Unscaled Time
|`frameCount`|int|The total number of frames since the start of the game \(Read Only\)\.|yes|no|Time \| Get Frame Count
|`inFixedTimeStep`|bool|Returns true if called inside a fixed time step callback \(like MonoBehaviour's MonoBehaviour\.FixedUpdate\), otherwise returns false\.|yes|no|Time \| Get In Fixed Time Step
|`realtimeSinceStartup`|float|The real time in seconds since the game started \(Read Only\)\.|yes|no|Time \| Get Realtime Since Startup
|`renderedFrameCount`|int||yes|no|Time \| Get Rendered Frame Count
|`smoothDeltaTime`|float|A smoothed out Time\.deltaTime \(Read Only\)\.|yes|no|Time \| Get Smooth Delta Time
|`time`|float|The time at the beginning of this frame \(Read Only\)\.|yes|no|Time \| Get Time
|`timeScale`|float|The scale at which time passes\.|yes|no|Time \| Get Time Scale
|`unscaledDeltaTime`|float|The timeScale\-independent interval in seconds from the last frame to the current one \(Read Only\)\.|yes|no|Time \| Get Unscaled Delta Time
|`unscaledTime`|float|The timeScale\-independent time for this frame \(Read Only\)\. This is the time in seconds since the start of the game\.|yes|no|Time \| Get Unscaled Time

## Enums

### UnityEngine\.RectTransform\.Axis

Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value |
|------|------:|
|`Horizontal`|0
|`Vertical`|1

### [UnityEngine\.RectTransform\.Edge](https://docs.unity3d.com/ScriptReference/RectTransform.Edge.html)

Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value |
|------|------:|
|`Left`|0
|`Right`|1
|`Top`|2
|`Bottom`|3

### [UnityEngine\.Space](https://docs.unity3d.com/ScriptReference/Space.html)

The coordinate space in which to operate\.

Values are mutually exclusive\.
\(Underlying type: int)

| Enum | Value | Description |
|------|------:|-------------|
|`World`|0|Applies transformation relative to the world coordinate system\.
|`Self`|1|Applies transformation relative to the local coordinate system\.
