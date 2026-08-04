# Bugs

## BUG-001 | Open | High

Summary
- Login sometimes hangs.

Reproduce
1. Open app
2. Login with Google

Cause
- Unknown

Fix
- Investigating

---

## BUG-002 | Fixed | Medium

Summary
- Notes not refreshing.

Cause
- Missing invalidate().

Fix
- Added cache invalidation.

Version
- Fixed in v0.3.2
