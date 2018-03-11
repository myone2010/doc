# 웹 콘솔/대시보드 문서

## 지원 브라우저

![Chrome](https://raw.github.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png) 
--- |
Latest ✔ 

## 주요 라이브러리
> Web-console 핵심 라이브러리만 기술

- Django 2.0
- Django REST Framework 3.7.7
- requests 2.18.4
- apscheduler 3.5.1
- Materialize CSS
- Wavesurfer.js

## 디렉토리 구조

> Folder structure options and naming conventions for software projects

### Top-level 디렉토리

    .
    ├── Dockerfile                   # 도커파일
    ├── README.md                    # 설치 및 사용방법
    ├── docs                         # 웹 콘솔/대시보드 문서
    ├── hana_project                 # Django 기본 설정 및 URL 연결
    ├── static                       # 정적 파일 (js,css,img)
    ├── templates                    # html 템플릿 파일
    ├── users                        # Login, Signup, 대시보드 페이지 관련 view, url
    ├── fileupload                   # 음성 업로드 페이지 관련 model, view, url, templatetags
    ├── api                          # Audio 모델을 제외한 모든 모델 (Decode, After, Cpu-usage 등)
    ├── manage.py                    # Django 기본 실행 파일
    ├── requirements.txt             # python 필요 패키지
    └── Pipfile                      # pipenv 환경 설치 파일


> Use short lowercase names at least for the top-level files and folders except
> `LICENSE`, `README.md`



## 클래스 다이어그램

### 음성인식, 후처리 모델 관계
![alt text][class-image1]

### 대시보드 및 기타 API
![alt text][class-image2]

[class-image1]: https://github.com/myone2010/doc/blob/master/%EA%B7%B8%EB%A6%BC1.png?raw=true
[class-image2]: https://github.com/myone2010/doc/blob/master/%EA%B7%B8%EB%A6%BC2.png?raw=true

해당


## 클래스 다이어그램

Option 1: TOS Check On Sign In
```python

In your root urlconf file ``urls.py`` add:

.. code-block:: python

    from tos.views import login

    # terms of service links
    urlpatterns += patterns('',
        url(r'^login/$', login, {}, 'auth_login',),
        url(r'^terms-of-service/', include('tos.urls')),
    )

Option 2: Middleware Check
```


## Overview

Django REST framework is a powerful and flexible toolkit for building Web APIs.

Some reasons you might want to use REST framework:

* The [Web browsable API][sandbox] is a huge usability win for your developers.
* [Authentication policies][authentication] including optional packages for [OAuth1a][oauth1-section] and [OAuth2][oauth2-section].
* [Serialization][serializers] that supports both [ORM][modelserializer-section] and [non-ORM][serializer-section] data sources.
* Customizable all the way down - just use [regular function-based views][functionview-section] if you don't need the [more][generic-views] [powerful][viewsets] [features][routers].
* [Extensive documentation][docs], and [great community support][group].

There is a live example API for testing purposes, [available here][sandbox].


## Features

- Make [XMLHttpRequests](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) from the browser
- Make [http](http://nodejs.org/api/http.html) requests from node.js
- Supports the [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) API
- Intercept request and response
- Transform request and response data
- Cancel requests
- Automatic transforms for JSON data
- Client side support for protecting against [XSRF](http://en.wikipedia.org/wiki/Cross-site_request_forgery)

### All algorithms implemented in Python (for education)

These are for demonstration purposes only. There are many implementations of sorts in the Python standard library that are much better for performance reasons.

## Sort Algorithms


### Bubble
![alt text][class-image]

From [Wikipedia][bubble-wiki]: Bubble sort, sometimes referred to as sinking sort, is a simple sorting algorithm that repeatedly steps through the list to be sorted, compares each pair of adjacent items and swaps them if they are in the wrong order. The pass through the list is repeated until no swaps are needed, which indicates that the list is sorted.

__Properties__
* Worst case performance	O(n^2)
* Best case performance	O(n)
* Average case performance	O(n^2)

###### View the algorithm in [action][bubble-toptal]



### Insertion
![alt text][insertion-image]

From [Wikipedia][insertion-wiki]: Insertion sort is a simple sorting algorithm that builds the final sorted array (or list) one item at a time. It is much less efficient on large lists than more advanced algorithms such as quicksort, heapsort, or merge sort.

__Properties__
* Worst case performance	O(n^2)
* Best case performance	O(n)
* Average case performance	O(n^2)

###### View the algorithm in [action][insertion-toptal]


### Merge
![alt text][merge-image]

From [Wikipedia][merge-wiki]: In computer science, merge sort (also commonly spelled mergesort) is an efficient, general-purpose, comparison-based sorting algorithm. Most implementations produce a stable sort, which means that the implementation preserves the input order of equal elements in the sorted output. Mergesort is a divide and conquer algorithm that was invented by John von Neumann in 1945.

__Properties__
* Worst case performance	O(n log n)
* Best case performance	O(n)
* Average case performance	O(n)


###### View the algorithm in [action][merge-toptal]

### Quick
![alt text][quick-image]

From [Wikipedia][quick-wiki]: Quicksort (sometimes called partition-exchange sort) is an efficient sorting algorithm, serving as a systematic method for placing the elements of an array in order.

__Properties__
* Worst case performance	O(n^2)
* Best case performance	O(n log n) or O(n) with three-way partition
* Average case performance	O(n log n)

###### View the algorithm in [action][quick-toptal]

### Selection
![alt text][selection-image]

From [Wikipedia][selection-wiki]: The algorithm divides the input list into two parts: the sublist of items already sorted, which is built up from left to right at the front (left) of the list, and the sublist of items remaining to be sorted that occupy the rest of the list. Initially, the sorted sublist is empty and the unsorted sublist is the entire input list. The algorithm proceeds by finding the smallest (or largest, depending on sorting order) element in the unsorted sublist, exchanging (swapping) it with the leftmost unsorted element (putting it in sorted order), and moving the sublist boundaries one element to the right.

__Properties__
* Worst case performance	O(n^2)
* Best case performance	O(n^2)
* Average case performance	O(n^2)

###### View the algorithm in [action][selection-toptal]

### Shell
![alt text][shell-image]

From [Wikipedia][shell-wiki]:  Shellsort is a generalization of insertion sort that allows the exchange of items that are far apart.  The idea is to arrange the list of elements so that, starting anywhere, considering every nth element gives a sorted list.  Such a list is said to be h-sorted.  Equivalently, it can be thought of as h interleaved lists, each individually sorted.

__Properties__
* Worst case performance O(nlog2 2n)
* Best case performance O(n log n)
* Average case performance depends on gap sequence

###### View the algorithm in [action][shell-toptal]

### Time-Compexity Graphs

Comparing the complexity of sorting algorithms (Bubble Sort, Insertion Sort, Selection Sort)

[Complexity Graphs](https://github.com/prateekiiest/Python/blob/master/sorts/sortinggraphs.png)

----------------------------------------------------------------------------------

## Search Algorithms

### Linear
![alt text][linear-image]

From [Wikipedia][linear-wiki]: linear search or sequential search is a method for finding a target value within a list. It sequentially checks each element of the list for the target value until a match is found or until all the elements have been searched.
  Linear search runs in at worst linear time and makes at most n comparisons, where n is the length of the list.

__Properties__
* Worst case performance	O(n)
* Best case performance	O(1)
* Average case performance	O(n)
* Worst case space complexity	O(1) iterative

### Binary
![alt text][binary-image]

From [Wikipedia][binary-wiki]: Binary search, also known as half-interval search or logarithmic search, is a search algorithm that finds the position of a target value within a sorted array. It compares the target value to the middle element of the array; if they are unequal, the half in which the target cannot lie is eliminated and the search continues on the remaining half until it is successful.

__Properties__
* Worst case performance	O(log n)
* Best case performance	O(1)
* Average case performance	O(log n)
* Worst case space complexity	O(1) 

----------------------------------------------------------------------------------------------------------------------

## Ciphers

### Caesar
![alt text][caesar]<br>
In cryptography, a **Caesar cipher**, also known as Caesar's cipher, the shift cipher, Caesar's code or Caesar shift, is one of the simplest and most widely known encryption techniques.<br>
It is **a type of substitution cipher** in which each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet. For example, with a left shift of 3, D would be replaced by A, E would become B, and so on. <br>
The method is named after **Julius Caesar**, who used it in his private correspondence.<br>
The encryption step performed by a Caesar cipher is often incorporated as part of more complex schemes, such as the Vigenère cipher, and still has modern application in the ROT13 system. As with all single-alphabet substitution ciphers, the Caesar cipher is easily broken and in modern practice offers essentially no communication security.
###### Source: [Wikipedia](https://en.wikipedia.org/wiki/Caesar_cipher)

### Vigenère
The **Vigenère cipher** is a method of encrypting alphabetic text by using a series of **interwoven Caesar ciphers** based on the letters of a keyword. It is **a form of polyalphabetic substitution**.<br>
The Vigenère cipher has been reinvented many times. The method was originally described by Giovan Battista Bellaso in his 1553 book La cifra del. Sig. Giovan Battista Bellaso; however, the scheme was later misattributed to Blaise de Vigenère in the 19th century, and is now widely known as the "Vigenère cipher".<br>
Though the cipher is easy to understand and implement, for three centuries it resisted all attempts to break it; this earned it the description **le chiffre indéchiffrable**(French for 'the indecipherable cipher'). 
Many people have tried to implement encryption schemes that are essentially Vigenère ciphers. Friedrich Kasiski was the first to publish a general method of deciphering a Vigenère cipher in 1863.
###### Source: [Wikipedia](https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher)

### Transposition
In cryptography, a **transposition cipher** is a method of encryption by which the positions held by units of plaintext (which are commonly characters or groups of characters) are shifted according to a regular system, so that the ciphertext constitutes a permutation of the plaintext. That is, the order of the units is changed (the plaintext is reordered).<br> 
Mathematically a bijective function is used on the characters' positions to encrypt and an inverse function to decrypt.
###### Source: [Wikipedia](https://en.wikipedia.org/wiki/Transposition_cipher)




[bubble-toptal]: https://github.com/myone2010/doc/blob/master/%EA%B7%B8%EB%A6%BC1.png?raw=true
[bubble-wiki]: https://en.wikipedia.org/wiki/Bubble_sort
[bubble-image]: https://github.com/myone2010/doc/blob/master/%EA%B7%B8%EB%A6%BC1.png?raw=true

[insertion-toptal]: https://www.toptal.com/developers/sorting-algorithms/insertion-sort
[insertion-wiki]: https://en.wikipedia.org/wiki/Insertion_sort
[insertion-image]: https://upload.wikimedia.org/wikipedia/commons/7/7e/Insertionsort-edited.png "Insertion Sort"

[quick-toptal]: https://www.toptal.com/developers/sorting-algorithms/quick-sort
[quick-wiki]: https://en.wikipedia.org/wiki/Quicksort
[quick-image]: https://upload.wikimedia.org/wikipedia/commons/6/6a/Sorting_quicksort_anim.gif "Quick Sort"

[merge-toptal]: https://www.toptal.com/developers/sorting-algorithms/merge-sort
[merge-wiki]: https://en.wikipedia.org/wiki/Merge_sort
[merge-image]: https://upload.wikimedia.org/wikipedia/commons/c/cc/Merge-sort-example-300px.gif "Merge Sort"

[selection-toptal]: https://www.toptal.com/developers/sorting-algorithms/selection-sort
[selection-wiki]: https://en.wikipedia.org/wiki/Selection_sort
[selection-image]: https://upload.wikimedia.org/wikipedia/commons/thumb/b/b0/Selection_sort_animation.gif/250px-Selection_sort_animation.gif "Selection Sort Sort"

[shell-toptal]: https://www.toptal.com/developers/sorting-algorithms/shell-sort
[shell-wiki]: https://en.wikipedia.org/wiki/Shellsort
[shell-image]: https://upload.wikimedia.org/wikipedia/commons/d/d8/Sorting_shellsort_anim.gif "Shell Sort"

[linear-wiki]: https://en.wikipedia.org/wiki/Linear_search
[linear-image]: http://www.tutorialspoint.com/data_structures_algorithms/images/linear_search.gif

[binary-wiki]: https://en.wikipedia.org/wiki/Binary_search_algorithm
[binary-image]: https://upload.wikimedia.org/wikipedia/commons/f/f7/Binary_search_into_array.png


[caesar]: https://upload.wikimedia.org/wikipedia/commons/4/4a/Caesar_cipher_left_shift_of_3.svg

[build-status-image]: https://secure.travis-ci.org/encode/django-rest-framework.svg?branch=master
[travis]: https://travis-ci.org/encode/django-rest-framework?branch=master
[coverage-status-image]: https://img.shields.io/codecov/c/github/encode/django-rest-framework/master.svg
[codecov]: https://codecov.io/github/encode/django-rest-framework?branch=master
[pypi-version]: https://img.shields.io/pypi/v/djangorestframework.svg
[pypi]: https://pypi.python.org/pypi/djangorestframework
[twitter]: https://twitter.com/_tomchristie
[group]: https://groups.google.com/forum/?fromgroups#!forum/django-rest-framework
[sandbox]: https://restframework.herokuapp.com/

[funding]: https://fund.django-rest-framework.org/topics/funding/
[sponsors]: https://fund.django-rest-framework.org/topics/funding/#our-sponsors

[rover-img]: https://raw.githubusercontent.com/encode/django-rest-framework/master/docs/img/premium/rover-readme.png
[sentry-img]: https://raw.githubusercontent.com/encode/django-rest-framework/master/docs/img/premium/sentry-readme.png
[stream-img]: https://raw.githubusercontent.com/encode/django-rest-framework/master/docs/img/premium/stream-readme.png
[machinalis-img]: https://raw.githubusercontent.com/encode/django-rest-framework/master/docs/img/premium/machinalis-readme.png
[rollbar-img]: https://raw.githubusercontent.com/encode/django-rest-framework/master/docs/img/premium/rollbar-readme.png

[rover-url]: http://jobs.rover.com/
[sentry-url]: https://getsentry.com/welcome/
[stream-url]: https://getstream.io/try-the-api/?utm_source=drf&utm_medium=banner&utm_campaign=drf
[machinalis-url]: https://hello.machinalis.co.uk/
[rollbar-url]: https://rollbar.com/

[oauth1-section]: http://www.django-rest-framework.org/api-guide/authentication/#django-rest-framework-oauth
[oauth2-section]: http://www.django-rest-framework.org/api-guide/authentication/#django-oauth-toolkit
[serializer-section]: http://www.django-rest-framework.org/api-guide/serializers/#serializers
[modelserializer-section]: http://www.django-rest-framework.org/api-guide/serializers/#modelserializer
[functionview-section]: http://www.django-rest-framework.org/api-guide/views/#function-based-views
[generic-views]: http://www.django-rest-framework.org/api-guide/generic-views/
[viewsets]: http://www.django-rest-framework.org/api-guide/viewsets/
[routers]: http://www.django-rest-framework.org/api-guide/routers/
[serializers]: http://www.django-rest-framework.org/api-guide/serializers/
[authentication]: http://www.django-rest-framework.org/api-guide/authentication/
[image]: http://www.django-rest-framework.org/img/quickstart.png

[docs]: http://www.django-rest-framework.org/
[security-mail]: mailto:rest-framework-security@googlegroups.com
