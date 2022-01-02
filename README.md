
okteto 注册地址： https://cloud.okteto.com

详情见： https://github.com/yunbaitech666/okvtwo

反向代理
代码：
const SingleDay = 'appname.herokuapp.com' 
const DoubleDay = 'appname.herokuapp.com' 
addEventListener( 
    "fetch",event => { 
 
        let nd = new Date(); 
        if (nd.getDate()%2) { 
            host = SingleDay 
        } else { 
            host = DoubleDay 
        } 
 
        let url=new URL(event.request.url); 
        url.hostname=host; 
        let request=new Request(url,event.request); 
        event.respondWith( 
            fetch(request) 
        ) 
    } 
)
