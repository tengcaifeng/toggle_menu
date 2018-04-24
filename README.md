# toggle_menu
# 1、同时打开同时关闭。
# 2、可以同时关闭，只能打开一个。
# 3、必须打开一个

### 以下是js代码，代码本生我已经写了很多注释

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<link rel="stylesheet" href="https://cdn.bootcss.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">
<script src=http://apps.bdimg.com/libs/jquery/2.1.4/jquery.min.js></script>

<style>
    .detail{
        background-color: #f2f2f2;
    }

    .detailbox{
        height: 100px;
        background-color: #f4f4f4!important;
        border-top:1px solid #5e49da;
    }

    .hide{
     display: none;
    }

    .xq{
        cursor: pointer;
    }

</style>
<body>
<div class="bs-example" data-example-id="bordered-table">
    <table class="table table-bordered">
        <thead>
        <tr>
            <th>#</th>
            <th>First Name</th>
            <th>Last Name</th>
            <th>Username</th>
        </tr>
        </thead>
        <tbody>



        <tr>
            <th >1</th>
            <td>Mark</td>
            <td>Otto</td>
            <td class="xq" id="x1" onclick="showdetial('x1');">详情</td>
        </tr>
        <tr   class="hide xq_content detailbox">
         <td colspan="4">
             这里是你的详情内容
         </td>
        </tr>



        <tr>
            <th >2</th>
            <td>Jacob</td>
            <td>Thornton</td>
            <td class="xq" id="x2" onclick="showdetial('x2');">详情</td>
        </tr>
        <tr  class="hide xq_content detailbox">
            <td colspan="4">
                这里是你的详情内容
            </td>
        </tr>



        <tr>
            <th >3</th>
            <td>Larry</td>
            <td>the Bird</td>
            <td class="xq" id="x3" onclick="showdetial('x3');">详情</td>
        </tr>
        <tr class="hide xq_content detailbox">
            <td colspan="4">
                这里是你的详情内容
            </td>
        </tr>



        </tbody>
    </table>
</div>
</body>
</html>

<script>
/*
说明
.hide display:none
.detail background-color:#f2f2f2;
先让所有的xq_content  添加.hide隐藏起来
分别让点击元素背景变色，和显示详情的框框
*/


/*可以同时关闭，只能打开一个*/
/*思路：
* 1、先让点击元素的所有兄弟都一起背景色都没有detail属性，
* 2、让当前点击元素toggle背景色detial属性
* 3、通过背景色判断xq_content是否显示
* 4、现将所有详情框框添加hide
* 5、判断点击元素是否有detail,有就将hide移除，否则添加
* */
//    function showdetial(id) {
//
//        $("#"+id+"").parent().siblings().removeClass('detail');
//        $("#"+id+"").parent().toggleClass('detail');
//
//        $('.xq_content').addClass('hide');
//        if($("#"+id+"").parent().hasClass('detail')){
//            $("#"+id+"").parent().next().removeClass('hide');
//        }else {
//            $("#"+id+"").parent().next().addClass('hide');
//        }
//    }


/*可以同时打开，可以同时关闭*/
/*
* 思路：
* 1、让点击元素toggleClass() detail 和 hide就是本来没有detail就有，本来有hide变成没有hide
*
* */
  function showdetial(id) {

   // $("#"+id+"").parent().siblings().removeClass('detail');
   $("#"+id+"").parent().toggleClass('detail');

   //$(".xq_content").hide();
   $("#"+id+"").parent().next().toggleClass('hide');

}



/*必须打开一个*/
/*思路：
1、先让点击元素的所有兄弟都一起背景色没有detail属性，
2、让当前点击元素添加背景色detial属性
3、让所有显示详情的元素都隐藏起来添加hide
4、让当前点击的元素的详情toggelClass hide属性，也就是有hide的就成了没有hide也就显示出来了
*/

// function showdetial(id) {
//
//      $("#"+id+"").parent().siblings().removeClass('detail');
//      $("#"+id+"").parent().addClass('detail');
//
//      $('.xq_content').addClass('hide');
//      $("#"+id+"").parent().next().toggleClass('hide');
//
// }

</script>
```
