---
title: Light
template: usermanual-page.tmpl.html
position: 10
---

The Light component attaches a dynamic light source to the Entity. The 'Type' property determines what kind of light is attached and what other properties are available.

The Light component can be enabled or disabled using the toggle in the top right of the component panel. If enabled, the light will light the scene.

#### Directional
![Light component (Directional)][1]
#### Point
![Light component (Point)][2]
#### Spot
![Light component (Spot)][3]

## Properties

<table class="table table-striped">
    <col class="property-name"></col>
    <col class="property-description"></col>
    <tr><th>Property</th><th>Description</th></tr>
    <tr><td>Type</td><td>Can be:
        <ul>
            <li>Directional: a light casting in a uniform direction</li>
            <li>Point: a light casting in all directional around a point</li>
            <li>Spot: a light casting from the apex of a cone</li>
        </ul>
    </td></tr>
    <tr><td>Lightmap</td><td>Enable lightmap baking from this light</td></tr>
    <tr><td>Affect</td><td>Determines which types of objects are lit by this light. Can be any combination of dynamically lit or lightmapped objects.</td></tr>
    <tr><td>Color</td><td>The color of the emitted light.</td></tr>
    <tr><td>Intensity</td><td>The intensity of the light, this acts as a scalar value for the light's color. This value can exceed 1.</td></tr>
    <tr><td>Range</td><td>Point and Spot only. The distance from the spotlight source at which its contribution falls to zero.</td></tr>
    <tr><td>Falloff Mode</td><td>Point and spot only. Controls the rate at which a light attenuates from its position.</td></tr>
    <tr><td>Cone Angles</td><td>Spot only. The inner and outer cone angles, measured from the spotlight's direction, at which light falls from its maximum to zero.</td></tr>
    <tr><td>Shadows</td><td>If checked, the light will cause shadow casting models to cast shadows.</td></tr>
    <tr><td>Update Mode</td><td>Determines when the shadowmap for this light is updated. Can be:
        <ul>
            <li>Once: generated once and never again. Useful if casters, receivers and light are static.</li>
            <li>Realtime: updated every frame.</li>
        </ul>
    </td></tr>
    <tr><td>Resolution</td><td>The resolution of the shadowmap generated by this light source. This property is only used when Cast Shadows is checked. A high value will result in a more accurate shadow but will be at the cost of performance.</td></tr>
    <tr><td>Distance</td><td>Directional lights only. The shadow distance is the maximum distance from the camera beyond which shadows that come from Directional Lights are no longer visible. Smaller values produce more detailed shadows. The closer the limit the less shadow data has to be mapped to, and represented by, any shadow map; shadow map pixels are mapped spatially and so the less distance the shadow map has to cover, the smaller the pixels and so the more resolution any shadow has.</td></tr>
    <tr><td>Shadow Type</td><td>The shadow mapping algorithm to use. The selection will affect the appearance and performance of the shadows. Can be:
        <ul>
            <li>Shadow Map: PCF (Percentage Closer Filtering) shadowmaps.</li>
            <li>Variance Shadow Map (8bit): Low precision shadowmaps. VSM is generally softer than PCF shadows.</li>
            <li>Variance Shadow Map (16bit): Medium precision shadowmaps. Uses twice as much VRAM as 8 bit VSM.</li>
            <li>Variance Shadow Map (32bit): High precision shadowmaps. Uses twice as much VRAM as 16 bit VSM.</li>
        </ul>
    </td></tr>
    <tr><td>Bias</td><td>Bias values enable the tuning of shadows in order to eliminate rendering artifacts, namely 'shadow acne' and 'peter-panning'. The two values are a shadow bias and a normal offset bias.</td></tr>
    <tr><td>Cookie</td><td>Point and spot only. A texture asset to be projected from the light.</td></tr>
    <tr><td>Intensity</td><td>Point and spot only. Defines the strength of the cookie texture.</td></tr>
    <tr><td>Falloff</td><td>Spot only. Disable the spotlight falloff.</td></tr>
</table>

## Scripting Interface

You can control a Light component's properties using a [script component][4]. The Light component's scripting interface is [here][5].

[1]: /images/user-manual/scenes/components/component-light-directional.png
[2]: /images/user-manual/scenes/components/component-light-point.png
[3]: /images/user-manual/scenes/components/component-light-spot.png
[4]: /user-manual/packs/components/script
[5]: /api/pc.LightComponent.html
