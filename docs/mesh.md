# Mesh

## Functions

| Function Name | Return Type | Description | Tags |
|---------------|-------------|-------------|------|
| PlayAnimation(string animationname) | [AnimationHandle](animation_handle) | Play a named animation on this mesh, once | None |
| PlayAniamtion(string animationname, boolean looping) | [AnimationHandle](animation_handle) | Play a named animation on this mesh, optionally looping | None |
| PlayAnimation(string animationname, boolean looping, table properties) | [AnimationHandle](animation_handle) | Play a named animation on this mesh, optional table can contain named values looping, either playbackTime or playbackSpeed and either 'positionFactor' or 'positionTime' a negative playbackSpeed will play the animation in reverse. For example playbackSpeed = -2 will play the animation twice as fast in reverse | None |
| PlayAnimationLooping(string animationName) | [AnimationHandle](animation_handle) | Play a named animation on this mesh, repeatedly | None |
| PlayAnimationLooping(string animationName, table properties) | [AnimationHandle](animation_handle) | This is the same as the PlayAnimation function taking a table containing playbackTime or playbackSpeed except that looping defaults to true | None |
| PlayAnimationClient(string animationName) | [AnimationHandle](animation_handle) | Use PlayAnimation instead, works on client or server | Deprecated |
| PlayAnimationClient(string animationname, boolean looping) | [AnimationHandle](animation_handle) | Use PlayAnimation instead, works on client or server | Deprecated |
| PlayAnimationLoopingClient(string animationName, boolean looping) | [AnimationHandle](animation_handle) | Use PlayAnimation instead, works on client or server | Deprecated |
| GetAnimationNames() | table`<string>` | Get a table of animation names that you can play on this mesh with PlayAnimation | None |
| GetAnimationLength(string animationName) | number | Get the length of an animation in seconds | None |
| CreateThruster() | [Thruster](thruster) | Add a thruster to an entity | None |
| CreateRelativeThruster() | [Thruster](thruster) | Add a relative thruster to an entity | None |
| DestroyThruster() | None | Destroy a thruster | None |
| AddImpulse([Vector](vector) impulse) | Add Impulse. An integral of force over a time interval. Newton seconds | None |
| AddAngularImpulse([Rotation](rotation) angularImpulse) | Add Angular Impulse. An integral of torque over a time interval. Newton seconds | None |

## Properties

| Property Name | Return Type | Description | Tags |
|---------------|-------------|-------------|------|
| collisionEnabled | boolean | Turn on or off collision (ie calling entry point OnCollision) | None |
| damageEnabled | boolean | Turn on or off damage (ie calling of entry point OnDamaged) | None |
| physicsEnabled | boolean | Turn on or off physics | None |
| gravityEnabled | boolean | Turn on or off gravity | None |
| onCollision | [Event](event) | Called when this entity is collided with by a player Character with the Character passed as an argument, as well as the mesh Entity from which the onCollision event was triggered. An alternative to listening for OnCollision in a script on the entity | None |
| onDamage | [Event](event) | Called when this entity is damaged with the amount of damage, the entity causing the damage and a HitResult structure, as well as the mesh Entity from which the onDamage event was sent. An alternative to listening for OnDamage in a script on the entity | None |
| mesh | meshno | Get or change the mesh | None |

## Examples

### PlayAnimation

he following code plays the active animation looped, starting at 50% of the way through the animation, and makes each full cycle take 1 second no matter how long the animation is. To find out what animations are available on a mesh entity hover over the "Animations" button in the property editor.

```lua
self:GetEntity():PlayAnimation("active", { looping = true, playbackTime = 1.0, positionFactor = 0.5 })
```

