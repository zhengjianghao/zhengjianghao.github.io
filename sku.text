# zhengjianghao.github.io
后端有skulist [['红，大，高']，['白，大，高']] ，选中的sku (红，大，高)
设置一个 canChooseValue 包含所有可以选择的sku值  （红，白，大，小，高）
1.click 某个sku时  判断该值是否已经存在 sku中，存在（取消），不存在选中
2.用目前的sku 和 skuList 中的每一项对比  看skuList中的每一项是否包含 当前选中的sku （红）// isContained
3.true 把该sku的值放到canChooseValue中， canChooseValue去重





let _checkList = []
let _skuNamesList = []
for (let _list of this.skuList) {
  _skuNamesList.push(_list.valueList) // _skuNamesList sku值的list [['红，大，高']，['白，大，高']]
}
for (let _skuNam of _skuNamesList) {
  if (this.isContained(_skuNam, _nams)) { // _nams 是当前选中的sku值
    _checkList = [..._checkList, ...this.array_difference(_skuNam, _nams), ..._nams]
  }
}
this.allValue = this.array_remove_repeat(_checkList)

// 是否包含
isContained (a, b) {
  let _inc = []
  for (let i of b) {
    if (a.includes(i)) {
      _inc.push(i)
    }
  }
  return _inc.length === b.length
  // if (!(a instanceof Array) || !(b instanceof Array)) return false
  // if (a.length < b.length) return false
  // var aStr = a.toString()
  // for (var i = 0, len = b.length; i < len; i++) {
  //   if (aStr.indexOf(b[i]) === -1) return false
  // }
  // return true
},


array_difference (a, b) { // 差集 a - b
// clone = a
  var clone = a.slice(0)
  for (var i = 0; i < b.length; i++) {
    var temp = b[i]
    for (var j = 0; j < clone.length; j++) {
      if (temp === clone[j]) {
        // remove clone[j]
        clone.splice(j, 1)
      }
    }
  }
  return this.array_remove_repeat(clone)
},
array_remove_repeat (a) { // 去重
  var r = []
  for (var i = 0; i < a.length; i++) {
    var flag = true
    var temp = a[i]
    for (var j = 0; j < r.length; j++) {
      if (temp === r[j]) {
        flag = false
        break
      }
    }
    if (flag) {
      r.push(temp)
    }
  }
  return r
},
