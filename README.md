# CD-AWS
Continuous delivery on AWS cloud

### PROBLEMS USUALLY ENCOUNTERED FOR CONTINUOS DELIVERY:
- In an Agile SDLC, there will be frequent code changes; manual code deployment is time consuming.
- Developers and testers are not equipped with OPS knowledge.
- Dependencies on OPS team.
- CI/CD server maintenance.
- Operational overhead to maintain server like jenkins, nexus, sonar, git, QA server for testing.

### SOLUTION:
- PASS AND SAAS cloud services
- Disposable environment
- Automate CI/CD process
- Build, test, deploy and test for every commit.

### BENEFITS OF CD PIPELINE:
- Agile
- No OPS
- No human intervention
- Fault isolation
- Short MTTR(Mean time to repair)

### AWS SERVICES FOR THIS PROJECT:
- Code commit (Version control system)
- Code artifact (maven repository for dependencies)
- Code build (Build service for AWS)
- Code deploy (Artifact deployment)
- Sonarcloud (Sonarqube cloud based tool)
- Checkstyle (code analysis from build job)
- Selenium ( Software testing , code build and others)
- Beanstalk (For hosting application)
- RDS (Database for application service)
- Codepipeline (service to integrate all jobs together)

### COMPARISON:
- AWS CODE COMMIT — GITHUB
- AWS CODEARTIFACT — NEXUS SONATYPE
- AWS CODE BUILD — JENKINS JOBS
- SONARCLOUD — SONARQUBE SERVER
- AWS CODEPIPELINE — JENKINS PIPELINE
- BEANSTALK INSTANCES — TOMCAT VM(VIRTUAL MACHINE)
- RDS(Relational database service) — MYSQL ON VM

### FLOW OF EXECUTION AFTER BUILDING AND TESTING YOUR CONTINUOS INTEGRATION PIPELINE JOB:
- Create Beanstalk and RDS
- Update RDS(Relational database service) security group
- Deploy DB in RDS
- Switch to CD-AWS branch
- Update settings.xml and pom.xml
- Create another build job to create artifact with buildspec file in CD-AWS branch in your github.
- Create a deploy job to beanstalk
- Create a build job for software testing(selenium script)
- Upload screenshot to s3 bucket
- Update pipeline: (a) Codecommit (b)Testcode (c) Build and store (d) Deploy to S3 bucket (e) Build and release (f) Deploy to beanstalk (g) Build job for selenium test script (h) Upload all result
- Test pipeline.
