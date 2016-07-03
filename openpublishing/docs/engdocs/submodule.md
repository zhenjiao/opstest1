#Submodule
A submodule allows you to keep another Git repository in a subdirectory of your repository. The other repository has its own history, which does not interfere with the history of the current repository. This can be used to have external dependencies such as third party themes for example.

In OPS, submodule can be used as third party css, js, fonts, images, templates. The repository don't need to care about the submodule's content's updation. The OPS will auto download the latest content and include it to repository.

##How to add the submodule?
```
git submodule add -b <branch of DocsThemes to add, usually ‘master’> -f --name <submodule name> -- <submodule URL, i.e. https://github.com/Microsoft/templates.docs.msft> <submodule folder, i.e. A/B/_themes>
```
**[IMPORTANT] The ```<submodule name>``` must be unique in one repository.You can use ```git submodule status``` to list all submodules and to check the submodules' name.**

##How to delete the submodule?
1. deinitialize the submodules with command ```git submodule deinit -f .```
2. delete the .git\modules directory if exist.
3. delete the submodules in the .gitmodules file. (If want to remove all submodules, just delete .gitmodules file.)
4. commit the changes.

##How to update the submodule?
### only update the commit id of submodule
1. run ```git submodule update --remote```
2. commit the changes.

### update the configuration of submodule.
1. should first delete the submodule.
2. add the new submodule.

##Build Logic
OPbuild will auto pull the latest submodules of user specified branch(if user haven't setted, then master branch will be used.) to local, even you add an old version of the submodule.

##Work around for specified commit id.
If the developer want to use a specific commit id of submodule, who should create a new branch of that commit id, and update the submodule to point to that branch.
