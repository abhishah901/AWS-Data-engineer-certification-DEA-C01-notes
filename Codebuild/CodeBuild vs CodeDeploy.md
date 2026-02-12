# CodeBuild vs CodeDeploy

## CodeBuild

**Purpose:** Build and test code

**What it does:**
- Compiles source code
- Runs unit tests
- Creates deployment artifacts (JAR, ZIP, Docker image)
- Runs in containers

**Input:** Source code
**Output:** Build artifacts

**Use cases:**
- Compile Java/Node.js/Python
- Run test suites
- Build Docker images
- Create deployment packages

**Configuration:** buildspec.yml

## CodeDeploy

**Purpose:** Deploy applications to infrastructure

**What it does:**
- Deploys artifacts to EC2, Lambda, ECS, on-premises
- Manages deployment strategies (rolling, blue/green)
- Traffic shifting
- Health monitoring
- Rollback on failure

**Input:** Build artifacts
**Output:** Running application

**Use cases:**
- Deploy to EC2 instances
- Update Lambda functions
- ECS service updates
- Blue/green deployments

**Configuration:** appspec.yml

## Typical Pipeline Flow

Source (CodeCommit) → Build (CodeBuild) → Deploy (CodeDeploy)

CodeBuild creates it → CodeDeploy deploys it

## Key Differences

**CodeBuild:**
- Pre-deployment (build phase)
- Creates deployable artifacts
- Test execution
- Build environment

**CodeDeploy:**
- Post-build (deploy phase)
- Places artifacts on targets
- Deployment strategies
- Production rollout

## Decision Tree

Need to compile/test? → CodeBuild
Need to deploy to instances? → CodeDeploy
Full pipeline? → Both (Build then Deploy)

## Exam Signals

"Compile code" → CodeBuild
"Run tests" → CodeBuild
"Create Docker image" → CodeBuild
"Deploy to EC2" → CodeDeploy
"Blue/green deployment" → CodeDeploy
"Rolling update" → CodeDeploy
"Traffic shifting" → CodeDeploy

## Common Exam Pattern

Wrong: CodeBuild deploys to EC2
Right: CodeBuild creates artifacts, CodeDeploy deploys

Wrong: CodeDeploy compiles code
Right: CodeDeploy only deploys pre-built artifacts