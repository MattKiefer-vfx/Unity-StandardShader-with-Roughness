# Unity-StandardShader-with-Roughness
A modification of the Unity 2019 Standard surface shader that lets it work with Roughness maps instead of Smoothness maps.

The Standard surface shader in Unity 2019 allows you to use the alpha channel of the Metallic map as a Smoothness map, where a value of 0 is fully rough and a value of 1 is fully smooth.  However the PBR shaders in most CG software, including Substance Painter, use Roughness maps where the values are the opposite of that.  A typical workflow for going from Substance Painter to Unity is to either use a filter to invert the Roughness maps before export or to use a script or other tool to invert the alpha channel of the Metallic map after export.  

Heck that.  Let's make the shader do that work for us.  

This modification of the Standard shader inverts the values in the alpha channel of the Metallic map when it is read to be used as a Smoothness map, essentially making it work as a Roughness map instead.  The functionality of the Smoothness slider on the shader is unchanged; it still acts as a multiplier against the values of the map, so setting the Smoothness slider down to 0 will make the material ignore the map and render as completely rough, and setting the slider to 1 uses the values from the map without change.  

This was designed for and has been tested in VRChat (Jan 2022) and seems to work fine for Desktop Mode and full VR Mode.  
