# GitLab CI Course - FreeCodeCamp  

## Progress  

- [x] ⌨️ Lesson 1 - Welcome (0:00:00​)
- [ ] ⌨️ Lesson 2 - Your first GitLab project (0:03:03​)
- [ ] ⌨️ Lesson 3 - Your first pipeline (0:13:00​)
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
6. Go to Build > Pipelines

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
