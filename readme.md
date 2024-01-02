# GitLab CI Course - FreeCodeCamp  

## Progress  

- [x] ⌨️ Lesson 1 - Welcome (0:00:00​)
- [x] ⌨️ Lesson 2 - Your first GitLab project (0:03:03​)
- [x] ⌨️ Lesson 3 - Your first pipeline (0:13:00​)
- [ ] ⌨️ Lesson 4 - Help, my pipeline is not working (0:23:32)
- [ ] ⌨️ Lesson 5 - What is YAML? (0:26:22)
- [ ] ⌨️ Lesson 6 - What is a shell? (0:35:12)
- [ ] ⌨️ Lesson 7 - GitLab architecture (0:37:50)
- [ ] ⌨️ Lesson 8 - Pipeline stages (0:43:14)

## Lesson 2 - Your first GitLab project (0:03:03​)

1. Create GitLab account
2. Create private project
3. Change settings > Preferences  > Syntax highlighting > Monokai
4. On: Render whitespace characters in the web IDE
5. Create new file `.gitlab-ci.yml`
6. Go to Build > Pipelines > Run pipeline
7. Check pipeline logs

Push an existing Git repository

```bash
cd existing_repo
git remote add origin https://gitlab.com/mzn2/gitlabci.git
git branch -M main
git push -uf origin main

```

```yml
test:
    script: echo "Hello world"

```

## Lesson 3 - Your first pipeline (0:13:00​)

![pipeline](./attachments/pipeline1.jpg)

1. Add commands to write text file
2. By default pipeline uses Ruby Docker image
3. Add alternative Docker image - Linux `alpine`
4. Commit changes
5. Check pipeline logs

```yml
build laptop:
    image: alpine
    script: 
        - echo "Building laptop"
        - mkdir build
        - touch build/computer.txt
        - echo "Mainboard" >> build/computer.txt
        - cat build/computer.txt
        - echo "Keyboard" >> build/computer.txt
        - cat build/computer.txt
```  

Output

```bash
Running with gitlab-runner 16.6.0~beta.105.gd2263193 (d2263193)
  on blue-2.saas-linux-small-amd64.runners-manager.gitlab.com/default XxUrkriX, system ID: s_f46a988edce4
  feature flags: FF_USE_IMPROVED_URL_MASKING:true
Resolving secrets
00:00
Preparing the "docker+machine" executor
00:05
Using Docker executor with image alpine ...
Pulling docker image alpine ...
Using docker image sha256:f8c20f8bbcb684055b4fea470fdd169c86e87786940b3262335b12ec3adef418 for alpine with digest alpine@sha256:51b67269f354137895d43f3b3d810bfacd3945438e94dc5ac55fdac340352f48 ...
Preparing environment
00:01
Running on runner-xxurkrix-project-53471482-concurrent-0 via runner-xxurkrix-s-l-s-amd64-1704186592-2d594c12...
Getting source from Git repository
00:01
Fetching changes with git depth set to 20...
Initialized empty Git repository in /builds/mzn2/gitlabci/.git/
Created fresh repository.
Checking out 341525e5 as detached HEAD (ref is main)...
Skipping Git submodules setup
$ git remote set-url origin "${CI_REPOSITORY_URL}"
Executing "step_script" stage of the job script
00:00
Using docker image sha256:f8c20f8bbcb684055b4fea470fdd169c86e87786940b3262335b12ec3adef418 for alpine with digest alpine@sha256:51b67269f354137895d43f3b3d810bfacd3945438e94dc5ac55fdac340352f48 ...
$ echo "Building laptop"
Building laptop
$ mkdir build
$ touch build/computer.txt
$ echo "Mainboard" >> build/computer.txt
$ cat build/computer.txt
Mainboard
$ echo "Keyboard" >> build/computer.txt
$ cat build/computer.txt
Mainboard
Keyboard
Cleaning up project directory and file based variables
00:01
Job succeeded
```
