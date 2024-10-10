# Gitflow Commands
The overall flow of Gitflow is:
1. A develop branch is created from main
2. A release branch is created from develop
3. Feature branches are created from develop
4. When a feature is complete it is merged into the develop branch
5. When the release branch is done it is merged into develop and main
6. If an issue in main is detected a hotfix branch is created from main
7. Once the hotfix is complete it is merged to both develop and main

## Clone the code
1. git clone https://github.com/Mija9961/gitflow.git

## Add some code (optional) and push it
1. git add README.md
2. git commit -m "first commit"
3. git push origin master

## Create a develop branch
1. git branch develop
2. git checkout develop
3. git push -u origin develop

## Create a feature branch
1. git checkout develop
2. git checkout -b feature_branch
3. git add .
4. git commit -m "Changes made in feature branch"
5. git push -u origin feature_branch

## Merge feature branch to develop
1. git checkout develop
2. git merge feature_branch
3. git push -u origin develop

## Create a release branch
1. git checkout develop
2. git checkout -b release/0.1.0

## Merge release branch to main/master
1. git checkout main
2. git merge release/0.1.0
3. git push -u origin main

## Create a tag to main/master
1. git checkout main
2. git tag -a v1.1.0 -m "xyz feature is released in this tag."
3. git tag
4. git push origin v1.0.1

## Create a hotfix branch
1. git checkout main
2. git checkout -b hotfix_branch
3. git add .
4. git commit -m "Changes made in hotfix branch"
5. git push -u origin hotfix_branch

## Merge hotfix branch to both main/master and develop
1. git checkout main
2. git merge hotfix_branch
3. git push -u origin main
4. git checkout develop
5. git merge hotfix_branch
6. git push -u origin develop
7. git branch -d hotfix_branch