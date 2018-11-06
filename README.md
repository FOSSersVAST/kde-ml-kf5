# KDE Malyalam Localization

Get latest `.po` files of a project :

```
export REPO_ROOT=$PWD
export PROJECT=''

mkdir $REPO_ROOT/locales/templates/$PROJECT
cd $REPO_ROOT/locales/templates/$PROJECT
svn checkout svn://anonsvn.kde.org/home/kde/trunk/l10n-kf5/ml/messages/$PROJECT .

mkdir $REPO_ROOT/locales/ml/$PROJECT
cd $REPO_ROOT/locales/ml/$PROJECT
svn checkout svn://anonsvn.kde.org/home/kde/trunk/l10n-kf5/ml/messages/$PROJECT .
```
