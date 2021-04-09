# aiodog.py
An async wrapper for https://pypi.org/projects/dog.py which covers all of https://thedogapi.com/

To install, type this command:
```
pip install -U aiodog.py
```

Here's a simple example:
```py
import asyncio

from aiodog import Client

TOKEN = 'my_token_here'

async def main():
    client = Client(TOKEN)

    images = await client.get_images()
    image = images[0]

    print("The dog url is", image.url)

    await client.close()

asyncio.run(main())
```

You can also use `async with`.

```py
async def main():
    async with Client(TOKEN) as client
        images = await client.get_images()
        image = images[0]

        print("The dog url is", image.url)
```