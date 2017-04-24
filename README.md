# JavaZone talk 2017

## Title

Things that go wrong when deploying Java with Kubernetes (and how to avoid them)

## Abstract

It's hard to walk when the earth quakes, and it's hard to run when the infrastructure doesn't rock. We've had both.

FINN.no is moving about four hundred apps from a legacy deployment system to Docker and Kubernetes, and most of those are written in Java. We've failed at (and fixed) a lot of things, including common security patches and secrets in the environment, and we've improved our application code along the way. Now it's time to share our solutions to some of our mess-ups!

Learn how we're using Docker and Kubernetes at FINN; how we've ensured quick security patches across all Java apps; what we've spent days on to simplify the migration path for the developers; which requirements we've found useful to place on the developers; and how our code has been forced to improve through the migration.

## Audience level

You're familiar with containers on a conceptual level, and want to know what went wrong when FINN.no deployed Java apps inside them. Kubernetes is used as the case, but most lessons learned are applicable to all sorts of deployments. There's no code, but plenty of useful real-world cases!

## Keywords

Java deployment, containers, Docker, Kubernetes, lessons learned

## Outline

- Part 1: Intro to Docker and Kubernetes at FINN (5 minutes)
  - You can sell your stuff through our website! Or sell your apartment, or post a job ad.
  - Website, administration page (for partner businesses), statistics, search, map service
  - How do we do Docker at FINN (adoption, migration process)
  - Kubernetes is fun!
- Part 2: Manage hundreds of services (15 minutes)
  - Common base images for Java 8 and Tomcat 8 (not required, but recommended)
  - Focus on drop-in to ease migration (can't do the same with Node)
  - Managing adoption and migration path
  - Automatically patching hundreds of services
  - Secrets (passwords and API keys) are weird, put them in the environment
- Part 3: Forced app improvement is good (25 minutes)
  - Environmental configuration (Constretto isn't for everyone, ConfigMaps are now an option)
  - Replicas (this time an _educated_ guess!)
  - Resource limits (memory and CPU): tuning is hard (but much cheaper)
  - Automatic memory limits for heap and metaspace (and CPU with 8u131)
  - Know your runtime! Way less scary to bump the JRE per app
  - No more persistent disk
  - Opt-out metrics (with Prometheus) (what about http-server-less apps?)
  - Liveness &amp; readiness checks, and how we use them (what about http-server-less apps?)
  - Only kubectl as app admin interface (no more abstraction named `iad` for `internet Ad`)
- Finale: Conclusion (5 minutes)
  - Brief recap of what we've done so far
  - Have a strategy! Think about patching!
  - Containerisation forced better code
- Questions (10 minutes)

## Speaker

Martin spends most of his time at FINN.no writing Java and JavaScript, and got involved in FINN's migration to Docker and Kubernetes. Some days that's fun, and some days there's craft beer after work. He runs his own server with Docker but not Kubernetes.

Most of his team's stack is built from Java and Node, which puts him right in the target audience for things like company-wide common Java Docker images and their (sometimes strange) behaviour. His love for software development leads him to promote his team's interests in infrastructure discussions, but his passion for infrastructure makes him frequently side with the infrastructure team in product talk.

He's done a few in-house talks to spread the love for Kubernetes and its tooling, teaches web development to final-year Bachelor students, and believes it's important to share some of FINN's experiences with the world.
