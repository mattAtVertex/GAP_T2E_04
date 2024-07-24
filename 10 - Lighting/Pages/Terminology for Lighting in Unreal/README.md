# Terminology for Lighting in Unreal

<p>Let's have&nbsp; a look at some terminology&nbsp;</p>
<ul>
<li>Light Actor</li>
<li>Static Lighting</li>
<li>Dynamic Lighting</li>
<li>Shadows</li>
<li>Indirect or Bounce Lighting (Lightmass)</li>
</ul>
<p>&nbsp;</p>
<hr style="clear: both;">
<h3>Light Actor</h3>
<p><img style="float: right; padding: 0 0 20px 20px;" src="https://vertexschool.instructure.com/courses/18/files/968/preview?verifier=GrI2aBffMDswKNqrTL0iWo9KHnTKbU2rVXg7elQW" alt="LightActor.jpg" width="600" height="438" data-api-endpoint="https://vertexschool.instructure.com/api/v1/courses/18/files/968" data-api-returntype="File"></p>
<p>The light actor is the actual component in the scene.&nbsp; In Unreal Engine, these would be the following:</p>
<ul>
<li>Directional Light</li>
<li>Spot Light</li>
<li>Point Light</li>
<li>Sky Light</li>
<li>Rect Light</li>
</ul>
<p>&nbsp;</p>
<hr style="clear: both;">
<h2>Static Lighting</h2>
<p><img style="float: right; padding: 0 0 20px 20px;" src="https://vertexschool.instructure.com/courses/18/files/966/preview?verifier=jSwUnM6JXCHgAb6xgnbXzBa6YIT07pnWTbPJx4tk" alt="StaticShadows.jpg" width="600" height="497" data-api-endpoint="https://vertexschool.instructure.com/api/v1/courses/18/files/966" data-api-returntype="File"></p>
<p>Static lighting is a type of lighting for objects that don't move. For this type of lighting, the lighting and shadows are baked down to a lightmap texture that is loaded into memory. The lighting is calculated only once during the build lighting procedure, so it doesn't cost any real time performance.</p>
<p>The baked lightmaps are then rendered on top of meshes in the scene to create static shadows. This static lighting won't cast any dynamic shadows at all. Any light actor set to static lighting cannot be moved or altered during gameplay.</p>
<p>For a static light, once the lighting is baked, that light no longer affects the scene. The actor stays in the scene so that you can see it in the editor and so it can be baked again if you build lighting again, but you could theoretically delete the light from the scene and the baked lighting information would still remain.</p>
<p>&nbsp;</p>
<hr style="clear: both;">
<h2>Dynamic Lighting</h2>
<p><img style="float: right; padding: 0 0 20px 20px;" src="https://vertexschool.instructure.com/courses/18/files/967/preview?verifier=AuKZYTbJgnRLLUxmfRCS2QniGxjD57c5jYNAIBly" alt="Dynamic Lighting.jpg" width="600" height="509" data-api-endpoint="https://vertexschool.instructure.com/api/v1/courses/18/files/967" data-api-returntype="File"></p>
<p>This refers to lighting on objects that move during gameplay. Lighting that is dynamic has to be calculated every frame at runtime so in terms of performance optimization, it is considered expensive. This also means that in real time rendering during gameplay, it can actually be lower quality than static lighting. Many aspects of a dynamic light can be changed during gameplay.&nbsp; It also does not get calculated during the building of lights. Since it does not bake a lightmap, meshes do not need to have correct lightmap UVs for a dynamic light to correctly light the mesh.</p>
<p>Examples of properties that can be changed during gameplay:</p>
<ul>
<li>Color</li>
<li>Intensity</li>
<li>Location and rotation</li>
</ul>
<p>&nbsp;</p>
<hr style="clear: both;">
<h2>Shadows</h2>
<p><img style="float: right; padding: 0 0 20px 20px;" src="https://vertexschool.instructure.com/courses/18/files/965/preview?verifier=TTpG081dQsrhwlcvMdjRI2zLoxugArHxPyQuGCkV" alt="Shadows.jpg" width="600" height="497" data-api-endpoint="https://vertexschool.instructure.com/api/v1/courses/18/files/965" data-api-returntype="File"></p>
<p>From a technical standpoint, shadows are the result of the engine taking a snapshot of the silhouette of an actor and projecting it onto other actors. From a visual perspective, shadows work the same way in a game engine that they do in real life. Imagine standing outside where the sun is shining on you from behind and casting your shadow onto the ground in front of you.</p>
<p>&nbsp;</p>
<hr style="clear: both;">
<h2>Indirect or Bounce Lighting</h2>
<p><img style="float: right; padding: 0 0 20px 20px;" src="https://vertexschool.instructure.com/courses/18/files/964/preview?verifier=0T0aZjPAOqzjOVLuqkiMSXFciFKVSIs9S0zJPKKt" alt="Bounce Lighting.jpg" width="600" height="497" data-api-endpoint="https://vertexschool.instructure.com/api/v1/courses/18/files/964" data-api-returntype="File"></p>
<p>This type of lighting refers to light that has been reflected off of one surface onto another surface. When light hits an object, depending on the reflectivity of the surface, a certain amount of light is absorbed and another amount reflected. The light that is reflected often takes on some of the color properties of the object it is bouncing off of. The light that is reflected or bounced comes across softer than direct light.</p>
<p>In the image, notice how when the purple surface is placed next to the white surfaces, light that hits it is reflected off to cast a softer purple tint onto the white surfaces.</p>