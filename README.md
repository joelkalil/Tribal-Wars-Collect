# Collect System Tribal Wars

## Introduction

You can check the app [there](https://tribal-wars-collect.vercel.app/).

This project consists in a calculator to optimize the collect in Tribal Wars. But how exactly it works? It's simple, the objective is to reach the higher value of farm/minute, and to calculate it, I had to considered multiples scenarios, but in the most part, the base approach was to consider equal time.

In Tribal Wars, we have 4 collect options, where the resource collect is proportional to the capacity of each ensemble of troops:
- Low Collect --> 10% Total Capacity
- Medium Collect --> 25% Total Capacity
- High Collect --> 50% Total Capacity
- Extreme Collect --> 75% Total Capacity

Besides that, the time of each collect is based in the total capacity. To mensure that, I got multiples samples and make an equation to represent this duration.
The equation is:

Duration(Farm) = 2,92 * e^05 * Farm + 0,0155 (We got a decimal value to represents the duration)

So now, we can calculate the total capacity and then get the total farm based in which distribution we'll consider. With the total farm, we stipulate the duration and gets the farm/minute.

To make this easily to understand, I'll use an example, fix the value of spears in 100, and then try some possibilities. Regard the results:

Put all in Low Collect:

    Farm:   250
    Duration:   00:32:50
    Farm/Minute:    7,61

Put all in Medium Collect:

    Farm:   625
    Duration:   00:48:36
    Farm/Minute:    12,86

And so on. Then I'll show the farm/minute of each possibility tested.

*Remember that for multiples collections, we will consider the same collect time on them.*

1. Only Low Collect = 7,61
1. Only Medium Collect = 12,86
1. Only High Collect = 16,69
1. Only Extreme Collect = 18,53
1. All Collections = 20,57
1. Low/Medium/High Collections = 16,34
1. Low/Medium/Extreme Collections = 16,79
1. Low//High/Extreme Collections = 18,62

So, we can see that to reach the best farm/minute, we should use the 4 collections at the same time.


## About the project

![](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white) ![](https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vue.js&logoColor=4FC08D) ![](https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E) ![](https://img.shields.io/badge/HTML-e34c26?style=for-the-badge&logo=html5&logoColor=white) ![](https://img.shields.io/badge/CSS-264de4?&style=for-the-badge&logo=css3&logoColor=white)

The project is a single page application, quite simple, made using Vue.Js.

## Project setup

```
# npm
npm install
```

### Compiles and hot-reloads for development

```
# npm
npm run dev
```

### Compiles and minifies for production

```
# npm
npm run build
```

### Lints and fixes files

```
# npm
npm run lint
```
