# ModelMapper
Entendendo Sobre a biblioteca ModelMapper

## O que é

`ModelMapper` é uma biblioteca que ajuda a fazer o mapeamento de objetos em Java. Muito utilizado quando você tem uma `class` com vários atributos, porém você quer mostrar apenas alguns deles.

## Configuração

Se você utiliza o `Maven` basta adicionar essa dependência na sua aplicação para poder utilizar o `modelmapper`:

```
<dependency>
  <groupId>org.modelmapper</groupId>
  <artifactId>modelmapper</artifactId>
  <version>3.0.0</version>
</dependency>
```
Caso utilize outra ferramenta de gestão de dependências recomendo acessar esse site: 
- https://mvnrepository.com/artifact/org.modelmapper/modelmapper/


## Alguns trechos de código importante do `modelmapper`
~~~Java
//Order order = new Order("PC", 2000);

ModelMapper modelMapper = new ModelMapper();
OrderDTO orderDTO = modelMapper.map(order, OrderDTO.class);
~~~

Com a `class` de **configuration** pode se usar a injeção de independência do `ModelMapper`

~~~Java
@Configuration
public class TesteModelConfiguration {

    @Bean
    public ModelMapper getModel(){
        return new ModelMapper();
    }
}
~~~~

~~~Java
@Autowired
    private ModelMapper modelMapper;
~~~
