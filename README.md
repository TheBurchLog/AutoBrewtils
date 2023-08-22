# AutoBrewtils
A streamlined tool to convert class objects into Beer Garden plugins. 

## Example



```
class ExampleClass:

    built = False

    __version__ = "1.0.1"

    def __init__(self):
        self.built = True

    def testFunction(self, one:str, two:int, three = None):

        print(one)
        print(two)
        print(three)

        return two

auto = AutoBrewObject()
auto.updateClientClass(ExampleClass, name="ExampleClass")

example = ExampleClass()
plugin = Plugin(
        name=example._bg_name,
        version=example._bg_version,
        bg_host='1.1.1.1',
        bg_port=80,
        ssl_enabled=False,
    )



plugin.client = example
plugin.run()


```
