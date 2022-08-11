---
title: useJoint
---

!!!module_summary title=useJoint|sourcePath=/hooks/useJoint.svelte|name=useJoint|from=rapier|type=component

Use this hook to initialize any [Rapier joint](https://rapier.rs/docs/user_guides/javascript/joints).

:::admonition type="info"
This example initializes a `RevoluteImpulseJoint` manually. Most of the times you'd want to use a shortcut hook (like ['useRevoluteJoint'](/rapier/use-revolute-joint)) to initialize a joint. This hook is used internally to initialize the currently available joints.
:::

```svelte
<script>
	import { useJoint, RigidBody, Collider } from '@threlte/rapier'

	const { joint, rigidBodyA, rigidBodyB } = useJoint((rbA, rbB, { world, rapier }) => {
    const params = rapier.JointData.revolute(
      { x: 0, y: 10, z: 1 },
      { x: 0, y: 0, z: 0 },
      { x: 0 y: 1, z: 0 }
    )
    return world.createImpulseJoint(params, rbA, rbB, true)
  })
</script>

<RigidBody bind:rigidBody={$rigidBodyA}>
	<Collider shape="cuboid" args={[1, 1, 1]} />
</RigidBody>

<RigidBody bind:rigidBody={$rigidBodyB}>
	<Collider shape="cuboid" args={[1, 1, 1]} />
</RigidBody>
```

The callback to initialize the Joint is called when both `rigidBodyA` and `rigidBodyB` are defined.

!!!

### Signature

```ts
const {
	joint: Writable<T>
	rigidBodyA: Writable<RAPIER.RigidBody>
	rigidBodyB: Writable<RAPIER.RigidBody>
} = useJoint<T extends RAPIER.ImpulseJoint | RAPIER.MultiBodyJoint>(
	initializeJoint: (rigidBodyA: RAPIER.RigidBody, rigidBodyB: RAPIER.RigidBody, RapierContext) => T
)
```