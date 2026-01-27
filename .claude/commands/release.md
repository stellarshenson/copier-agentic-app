# Release

Create a new patch release of copier-agentic-app.

## Steps

1. **Read current version** from `pyproject.toml`

2. **Increment patch version**:
   - Parse version string (e.g., "1.0.12")
   - Increment patch number (e.g., "1.0.13")
   - Update `pyproject.toml` with new version

3. **Update journal** if there are uncommitted substantive changes:
   - Add entry noting the release version
   - Include summary of changes since last release

4. **Commit changes**:
   ```bash
   git add pyproject.toml .claude/JOURNAL.md
   git commit -m "chore: release v<new_version>"
   ```

5. **Push to remote**:
   ```bash
   git push
   ```

6. **Create and push tag**:
   ```bash
   git tag v<new_version>
   git push origin v<new_version>
   ```

7. **Report** the new version number to user

## Example

If current version is `1.0.12`:
- New version: `1.0.13`
- Commit message: `chore: release v1.0.13`
- Tag: `v1.0.13`

## Notes

- Only increments patch version (x.y.Z)
- For minor or major version bumps, manually edit pyproject.toml first
- Ensure all changes are committed before running release
