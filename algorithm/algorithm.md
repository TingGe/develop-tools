# 8大排序算法 JS 示例

## 代码

### 插入排序

直接插入

```javascript
function insert(arr, i, v) {
  arr.splice(i, 0, v);
}

function insertSort(arr, comp) {
  var result = new Array();
  for (; arr.length > 0;) {
    var inserted = false;
    for (var j = 0; j < result.length; j++) {
      if (comp(result[j], arr[0])) {
        insert(result, j, arr[0]);
        inserted = true;
        break;
      }
    }
    if (!inserted) {
      insert(result, result.length, arr[0]);
    }
    arr.splice(0, 1);
  }
  return result;
}

var input = new Array(5, 1, 4, 2, 3);
var ret = insertSort(input, function(a, b) {
  return a > b;
});
console.log(ret);
var input = new Array(5, 1, 4, 2, 3);
ret = insertSort(input, function(a, b) {
  return a < b;
});
console.log(ret);
```

希尔排序

```javascript
function shellSort(a, comp) {
  for (var h = a.length; h = parseInt(h / 2);) {
    for (var i = h; i < a.length; i++) {
      var k = a[i];
      for (var j = i; j >= h && comp(k, a[j - h]); j -= h) a[j] = a[j - h];
      a[j] = k;
    }
  }
  return a;
}

var arr = new Array(7, 9, 2, 5, 4, 1, 3);
var r = shellSort(arr, function(a, b) {
  return a > b;
});
console.log(r);
```

### 选择排序

直接选择

```javascript
function exch(a, i, j) {
  var tmp = a[i];
  a[i] = a[j];
  a[j] = tmp;
}

function selectionSort(arr, comp) {
  for (var i = 0; i < arr.length; i++) {
    for (var j = i; j < arr.length; j++) {
      if (comp(arr[i], arr[j])) {
        exch(arr, i, j);
      }
    }
  }
}

var input = new Array(5, 1, 4, 2, 3);
selectionSort(input, function(a, b) {
  return a > b;
});
console.log(input);

input = new Array(5, 1, 4, 2, 3);
selectionSort(input, function(a, b) {
  return a < b;
});
console.log(input);
```

堆排序

```javascript
var ret = new Array();
function heapS(arr, comp) {
  if (arr.length == 0) {
    return;
  }
  var i = arr.length / 2 | 0;
  for (; i >= 0; i--) {
    if (comp(arr[i], arr[i * 2])) {
      exch(arr, i, i * 2);
    }
    if (comp(arr[i], arr[i * 2 + 1])) {
      exch(arr, i, i * 2 + 1);
    }
  }
  ret.push(arr[0]);
  arr.splice(0, 1);
  heapS(arr, comp);
}

heapS(new Array(16, 22, 91, 0, 51, 44, 23), function(a, b) {
  return a > b;
});
console.log(ret);
```

### 交换排序

冒泡

```javascript
function exch(a, i, j) {
  var tmp = a[i];
  a[i] = a[j];
  a[j] = tmp;
}

function bubbleSort(arr, comp) {
  for (var i = 0; i < arr.length; i++) {
    for (var j = 0; j < arr.length - i - 1; j++) {
      if (comp(arr[j], arr[j + 1])) {
        exch(arr, j, j + 1);
      }
    }
  }
}

var input = new Array(5, 1, 4, 2, 3);
bubbleSort(input, function(a, b) {
  return a > b;
});
console.log(input);

input = new Array(5, 1, 4, 2, 3);
bubbleSort(input, function(a, b) {
  return a < b;
});
console.log(input);
```

快速排序

```javascript
function quickS(arr, lo, hi, comp) {
  if (lo >= hi) {
    return;
  }
  var stub = arr[lo];
  var i = lo + 1;
  var j = hi;
  for (; i < j;) {
    for (; i < j && !comp(stub, arr[j]); j--);
    for (; i < j && comp(stub, arr[i]); i++);
    if (i >= j) {
      break;
    }
    var t = arr[i];
    arr[i] = arr[j];
    arr[j] = t;
    j--;
    i++;
  }
  if (comp(arr[lo], arr[i])) {
    var t = arr[lo];
    arr[lo] = arr[i];
    arr[i] = t;
  }
  quickS(arr, lo, i - 1, comp);
  quickS(arr, i, hi, comp);
}

var input = new Array(22, 3, 10, 66, 15, 11, 2, 4, 31, 9);
quickS(input, 0, input.length - 1, function(a, b) {
  return a > b;
});
console.log(input);
```

### 归并排序

```javascript
function mergeS(arr, comp) {
  if (arr.length == 1) {
    return arr;
  }
  var mid = arr.length / 2 | 0;
  var leftArr = new Array();
  var rightArr = new Array();
  for (var i = 0; i < mid; i++) {
    leftArr.push(arr[i]);
  }
  for (var j = mid; j < arr.length; j++) {
    rightArr.push(arr[j]);
  }
  console.log("before : " + leftArr + " | " + rightArr);
  var leftRet = mergeS(leftArr, comp);
  var rightRet = mergeS(rightArr, comp);
  var r = merge(leftRet, rightRet, comp);
  return r;
}

function merge(leftArr, rightArr, comp) {
  var ret = new Array();
  var i = j = 0;
  for (; i < leftArr.length && j < rightArr.length;) {
    if (comp(leftArr[i], rightArr[j])) {
      ret.push(leftArr[i]);
      i++
    } else {
      ret.push(rightArr[j]);
      j++
    }
  }
  for (; i < leftArr.length;) {
    ret.push(leftArr[i]);
    i++;
  }
  for (; j < rightArr.length;) {
    ret.push(rightArr[j]);
    j++;
  }
  return ret;
}

var r = mergeS(new Array(0, 6, 5, 1, 2, 4, 3, 9), function(a, b) {
  return a > b;
});
console.log(r);
```

### 基数排序

```javascript
// Todo
```

## 参考

- [8大排序算法总结 JS 实现](http://m.2cto.com/kf/201412/360965.html)