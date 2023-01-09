---
layout: post
current: post
cover: False
navigation: True
title: 프로그래머스 - 타겟넘버
date: 2023-01-08 00:23:00
tags: [algorithm]
class: post-template
subclass: 'post tag-algorithm'
author: moonyvibes
---
{% include algorithm-table-of-contents.html %}

![image-20230109022031773](../../assets/images/image-20230109022031773.png)

~~~python
from collections import deque

def solution(numbers, target):
    answer = 0
    queue = deque([[0, 0]])
    while queue:
        accum, idx = queue.popleft()

        if idx == len(numbers):
            if accum == target:
                answer += 1

        else:
            num = numbers[idx]
            queue.append([accum - num, idx + 1])
            queue.append([accum + num, idx + 1])

    return answer
~~~