# 

Perform a comprehensive, READ-ONLY local development and debugging audit of this repository.

Context:
- macOS Apple Silicon (M5 Max)
- OpenJDK 21
- Gradle 9.0.0 per team guidance
- IntelliJ IDEA Ultimate
- Claude Code connected to IntelliJ through company-approved AWS Bedrock
- Repository has already cloned and built successfully

Your tasks:
1. Identify whether this is an executable Java application, Spring Boot service, shared library, monorepo, or multi-module project. Identify entry points and runnable modules.
2. Inspect settings.gradle, build.gradle files, Gradle wrapper, application configuration, README, Docker/Podman files, scripts, and existing IntelliJ run configurations. Do not assume they exist.
3. Determine the actual required Java version, Gradle version, application profiles, environment variables, JVM arguments, startup commands, and service ports. Distinguish required from optional settings.
4. Identify dependencies required to run locally: databases, queues, other services, containers, VPN, credentials, cloud access, and internal artifact repositories. List variable names only; never display secret values.
5. Determine whether the application can run fully locally, requires a dev environment, or is not independently runnable. Explain the evidence and blockers.
6. Recommend the exact IntelliJ Run/Debug configuration: configuration type, module or main class, JDK, working directory, program arguments, VM options, environment-variable names, and before-launch tasks. Only specify values supported by repository evidence.
7. Identify the safest existing unit or integration test to debug first, and explain where to place a breakpoint.
8. Provide exact build, test, and startup commands where verified. Do not execute startup commands yet.
9. Assess whether Gradle 9.0.0 is actually required by the repository wrapper and whether the configured Java 21 is compatible.
10. Provide a concise step-by-step local setup plan, with blockers and questions for my team lead.

Safety rules:
- READ-ONLY inspection only. Do not edit files, create configurations, install dependencies, start services, launch containers, or make network requests.
- Do not run Gradle tasks or scripts during this audit; inspect their definitions instead.
- Do not access, print, or summarize secret values, credential files, tokens, or private keys.
- Do not execute database migrations, deployments, cloud operations, or destructive commands.
- Cite repository file paths and relevant line numbers for findings.
- Clearly separate VERIFIED facts, INFERENCES, and UNKNOWN items.

Output format:
A. Repository type and runnable modules
B. Local prerequisites and blockers
C. Exact IntelliJ Run/Debug setup
D. Safest first debugging exercise
E. Commands to run after approval
F. Questions for my team lead

Do not make any changes. Wait for my approval before implementing anything.