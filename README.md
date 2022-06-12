<br>
<h1 align="center">🐶 Unreal Engine Cel Shading 🐶</h1>
<p align="center">This is a version of Unreal Engine 5.0 with a custom cel and outline shader built into the rendering engine. Any object can be easily cel shaded using the Cel Shading shading model. The cel shading is currently only in the <a href="https://github.com/Treixatek/UnrealEngine/tree/5.0">5.0 branch</a> but will probably be added to future versions. The principles should still remain the same for a while if you want to implement this yourself by reading my article. If not, follow <a href="https://youtu.be/DcEBKnJMxng">this video</a> to clone and install the UE5 source, except clone this repo instead of the Epic Games repo. <strong>As this is a fork of Unreal Engine, the repo is private and you need to join the epic games organization to gain access, follow these steps <a href="https://www.unrealengine.com/en-US/ue-on-github?sessionInvalidated=true">here</a></strong></p>
<div align="center">
	<a href="https://github.com/Treixatek/UnrealEngine"><strong>Go to UE5 fork »</strong></a>
</div>
</br>

<h2 align="center">Media</h2>

![cel shade](https://user-images.githubusercontent.com/65512990/173237738-93ca6cae-b874-444b-9162-5b5158b7eb25.png)
![cel lights](https://user-images.githubusercontent.com/65512990/173237743-59cbe89e-c171-44e8-984c-919d64bceb67.png)
![Screenshot 2022-06-04 160705](https://user-images.githubusercontent.com/65512990/173237750-a7f04f96-f40a-40a0-8fbe-baa61931a82d.png)
_yes! colored lights are supported!_

<h2 align="center">How to Use</h2>

1. In the panel of the material graph, set the blend mode to **opaque** or **masked** (masked should work, create an issue if not, I have not explicitly supported it)
2. Under that, switch the shading model to to **Cel Shading**
3. You will see the custom data pins 0 & 1 open up, as Cel Bands and Outline Thickness, **Cel Bands takes a fraction**. 
	```sh
   		1
   ____________________
	# of bands you want
   ```
4. Set the Outline Thickness pin to a value between 0 and 1
5. Set the Outline Sensitivity pin, this decides what is an edge or not, between 0 and 1 as well, around .5 is a good value

<h2 align="center">Slight problem</h2>
<p align="center">I have been unable to get cel shading of the shadows to work, for some unknown reason the method I used to split the shadowed regions into bands no longer works after the changes made to the rendering engine in UE5. Here are some resources which I think might hold the solution. I was studying these before I eventually concluded that for my project, banded shadows were unnecessary as I would likely use a single band anyway</p>

- https://forums.unrealengine.com/t/ue5-anime-toon-shading-model/544226
- https://github.com/envieous/UnrealEngine-SelShader/blob/9a61a8cdc5fd20261bb980625b4f13f5d718ae3f/Engine/Shaders/Private/DeferredLightPixelShaders.usf#L318
- https://medium.com/@lordned/ue4-rendering-part-6-adding-a-new-shading-model-e2972b40d72d (Changing Attenuation Calculations section)

<h3 align="center">Contact</h3>

At this point I have a very good understanding of how the code involved in rendering works so if you need any help with either following the article or investigating cel shading of the shadows but you are new to the source code, feel free to reach out with any questions either by hello@deveelo.com or [discord](https://discord.com/invite/bEqqgTPVHD)!! 😀
