# debounce
防抖函数

使用
const {debounce} = require('./debounce.js');
定义一个全局的空变量
var dTips=null
例如你的搜索函数
 function searchTips(value) {
    var that = this;
    location.getInputtips(value).then(res => {
      if (res.code == 200) {
        that.setData({
          cityList: res.data.tips.filter(e => {
            return e.location.length != 0
          })
        });
        console.log(that.data.cityList);
      }
    })
  }
  
  直接点击执行就行
  debounce(this.searchTips, 200)
