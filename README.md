## Dev

1. Clone repository
2. Create .env file based on .env.template
3. Run command to load the submodules `git submodule update --init --recursive`
4. Run docker desktop
5. Run all services: Exec command `docker compose up --build`

### Steps to create Git Submodules

1. Create new repository on GitHub
2. Clone repository on your local machine
3. Add submodule, where `repository_url` is the repo url and `directory_name` is the folder name that you want to keep (may not exist on the project)

```
git submodule add <repository_url> <directory_name>
```

4. Add changes on the principal repo (git add, git commit, git push)
   Ej:

```
git add .
git commit -m "Add submodule"
git push
```

5. Initialize and update Sub-modules, when someone clones the repository for the first time, they should run the following command to initialize and update the sub-modules

```
git submodule update --init --recursive
```

6. To update the sub-module references

```
git submodule update --remote
```

## Important

If working in the repository that has the sub-modules, **first update and push** in the sub-module and **then** in the principal repository.

CARE!!!: If this is done the other way around, the sub-module references in the main repository will be lost and we will have to resolve conflicts.
