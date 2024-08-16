# vm-example-chart
[![Release Helm Charts](https://github.com/neilkuan/vm-example-chart/actions/workflows/release.yml/badge.svg)](https://github.com/neilkuan/vm-example-chart/actions/workflows/release.yml)
[![pages-build-deployment](https://github.com/neilkuan/vm-example-chart/actions/workflows/pages/pages-build-deployment/badge.svg?branch=gh-pages)](https://github.com/neilkuan/vm-example-chart/actions/workflows/pages/pages-build-deployment)

![](./docs/1.png)

## Use this chart
```bash
helm repo add vm-example-chart https://neilkuan.github.io/vm-example-chart/
```

## Normal release 
- Clone this project
  - `git clone https://github.com/neilkuan/vm-example-chart.git`
- Checkout new branch from main branch 
  - `git checkout -b feat-awesome-branch`
- make some magic 🪄
  - 🚨 🚨 🚨 do not forget update version in Chart.yaml 🚨 🚨 🚨
- Review by DevOps Team
- After merged , git tag version `v?.?.?` will trigger [workflow](https://github.com/neilkuan/vm-example-chart/actions/workflows/release.yml) release to `gh-pages` branch
  - `git tag v?.?.? && git push origin v?.?.?`

## Local build chart 
```bash
git checkout main
helm dependency build --skip-refresh

## make some magic 🚨 🚨 🚨 do not forget update version in Chart.yaml 🚨 🚨 🚨

```

## Local package chart 
```bash
## make some magic 🚨 🚨 🚨 do not forget update version in Chart.yaml 🚨 🚨 🚨

helm package .
```

## Local release chart 
```bash
git switch gh-pages

git pull origin gh-pages

rm -rf charts/

### Use none url 
helm repo index --url "" .

git add .

## 🚨 🚨 🚨 only need commit `index.yaml` and `vm-example-chart-x.x.x.tgz` 🚨 🚨 🚨
git status

git commit -a -m "release version"

git push origin gh-pages
```