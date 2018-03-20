一个10年的老项目，使用spring+struts+hibernate框架。  

问题：   
    使用注解 @component , 并在属性上使用注解 @value，但是一直没有取到值。  

解决：   
    不使用 @component， 更换为 @service, 问题解决。 猜测是与 spring 配置文件的加载顺序有关，未找到问题根源。  

TIPS：   
    变量static 使用@value时， @value应标注在 set方法上，set方法不要有 static!!

    public static String URL;
    
    @Value("${webarticleurl.url}")
    public void setURL(String uRL) {
        URL = uRL;
    }
