# **Project 2: CI/CD Pipeline with Azure DevOps
## **Complete Implementation Documentation

---

## **PROJECT OVERVIEW**


Built a complete CI/CD pipeline that:
- Automatically builds code when pushed to GitHub
- Created deployable web packages
- Deployed through 3 environments (DEV -> STAGING -> PRODUCTION)
- Fully automated end-to-end deployment

---

## **ARCHITECTURE**
```

Developer pushes code
|
GitHub detects change
|
Azure DevOps Build Pipeline triggers
|
Build completes, artifact created
|
DEV deployment (Automatic)
|
STAGING Deployment (Automatic)
|
PRODUCTION Deployment (Automatic)
|
Website updated live!
```

---


## **PIPELINE STAGES**

### **Stage 1: BUILD**
- Triggers on GitHub push (main branch)
- PowerShell creates web package
- Copies all HTML files
- Publishes artifacts (drop/web)
- **Status:** ✅ Working

### **Stage 2: DEPLOY TO DEV**
- Depends on: Build success
- Environment: DEV
- VMs: vm-web-1, vm-web-2
- **Status:** ✅ Working

### **Stage 3: DEPLOY TO STAGING**
- Depends on: DEV deployment success
- Environment: STAGING
- VMs: vm-we-1, vm-web-2
- **Status:** ✅ Working

### **Stage 4: DEPLOY TO PRODUCTION**
- Depends on: STAGING deployment success
- Environment: PRODUCTION
- VMs: vm-web-1, vm-web-2
- **Status:** ✅ Working

---

## **COMPONENTS CREATED**

### **GITHUB**
- ✅ Repository: azure-devops-app
- ✅ Code: index.html
- ✅ Pipeline config: azure-pipelines.yml
- ✅ Webhook: Enabled (auto-triggers builds)

### **Azure DevOps**
- ✅ Organization: sarvesh-devops
- ✅ Project: azure-cicd
- ✅ Build Pipeline: Multi-stage YAML
- ✅ Environments: DEV, STAGING, PRODUCTION

### **Environments**
- ✅ DEV: vm-web-1, vm-web-2 registered
- ✅ STAGING: vm-web-1, vm-web-2 registered
- ✅ PRODUCTION: vm-web-1, vm-web-2 registered

---

## **PIPELINE CONFIGURATION**

### **Trigger**
```
On every push to main branch
Automatic build starts
```
### **Build Steps**
```
1. Create web package directly
2. Copy all .html files
3. Publish as artifact (drop/web)
```

### **Deployment Flow**
```
Build Success -> DEV Deploy -> STAGING Deploy -> PORD Deploy
(Each Stage waits for previous to succeed)
```

---

## **HOW IT WORKS (Step-by-Step)**

### **When Developer Pushes Code:**
```
1. Developer edits index.html locally
2. git add .
3. git commit -m "message"
4. git push origin main
5. GitHub receives push
6. GitHub webhook triggers azure DevOps
7. Build pipeline starts automatically
8. PowerShell tasks run
9. Web package created
10. Artifact published
11. DEV deployment starts
12. Files deployed to vm-web-1 and vm-web-2 (DEV)
13. DEV deployment completes
14. STAGING deployment starts
15. Files deployed to vm-web-1 and vm-web-2 (STAGING)
16. STAGING deployment completes
17. PRODUCTION deployment starts
18. Files deployed to vm-web-1 and vm-web-2 (PRODUCTION)
19. PRODUCTION deployment completes
20. Website updated live!
```

**Total time:** ~3-5 minutes from push to live 


---

## **BUILD ARTIFACTS**


Generated artifact structure:
```
drop/
   |__web/
    |-- index.html
    |__ [other HTML Files]
```

Artifact Location: Azure DevOps artifact repository


---


## **TESTING PERFORMED**

### **Test 1: Manual Build Trigger
- ✅ Triggered manually
- ✅ All 4 stages completed 
- ✅ Artifact created

### **Test 2: Code Push Trigger
- ✅ Modified index.html
- ✅ Pushed to GitHub
- ✅ Build triggered automatically
- ✅ All stages completed
- ✅ Full pipeline working end-to-end


---


### **Deployments**
- ✅ DEV: **Ready**
- ✅ STAGING: **Ready**
- ✅ PRODUCTION: **Ready**


---


## **KEY BENEFITS**

✅ **Automation**
- No manual builds needed
- No manual deployments needed
- Fully automated workflow

✅ **Speed**
- Code to production in minutes
- No waiting for manual processes

✅ **Visibility**
- Can see pipeline progress in Azure DevOps
- Can see deployment logs
- Can track every change

✅ **Safety**
- Change go through DEV first
- Then STAGING for validation
- Finally PRODUCTION
- Multi-stage ensures quality


---


## **WHAT THIS DEMONSTRATES**

This CI/CD pipeline shows:
- **Continuous Integration** - Code automatically builds
- **Continuous Deployment** - Code automatically deploys
- **Multi-stage Pipeline** - DEV -> STAGING -> PRODUCTION
- **Automation** - No manual intervention
- **DevOps Best Practices** - Industry standard setup

---

## **USE CASES**

This Pipeline is ideal for:
- Web application 
- SaaS products
- Microservices
- APIs
- Any application needing frequent updates


---


## **PROJECT COMPLETION STATUS**


| **COMPONENTS | **STATUS** |
|--------------|------------|

[GitHub Repository] / [✅ Created]
[Application Code] / [✅ Created]
[Pipeline YAML] / [✅ Created]
[Azure DevOps Project] / [✅ Created]
[Build Pipeline] / [✅ Working]
[Environment] / [✅ Created]
[VM Registration] / [✅ Complete]
[Multi-Stage Pipeline] / [✅ Working]
[End-to-End Testing] / [✅ Complete]
[Documentation] / [✅ Complete]


---


## **COMPLETE INTEGRATION**

This Project 2 integrates with:
- **Project 1:** Infrastructure (VMs, Load Balancer)
- **Project 3:** Monitoring (Auto-scaling, Alerts)


Together they from a **complete DevOps solution**.


---


**Project 2 Status: ✅ COMPLETE & FULLY TESTED**

Build pipeline working, deployments configured, end-to-end automation verified.
```

## **PROJECT 2 IS NOW 100% COMPLETE!**

## **Currently We Have**
✅ GitHub Repo
✅ Build pipeline (WORKING)
✅ Multi-stage deployment (DEV -> STAGING -> PRODUCTION)
✅ Environments configured
✅ VM's registered
✅ End-to-end testing (PASSED)
✅ Documentation complete 