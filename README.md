# Avatar | アバター

Is a webapp that uses the multiple end points provided by [Kiko Beats](https://github.com/Kikobeats) to fetch and display a given user's profile picture .

This was made just to put a UI on the already existing project.
Since i've used these links quit a lot lately , i wanted to make it more accessible
for me or anyone else who's interested .

You can always refer to the original project here :

[Unavatar](https://github.com/Kikobeats/unavatar)

## How does it work :

![Screenshot](/src/assets/avatar.gif)

## Different platforms :

| Facebook![ Screenshot ](/src/assets/fb.png) | Instagram![ Screenshot ](/src/assets/ig.png) | Twitter![ Screenshot ](/src/assets/tw.png) | Error![ Screenshot ](/src/assets/error.png) |
| ------------------------------------------- | -------------------------------------------- | ------------------------------------------ | ------------------------------------------- |


## User not found :

```
In case of a not valid username on any platform , the image displayed is :
```

<div align="center">
<img src="/src/assets/error.png" >

</div>

```
This can be changed ! just refer to the documentation 📚 here :
```

👉 [Unavatar](https://unavatar.now.sh/) 👈

## False negative for IG ids :

```
I noticed that sometimes , the username is correct but still returns no picture .
The fix for instagram is easy !
On the IG app , open the profile you want ,
Click on the three dots on the top right of the screen
Then click on ' Copy Profile URL '
Past it in the search field and voila!

The id looks something like : USERNAME?igshid=XXXXXXXXXXXXX
```

## False negative for Facebook :

```
this one is kind of a hit or miss .
```

## Install

-**Project setup**

```
pnpm install
```

-**Compiles and hot-reloads for development**

```
pnpm run serve
```

-**Compiles and minifies for production**

```
pnpm run build
```

## Support

```
Any help improving this spa , is welcomed :heart:
```

## Contact

```
you can contact me at ZTF666@protonmail.ch or via my portfolio
```

- **:biohazard:** [Portfolio](https://ztfportfolio.web.app/) **:biohazard:**

## License

**Avatar | アバター** released under the [MIT](LICENSE) License.

```
Made with 💘 by a 👨‍💻 on a 💻 | 2020 | ZTF666
```
