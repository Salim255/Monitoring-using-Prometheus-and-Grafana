# Monitoring-using-Prometheus-and-Grafana

## 🍎 Prometheus is a very common application to use in the kubernetes space(an open source), so Prometheus is capable of gathering metrics from our running kubernetes cluster

## 🍎 Graphical tool of your choice: and a very common choice here is 🍉GRAFANA🍉 a very open tool and it can integrate with many source of data Grafana usually sits on top of Prometheus

## 🍎 So Prometheus combined with Grafana, is very common and powerful set of tools, that professional projects use to monitor their clusters.

## 🍎 Configuring Prometheus would be a very time consuming job, you would first of all need to learn how Prometheus works at a pretty deep level.

## 🍎 install eksctl: run => brew tap weaveworks/tap brew install weaveworks/tap/eksctl

## To list all the cluster in our AWS account : aws eks list-clusters

## Create cluster =>

### 1\ export RELEASE=1.25 .0

### 2\ Check the download of step (1) we run : curl -LO https://storage.googleapis.com/kubernetes-release/release/v$RELEASE/bin/linux/amd64/kubectl

## 🍎Create A cluster run: eksctl create cluster --name fleetman

### kubectl apply -f storage-aws.yaml

## 🍎 delete cluster run : eksctl delete cluster salimm

## 🍎 Installing Monitoring system inside my cluster

### 1\ kubectl apply -f crds.yaml

### 2\kubectl apply -f eks-monitoring.yaml

### 3\ kubectl get po -n monitoring

### 4\ kubectl get svc -n monitoring

### 5\ kubectl edit svc monitoring-kube-prometheus-prometheus -n monitoring, to set a loadbalancer

### 6\ Using the Loadbalancer string that associate to monitoring-kube-prometheus-prometheus, with the port 9090 we can get to prometheus page

### 🍎7\ Grafana : kubectl edit svc monitoring-grafana -n monitoring
