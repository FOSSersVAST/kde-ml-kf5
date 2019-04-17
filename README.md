# KDE Malayalam Localization

This repo has the `.po` gettext source files of KDE. The source files from here is imported to Weblate.

Currently KDE K Framework 5 trunk files are stored here.

[Weblate Instance Source](https://github.com/subins2000/kde-weblate)

## Adding a new package

Each package should be in a separate branch

Find the package to add from [here](https://l10n.kde.org/stats/gui/trunk-kf5/package/). Example : `applications`, `kde-workspace`

* Set the package :
  ```
  git checkout master
  export REPO_ROOT=$PWD
  export PACKAGE=''
  ```
* Make folders if haven't done already :
  ```
  mkdir $REPO_ROOT/locales/ $REPO_ROOT/locales/templates $REPO_ROOT/locales/ml
  ```
* Make a branch for the package :
  ```
  git checkout -b $PACKAGE
  ```
* Get the files :
  ```
  mkdir $REPO_ROOT/locales/templates/$PACKAGE
  cd $REPO_ROOT/locales/templates/$PACKAGE
  svn checkout svn://anonsvn.kde.org/home/kde/trunk/l10n-kf5/templates/messages/$PACKAGE .

  mkdir $REPO_ROOT/locales/ml/$PACKAGE
  cd $REPO_ROOT/locales/ml/$PACKAGE
  svn checkout svn://anonsvn.kde.org/home/kde/trunk/l10n-kf5/ml/messages/$PACKAGE .
  ```
* Commit & Push :
  ```
  cd $REPO_ROOT
  git add $REPO_ROOT/locales
  git commit $REPO_ROOT/locales -m "Added $PACKAGE locale files"
  git push --set-upstream origin $PACKAGE
  ```
* To pull changes from KDE SVN upstream :
  ```
  git checkout $PACKAGE
  cd $REPO_ROOT/locales/templates/$PACKAGE
  svn update
  cd $REPO_ROOT/locales/ml/$PACKAGE
  svn update
  cd $REPO_ROOT
  git commit $REPO_ROOT/locales -m "Merge changes from KDE upstream"
  ```