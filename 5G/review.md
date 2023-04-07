# 复习

## 1. option 组网方案

### 1.1 option1

无线侧使用LTE，核心网侧使用EPC，是属于4G的方案

### 1.2 option2

无线侧是NR，核心网是5GC，即无线和核心网侧全部更新换代，狭义的5G网指的就是SA组网

### 1.3 option3

无线接入网是LTE+NR，核心网是EPC，是NSA组网方案

### 1.4 option4

无线接入网是LTE+NR，核心网是5GC，在这种组网方式下，对于UE而言，无线接入网有两种接入的方案:LTE+NR

### 1.5 option5

为SA组网的方案，无线接入网是LTE，核心网是5GC

### 1.6 option6

NR+EPC 网是LTE+NR，核心网是EPC，是SA组网方式，但是已经被废弃

### 1.7 option7

无线接入网是LTE+NR，核心网是5GC，且终端控制由LTE进行控制，其组网方式也是NSA

## 2. 5G的组件

### 2.1 RRU

RRU是射频远程单元，其防护等级是60

### 2.2 CU

CU为协议栈的较高层提供支持，例如SDAP，PDCP和RRC，DU为协议栈的较低层提供支持

一个gnb对应一个CU，但是一个CU可用控制多个DU


![image.png](https://s2.loli.net/2023/04/06/HYNCWDRhXfr9wEs.png)

### 2.3 DU

DU是分布式单元，可以支持一个或者多个cell


### 2.4 5G核心网

5G核心网的网元：UPF，AUSF，UDM，AMF，SMF，PCF，NSSF，NRF，NEF，需要注意的是AAU不属于。



