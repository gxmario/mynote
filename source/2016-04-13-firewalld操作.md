---
layout: post
title:  "fiewalld操作"
date:   2016-04-13 19:11:15 +0800
categories: jekyll update
---

## 查看firewalld状态
systemctl status firewalld
## 停止firewalld
systemctl stop firewalld
# firewall-cmd 指令

---

## 查看firewalld状态
firewall-cmd --state

## 查看某个接口是属于哪个zone的
firewall-cmd --get-zone-of-interface=eth0

## 查看某个zone里开启了哪些服务、端口、接口：
firewall-cmd --zone=public --list-all

## 查看某个zone里开启了哪些服务：
firewall-cmd --zone=public --list-services

## 查看某个zone里开启了哪些端口：
firewall-cmd --zone=public --list-ports

## 把接口加入到某个zone：
firewall-cmd [--zone=<zone>] --add-interface=<interface>

## 把eth0加入到默认zone
firewall-cmd --add-interface=eth0

## 使设定永久生效
firewall-cmd --permanent *******
(reload之后生效)

## 获取所有服务
firewall-cmd --get-services

## 为zone添加端口/协议
firewall-cmd [--permanent] [--zone=zone] --add-port=portid[-portid]/protocol [--timeout=timeval]
The port can either be a single port number or a port range portid-portid. The protocol can either be tcp or udp.

## 为zone移除端口/协议
[--permanent] [--zone=zone] --remove-port=portid[-portid]/protocol

## 为zone添加服务
[--permanent] [--zone=zone] --add-service=service [--timeout=timeval]

## 为zone移除服务
[--permanent] [--zone=zone] --remove-service=service [--timeout=timeval]
