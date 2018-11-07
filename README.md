# KDE Malayalam Localization

Sources for KDE Malayalam Localization. [KDE-ML Telegram Group](https://t.me/kde_ml)

## Adding a new package

Each package should be in a separate branch

Find the package to add from [here](https://l10n.kde.org/stats/gui/trunk-kf5/package/). Example : `applications`, `kde-workspace`

* Set the package :
  ```
  export REPO_ROOT=$PWD
  export PACKAGE=''
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
