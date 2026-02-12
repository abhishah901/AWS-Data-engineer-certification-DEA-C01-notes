# runOrder in CodePipeline

Controls execution sequence of actions within a stage.

## Purpose
- Actions with same runOrder execute in parallel
- Actions with different runOrder execute sequentially
- Lower numbers run first

## Example
```yaml
stages:
  - name: Build
    actions:
      - name: BuildApp
        runOrder: 1
        actionTypeId:
          category: Build
          provider: CodeBuild
      
      - name: BuildTests
        runOrder: 1  # Runs parallel with BuildApp
        actionTypeId:
          category: Build
          provider: CodeBuild
      
      - name: PackageArtifacts
        runOrder: 2  # Runs after both builds complete
        actionTypeId:
          category: Build
          provider: CodeBuild
```

## Key Points
- Default: runOrder = 1
- Range: 1-999
- Stage completes when all actions finish
- Use for optimization (parallel builds) or dependencies (sequential steps)

## Common Pattern
```
runOrder: 1 → Multiple parallel builds
runOrder: 2 → Combine/package artifacts
runOrder: 3 → Deploy
```