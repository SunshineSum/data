##用jquery发送ajax——get请求的第一种方式（复杂方式）
    /*$.ajax('http://localhost:3000/demo1',{
      method:'GET',
      data:{
        name:'kobe',
        age:12
      },
      success:function (data) {
        console.log(data)
      },
      error:function (err) {
        console.log(err)
      }
##用jquery发送ajax——post请求的第一种方式（复杂方式）
	$.ajax('http://localhost:3000/demo2',{
      method:'POST',
      data:{
        name:'kobe',
        age:12
      },
      success:function (data) {
        console.log(data)
      },
      error:function (err) {
        console.log(err)
      }
	})
##用jquery发送ajax——get请求的第二种方式（简单方式）
	$.get('http://localhost:3000/demo1',{name:'kobe',age:12},(data)=>{
      console.log(data)
    })
   
##用jquery发送ajax——post请求的第二种方式（简单方式）
    $.post('http://localhost:3000/demo2',{name:'kobe',age:12},(data)=>{
      console.log(data)
    })