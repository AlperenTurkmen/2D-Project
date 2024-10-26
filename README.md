# BikeController Script Update

## Overview
This update fixes an issue in the `BikeController` script where the `SphereCollider` radius was accessed incorrectly, causing a runtime error. Due to time constraints and a heavy workload, I couldn't run the game or make further adjustments.

## Change Log
- **Modified Line**: Corrected how the `SphereCollider` is accessed.
- **Before**:
  ```csharp
  _rayLength = _baseRb.GetComponents<SphereCollider>().radius + 0.25f;
  ```
- **After**:
  ```csharp
  _rayLength = _baseRb.GetComponents<SphereCollider>()[0].radius + 0.25f;
  ```

## How to Use
Ensure the GameObject with the `_baseRb` `Rigidbody` has at least one `SphereCollider`. The script now calculates `_rayLength` using the radius of the first `SphereCollider`.
