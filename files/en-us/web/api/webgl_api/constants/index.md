---
title: WebGL constants
slug: Web/API/WebGL_API/Constants
tags:
  - API
  - Reference
  - WebGL
  - constants
---
<div>{{WebGLSidebar}}</div>

<p>The <a href="/en-US/docs/Web/API/WebGL_API">WebGL API</a> provides several constants that are passed into or returned by functions. All constants are of type {{domxref("WebGL_API/Types", "GLenum")}}.</p>

<p>Standard WebGL constants are installed on the {{domxref("WebGLRenderingContext")}} and {{domxref("WebGL2RenderingContext")}} objects, so that you use them as <code>gl.CONSTANT_NAME</code>:</p>

<pre class="brush: js">var canvas = document.getElementById('myCanvas');
var gl = canvas.getContext('webgl');

gl.getParameter(gl.LINE_WIDTH);
</pre>

<p>Some constants are also provided by <a href="/en-US/docs/Web/API/WebGL_API/Using_Extensions">WebGL extensions</a>. A <a href="#constants_defined_in_webgl_extensions">list</a> is provided below.</p>

<pre class="brush: js">var debugInfo = gl.getExtension('WEBGL_debug_renderer_info');
var vendor = gl.getParameter(debugInfo.UNMASKED_VENDOR_WEBGL);</pre>

<p>The <a href="/en-US/docs/Web/API/WebGL_API/Tutorial" title="WebGL tutorial">WebGL tutorial</a> has more information, examples, and resources on how to get started with WebGL.</p>

<h2 id="Table_of_contents">Table of contents</h2>

<ul>
 <li><a href="#standard_webgl_1_constants">Standard WebGL 1 constants</a></li>
 <li><a href="#additional_constants_defined_webgl_2">Standard WebGL 2 constants</a></li>
 <li><a href="#constants_defined_in_webgl_extensions">WebGL extension constants</a></li>
</ul>

<h2 id="Standard_WebGL_1_constants">Standard WebGL 1 constants</h2>

<p>These constants are defined on the {{domxref("WebGLRenderingContext")}} interface.</p>

<h3 id="Clearing_buffers">Clearing buffers</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.clear()")}} to clear buffer masks.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>DEPTH_BUFFER_BIT</code></td>
   <td>0x00000100</td>
   <td>Passed to <code>clear</code> to clear the current depth buffer.</td>
  </tr>
  <tr>
   <td><code>STENCIL_BUFFER_BIT</code></td>
   <td>0x00000400</td>
   <td>Passed to <code>clear</code> to clear the current stencil buffer.</td>
  </tr>
  <tr>
   <td><code>COLOR_BUFFER_BIT</code></td>
   <td>0x00004000</td>
   <td>Passed to <code>clear</code> to clear the current color buffer.</td>
  </tr>
 </tbody>
</table>

<h3 id="Rendering_primitives">Rendering primitives</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.drawElements()")}} or {{domxref("WebGLRenderingContext.drawArrays()")}} to specify what kind of primitive to render.</p>

<table class="no-markdown">
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>POINTS</code></td>
   <td>0x0000</td>
   <td>Passed to <code>drawElements</code> or <code>drawArrays</code> to draw single points.</td>
  </tr>
  <tr>
   <td><code>LINES</code></td>
   <td>0x0001</td>
   <td>Passed to <code>drawElements</code> or <code>drawArrays</code> to draw lines. Each vertex connects to the one after it.</td>
  </tr>
  <tr>
   <td><code>LINE_LOOP</code></td>
   <td>0x0002</td>
   <td>Passed to <code>drawElements</code> or <code>drawArrays</code> to draw lines. Each set of two vertices is treated as a separate line segment.</td>
  </tr>
  <tr>
   <td><code>LINE_STRIP</code></td>
   <td>0x0003</td>
   <td>Passed to <code>drawElements</code> or <code>drawArrays</code> to draw a connected group of line segments from the first vertex to the last.</td>
  </tr>
  <tr>
   <td><code>TRIANGLES</code></td>
   <td>0x0004</td>
   <td>Passed to <code>drawElements</code> or <code>drawArrays</code> to draw triangles. Each set of three vertices creates a separate triangle.</td>
  </tr>
  <tr>
   <td><code>TRIANGLE_STRIP</code></td>
   <td>0x0005</td>
   <td>Passed to <code>drawElements</code> or <code>drawArrays</code> to draw a connected group of triangles.</td>
  </tr>
  <tr>
   <td><code>TRIANGLE_FAN</code></td>
   <td>0x0006</td>
   <td>Passed to <code>drawElements</code> or <code>drawArrays</code> to draw a connected group of triangles. Each vertex connects to the previous and the first vertex in the fan.</td>
  </tr>
 </tbody>
</table>

<h3 id="Blending_modes">Blending modes</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.blendFunc()")}} or {{domxref("WebGLRenderingContext.blendFuncSeparate()")}} to specify the blending mode (for both, RBG and alpha, or separately).</p>

<table class="no-markdown">
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>ZERO</code></td>
   <td>0</td>
   <td>Passed to <code>blendFunc</code> or <code>blendFuncSeparate</code> to turn off a component.</td>
  </tr>
  <tr>
   <td><code>ONE</code></td>
   <td>1</td>
   <td>Passed to <code>blendFunc</code> or <code>blendFuncSeparate</code> to turn on a component.</td>
  </tr>
  <tr>
   <td><code>SRC_COLOR</code></td>
   <td>0x0300</td>
   <td>Passed to <code>blendFunc</code> or <code>blendFuncSeparate</code> to multiply a component by the source elements color.</td>
  </tr>
  <tr>
   <td><code>ONE_MINUS_SRC_COLOR</code></td>
   <td>0x0301</td>
   <td>Passed to <code>blendFunc</code> or <code>blendFuncSeparate</code> to multiply a component by one minus the source elements color.</td>
  </tr>
  <tr>
   <td><code>SRC_ALPHA</code></td>
   <td>0x0302</td>
   <td>Passed to <code>blendFunc</code> or <code>blendFuncSeparate</code> to multiply a component by the source's alpha.</td>
  </tr>
  <tr>
   <td><code>ONE_MINUS_SRC_ALPHA</code></td>
   <td>0x0303</td>
   <td>Passed to <code>blendFunc</code> or <code>blendFuncSeparate</code> to multiply a component by one minus the source's alpha.</td>
  </tr>
  <tr>
   <td><code>DST_ALPHA</code></td>
   <td>0x0304</td>
   <td>Passed to <code>blendFunc</code> or <code>blendFuncSeparate</code> to multiply a component by the destination's alpha.</td>
  </tr>
  <tr>
   <td><code>ONE_MINUS_DST_ALPHA</code></td>
   <td>0x0305</td>
   <td>Passed to <code>blendFunc</code> or <code>blendFuncSeparate</code> to multiply a component by one minus the destination's alpha.</td>
  </tr>
  <tr>
   <td><code>DST_COLOR</code></td>
   <td>0x0306</td>
   <td>Passed to <code>blendFunc</code> or <code>blendFuncSeparate</code> to multiply a component by the destination's color.</td>
  </tr>
  <tr>
   <td><code>ONE_MINUS_DST_COLOR</code></td>
   <td>0x0307</td>
   <td>Passed to <code>blendFunc</code> or <code>blendFuncSeparate</code> to multiply a component by one minus the destination's color.</td>
  </tr>
  <tr>
   <td><code>SRC_ALPHA_SATURATE</code></td>
   <td>0x0308</td>
   <td>Passed to <code>blendFunc</code> or <code>blendFuncSeparate</code> to multiply a component by the minimum of source's alpha or one minus the destination's alpha.</td>
  </tr>
  <tr>
   <td><code>CONSTANT_COLOR</code></td>
   <td>0x8001</td>
   <td>Passed to <code>blendFunc</code> or <code>blendFuncSeparate</code> to specify a constant color blend function.</td>
  </tr>
  <tr>
   <td><code>ONE_MINUS_CONSTANT_COLOR</code></td>
   <td>0x8002</td>
   <td>Passed to <code>blendFunc</code> or <code>blendFuncSeparate</code> to specify one minus a constant color blend function.</td>
  </tr>
  <tr>
   <td><code>CONSTANT_ALPHA</code></td>
   <td>0x8003</td>
   <td>Passed to <code>blendFunc</code> or <code>blendFuncSeparate</code> to specify a constant alpha blend function.</td>
  </tr>
  <tr>
   <td><code>ONE_MINUS_CONSTANT_ALPHA</code></td>
   <td>0x8004</td>
   <td>Passed to <code>blendFunc</code> or <code>blendFuncSeparate</code> to specify one minus a constant alpha blend function.</td>
  </tr>
 </tbody>
</table>

<h3 id="Blending_equations">Blending equations</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.blendEquation()")}} or {{domxref("WebGLRenderingContext.blendEquationSeparate()")}} to control how the blending is calculated (for both, RBG and alpha, or separately).</p>

<table class="no-markdown">
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>FUNC_ADD</code></td>
   <td>0x8006</td>
   <td>Passed to <code>blendEquation</code> or <code>blendEquationSeparate</code> to set an addition blend function.</td>
  </tr>
  <tr>
   <td><code>FUNC_SUBTRACT</code></td>
   <td>0x800A</td>
   <td>Passed to <code>blendEquation</code> or <code>blendEquationSeparate</code> to specify a subtraction blend function (source - destination).</td>
  </tr>
  <tr>
   <td><code>FUNC_REVERSE_SUBTRACT</code></td>
   <td>0x800B</td>
   <td>Passed to <code>blendEquation</code> or <code>blendEquationSeparate</code> to specify a reverse subtraction blend function (destination - source).</td>
  </tr>
 </tbody>
</table>

<h3 id="Getting_GL_parameter_information">Getting GL parameter information</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.getParameter()")}} to specify what information to return.</p>

<table class="no-markdown">
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>BLEND_EQUATION</code></td>
   <td>0x8009</td>
   <td>Passed to <code>getParameter</code> to get the current RGB blend function.</td>
  </tr>
  <tr>
   <td><code>BLEND_EQUATION_RGB</code></td>
   <td>0x8009</td>
   <td>Passed to <code>getParameter</code> to get the current RGB blend function. Same as BLEND_EQUATION</td>
  </tr>
  <tr>
   <td><code>BLEND_EQUATION_ALPHA</code></td>
   <td>0x883D</td>
   <td>Passed to <code>getParameter</code> to get the current alpha blend function. Same as BLEND_EQUATION</td>
  </tr>
  <tr>
   <td><code>BLEND_DST_RGB</code></td>
   <td>0x80C8</td>
   <td>Passed to <code>getParameter</code> to get the current destination RGB blend function.</td>
  </tr>
  <tr>
   <td><code>BLEND_SRC_RGB</code></td>
   <td>0x80C9</td>
   <td>Passed to <code>getParameter</code> to get the current destination RGB blend function.</td>
  </tr>
  <tr>
   <td><code>BLEND_DST_ALPHA</code></td>
   <td>0x80CA</td>
   <td>Passed to <code>getParameter</code> to get the current destination alpha blend function.</td>
  </tr>
  <tr>
   <td><code>BLEND_SRC_ALPHA</code></td>
   <td>0x80CB</td>
   <td>Passed to <code>getParameter</code> to get the current source alpha blend function.</td>
  </tr>
  <tr>
   <td><code>BLEND_COLOR</code></td>
   <td>0x8005</td>
   <td>Passed to <code>getParameter</code> to return a the current blend color.</td>
  </tr>
  <tr>
   <td><code>ARRAY_BUFFER_BINDING</code></td>
   <td>0x8894</td>
   <td>Passed to <code>getParameter</code> to get the array buffer binding.</td>
  </tr>
  <tr>
   <td><code>ELEMENT_ARRAY_BUFFER_BINDING</code></td>
   <td>0x8895</td>
   <td>Passed to <code>getParameter</code> to get the current element array buffer.</td>
  </tr>
  <tr>
   <td><code>LINE_WIDTH</code></td>
   <td>0x0B21</td>
   <td>Passed to <code>getParameter</code> to get the current <code>lineWidth</code> (set by the <code>lineWidth</code> method).</td>
  </tr>
  <tr>
   <td><code>ALIASED_POINT_SIZE_RANGE</code></td>
   <td>0x846D</td>
   <td>Passed to <code>getParameter</code> to get the current size of a point drawn with <code>gl.POINTS</code></td>
  </tr>
  <tr>
   <td><code>ALIASED_LINE_WIDTH_RANGE</code></td>
   <td>0x846E</td>
   <td>Passed to <code>getParameter</code> to get the range of available widths for a line. Returns a length-2 array with the lo value at 0, and hight at 1.</td>
  </tr>
  <tr>
   <td><code>CULL_FACE_MODE</code></td>
   <td>0x0B45</td>
   <td>Passed to <code>getParameter</code> to get the current value of <code>cullFace</code>. Should return <code>FRONT</code>, <code>BACK</code>, or <code>FRONT_AND_BACK</code></td>
  </tr>
  <tr>
   <td><code>FRONT_FACE</code></td>
   <td>0x0B46</td>
   <td>Passed to <code>getParameter</code> to determine the current value of <code>frontFace</code>. Should return <code>CW</code> or <code>CCW</code>.</td>
  </tr>
  <tr>
   <td><code>DEPTH_RANGE</code></td>
   <td>0x0B70</td>
   <td>Passed to <code>getParameter</code> to return a length-2 array of floats giving the current depth range.</td>
  </tr>
  <tr>
   <td><code>DEPTH_WRITEMASK</code></td>
   <td>0x0B72</td>
   <td>Passed to <code>getParameter</code> to determine if the depth write mask is enabled.</td>
  </tr>
  <tr>
   <td><code>DEPTH_CLEAR_VALUE</code></td>
   <td>0x0B73</td>
   <td>Passed to <code>getParameter</code> to determine the current depth clear value.</td>
  </tr>
  <tr>
   <td><code>DEPTH_FUNC</code></td>
   <td>0x0B74</td>
   <td>Passed to <code>getParameter</code> to get the current depth function. Returns <code>NEVER</code>, <code>ALWAYS</code>, <code>LESS</code>, <code>EQUAL</code>, <code>LEQUAL</code>, <code>GREATER</code>, <code>GEQUAL</code>, or <code>NOTEQUAL</code>.</td>
  </tr>
  <tr>
   <td><code>STENCIL_CLEAR_VALUE</code></td>
   <td>0x0B91</td>
   <td>Passed to <code>getParameter</code> to get the value the stencil will be cleared to.</td>
  </tr>
  <tr>
   <td><code>STENCIL_FUNC</code></td>
   <td>0x0B92</td>
   <td>Passed to <code>getParameter</code> to get the current stencil function. Returns <code>NEVER</code>, <code>ALWAYS</code>, <code>LESS</code>, <code>EQUAL</code>, <code>LEQUAL</code>, <code>GREATER</code>, <code>GEQUAL</code>, or <code>NOTEQUAL</code>.</td>
  </tr>
  <tr>
   <td><code>STENCIL_FAIL</code></td>
   <td>0x0B94</td>
   <td>Passed to <code>getParameter</code> to get the current stencil fail function. Should return <code>KEEP</code>, <code>REPLACE</code>, <code>INCR</code>, <code>DECR</code>, <code>INVERT</code>, <code>INCR_WRAP</code>, or <code>DECR_WRAP</code>.</td>
  </tr>
  <tr>
   <td><code>STENCIL_PASS_DEPTH_FAIL</code></td>
   <td>0x0B95</td>
   <td>Passed to <code>getParameter</code> to get the current stencil fail function should the depth buffer test fail. Should return <code>KEEP</code>, <code>REPLACE</code>, <code>INCR</code>, <code>DECR</code>, <code>INVERT</code>, <code>INCR_WRAP</code>, or <code>DECR_WRAP</code>.</td>
  </tr>
  <tr>
   <td><code>STENCIL_PASS_DEPTH_PASS</code></td>
   <td>0x0B96</td>
   <td>Passed to <code>getParameter</code> to get the current stencil fail function should the depth buffer test pass. Should return KEEP, REPLACE, INCR, DECR, INVERT, INCR_WRAP, or DECR_WRAP.</td>
  </tr>
  <tr>
   <td><code>STENCIL_REF</code></td>
   <td>0x0B97</td>
   <td>Passed to <code>getParameter</code> to get the reference value used for stencil tests.</td>
  </tr>
  <tr>
   <td><code>STENCIL_VALUE_MASK</code></td>
   <td>0x0B93</td>
   <td></td>
  </tr>
  <tr>
   <td><code>STENCIL_WRITEMASK</code></td>
   <td>0x0B98</td>
   <td></td>
  </tr>
  <tr>
   <td><code>STENCIL_BACK_FUNC</code></td>
   <td>0x8800</td>
   <td></td>
  </tr>
  <tr>
   <td><code>STENCIL_BACK_FAIL</code></td>
   <td>0x8801</td>
   <td></td>
  </tr>
  <tr>
   <td><code>STENCIL_BACK_PASS_DEPTH_FAIL</code></td>
   <td>0x8802</td>
   <td></td>
  </tr>
  <tr>
   <td><code>STENCIL_BACK_PASS_DEPTH_PASS</code></td>
   <td>0x8803</td>
   <td></td>
  </tr>
  <tr>
   <td><code>STENCIL_BACK_REF</code></td>
   <td>0x8CA3</td>
   <td></td>
  </tr>
  <tr>
   <td><code>STENCIL_BACK_VALUE_MASK</code></td>
   <td>0x8CA4</td>
   <td></td>
  </tr>
  <tr>
   <td><code>STENCIL_BACK_WRITEMASK</code></td>
   <td>0x8CA5</td>
   <td></td>
  </tr>
  <tr>
   <td><code>VIEWPORT</code></td>
   <td>0x0BA2</td>
   <td>Returns an {{jsxref("Int32Array")}} with four elements for the current viewport dimensions.</td>
  </tr>
  <tr>
   <td><code>SCISSOR_BOX</code></td>
   <td>0x0C10</td>
   <td>Returns an {{jsxref("Int32Array")}} with four elements for the current scissor box dimensions.</td>
  </tr>
  <tr>
   <td><code>COLOR_CLEAR_VALUE</code></td>
   <td>0x0C22</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_WRITEMASK</code></td>
   <td>0x0C23</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNPACK_ALIGNMENT</code></td>
   <td>0x0CF5</td>
   <td></td>
  </tr>
  <tr>
   <td><code>PACK_ALIGNMENT</code></td>
   <td>0x0D05</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_TEXTURE_SIZE</code></td>
   <td>0x0D33</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_VIEWPORT_DIMS</code></td>
   <td>0x0D3A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SUBPIXEL_BITS</code></td>
   <td>0x0D50</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RED_BITS</code></td>
   <td>0x0D52</td>
   <td></td>
  </tr>
  <tr>
   <td><code>GREEN_BITS</code></td>
   <td>0x0D53</td>
   <td></td>
  </tr>
  <tr>
   <td><code>BLUE_BITS</code></td>
   <td>0x0D54</td>
   <td></td>
  </tr>
  <tr>
   <td><code>ALPHA_BITS</code></td>
   <td>0x0D55</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DEPTH_BITS</code></td>
   <td>0x0D56</td>
   <td></td>
  </tr>
  <tr>
   <td><code>STENCIL_BITS</code></td>
   <td>0x0D57</td>
   <td></td>
  </tr>
  <tr>
   <td><code>POLYGON_OFFSET_UNITS</code></td>
   <td>0x2A00</td>
   <td></td>
  </tr>
  <tr>
   <td><code>POLYGON_OFFSET_FACTOR</code></td>
   <td>0x8038</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_BINDING_2D</code></td>
   <td>0x8069</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SAMPLE_BUFFERS</code></td>
   <td>0x80A8</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SAMPLES</code></td>
   <td>0x80A9</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SAMPLE_COVERAGE_VALUE</code></td>
   <td>0x80AA</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SAMPLE_COVERAGE_INVERT</code></td>
   <td>0x80AB</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COMPRESSED_TEXTURE_FORMATS</code></td>
   <td>0x86A3</td>
   <td></td>
  </tr>
  <tr>
   <td><code>VENDOR</code></td>
   <td>0x1F00</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RENDERER</code></td>
   <td>0x1F01</td>
   <td></td>
  </tr>
  <tr>
   <td><code>VERSION</code></td>
   <td>0x1F02</td>
   <td></td>
  </tr>
  <tr>
   <td><code>IMPLEMENTATION_COLOR_READ_TYPE</code></td>
   <td>0x8B9A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>IMPLEMENTATION_COLOR_READ_FORMAT</code></td>
   <td>0x8B9B</td>
   <td></td>
  </tr>
  <tr>
   <td><code>BROWSER_DEFAULT_WEBGL</code></td>
   <td>0x9244</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Buffers">Buffers</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.bufferData()")}}, {{domxref("WebGLRenderingContext.bufferSubData()")}}, {{domxref("WebGLRenderingContext.bindBuffer()")}}, or {{domxref("WebGLRenderingContext.getBufferParameter()")}}.</p>

<table class="no-markdown">
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>STATIC_DRAW</code></td>
   <td>0x88E4</td>
   <td>Passed to <code>bufferData</code> as a hint about whether the contents of the buffer are likely to be used often and not change often.</td>
  </tr>
  <tr>
   <td><code>STREAM_DRAW</code></td>
   <td>0x88E0</td>
   <td>Passed to <code>bufferData</code> as a hint about whether the contents of the buffer are likely to not be used often.</td>
  </tr>
  <tr>
   <td><code>DYNAMIC_DRAW</code></td>
   <td>0x88E8</td>
   <td>Passed to <code>bufferData</code> as a hint about whether the contents of the buffer are likely to be used often and change often.</td>
  </tr>
  <tr>
   <td><code>ARRAY_BUFFER</code></td>
   <td>0x8892</td>
   <td>Passed to <code>bindBuffer</code> or <code>bufferData</code> to specify the type of buffer being used.</td>
  </tr>
  <tr>
   <td><code>ELEMENT_ARRAY_BUFFER</code></td>
   <td>0x8893</td>
   <td>Passed to <code>bindBuffer</code> or <code>bufferData</code> to specify the type of buffer being used.</td>
  </tr>
  <tr>
   <td><code>BUFFER_SIZE</code></td>
   <td>0x8764</td>
   <td>Passed to <code>getBufferParameter</code> to get a buffer's size.</td>
  </tr>
  <tr>
   <td><code>BUFFER_USAGE</code></td>
   <td>0x8765</td>
   <td>Passed to <code>getBufferParameter</code> to get the hint for the buffer passed in when it was created.</td>
  </tr>
 </tbody>
</table>

<h3 id="Vertex_attributes">Vertex attributes</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.getVertexAttrib()")}}.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>CURRENT_VERTEX_ATTRIB</code></td>
   <td>0x8626</td>
   <td>Passed to <code>getVertexAttrib</code> to read back the current vertex attribute.</td>
  </tr>
  <tr>
   <td><code>VERTEX_ATTRIB_ARRAY_ENABLED</code></td>
   <td>0x8622</td>
   <td></td>
  </tr>
  <tr>
   <td><code>VERTEX_ATTRIB_ARRAY_SIZE</code></td>
   <td>0x8623</td>
   <td></td>
  </tr>
  <tr>
   <td><code>VERTEX_ATTRIB_ARRAY_STRIDE</code></td>
   <td>0x8624</td>
   <td></td>
  </tr>
  <tr>
   <td><code>VERTEX_ATTRIB_ARRAY_TYPE</code></td>
   <td>0x8625</td>
   <td></td>
  </tr>
  <tr>
   <td><code>VERTEX_ATTRIB_ARRAY_NORMALIZED</code></td>
   <td>0x886A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>VERTEX_ATTRIB_ARRAY_POINTER</code></td>
   <td>0x8645</td>
   <td></td>
  </tr>
  <tr>
   <td><code>VERTEX_ATTRIB_ARRAY_BUFFER_BINDING</code></td>
   <td>0x889F</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Culling">Culling</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.cullFace()")}}.</p>

<table class="no-markdown">
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>CULL_FACE</code></td>
   <td>0x0B44</td>
   <td>Passed to <code>enable</code>/<code>disable</code> to turn on/off culling. Can also be used with <code>getParameter</code> to find the current culling method.</td>
  </tr>
  <tr>
   <td><code>FRONT</code></td>
   <td>0x0404</td>
   <td>Passed to <code>cullFace</code> to specify that only front faces should be culled.</td>
  </tr>
  <tr>
   <td><code>BACK</code></td>
   <td>0x0405</td>
   <td>Passed to <code>cullFace</code> to specify that only back faces should be culled.</td>
  </tr>
  <tr>
   <td><code>FRONT_AND_BACK</code></td>
   <td>0x0408</td>
   <td>Passed to <code>cullFace</code> to specify that front and back faces should be culled.</td>
  </tr>
 </tbody>
</table>

<h3 id="Enabling_and_disabling">Enabling and disabling</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.enable()")}} or {{domxref("WebGLRenderingContext.disable()")}}.</p>

<table class="no-markdown">
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>BLEND</code></td>
   <td>0x0BE2</td>
   <td>Passed to <code>enable</code>/<code>disable</code> to turn on/off blending. Can also be used with <code>getParameter</code> to find the current blending method.</td>
  </tr>
  <tr>
   <td><code>DEPTH_TEST</code></td>
   <td>0x0B71</td>
   <td>Passed to <code>enable</code>/<code>disable</code> to turn on/off the depth test. Can also be used with <code>getParameter</code> to query the depth test.</td>
  </tr>
  <tr>
   <td><code>DITHER</code></td>
   <td>0x0BD0</td>
   <td>Passed to <code>enable</code>/<code>disable</code> to turn on/off dithering. Can also be used with <code>getParameter</code> to find the current dithering method.</td>
  </tr>
  <tr>
   <td><code>POLYGON_OFFSET_FILL</code></td>
   <td>0x8037</td>
   <td>Passed to <code>enable</code>/<code>disable</code> to turn on/off the polygon offset. Useful for rendering hidden-line images, decals, and or solids with highlighted edges. Can also be used with <code>getParameter</code> to query the scissor test.</td>
  </tr>
  <tr>
   <td><code>SAMPLE_ALPHA_TO_COVERAGE</code></td>
   <td>0x809E</td>
   <td>Passed to <code>enable</code>/<code>disable</code> to turn on/off the alpha to coverage. Used in multi-sampling alpha channels.</td>
  </tr>
  <tr>
   <td><code>SAMPLE_COVERAGE</code></td>
   <td>0x80A0</td>
   <td>Passed to <code>enable</code>/<code>disable</code> to turn on/off the sample coverage. Used in multi-sampling.</td>
  </tr>
  <tr>
   <td><code>SCISSOR_TEST</code></td>
   <td>0x0C11</td>
   <td>Passed to <code>enable</code>/<code>disable</code> to turn on/off the scissor test. Can also be used with <code>getParameter</code> to query the scissor test.</td>
  </tr>
  <tr>
   <td><code>STENCIL_TEST</code></td>
   <td>0x0B90</td>
   <td>Passed to <code>enable</code>/<code>disable</code> to turn on/off the stencil test. Can also be used with <code>getParameter</code> to query the stencil test.</td>
  </tr>
 </tbody>
</table>

<h3 id="Errors">Errors</h3>

<p>Constants returned from {{domxref("WebGLRenderingContext.getError()")}}.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>NO_ERROR</code></td>
   <td>0</td>
   <td>Returned from <code>getError</code>.</td>
  </tr>
  <tr>
   <td><code>INVALID_ENUM</code></td>
   <td>0x0500</td>
   <td>Returned from <code>getError</code>.</td>
  </tr>
  <tr>
   <td><code>INVALID_VALUE</code></td>
   <td>0x0501</td>
   <td>Returned from <code>getError</code>.</td>
  </tr>
  <tr>
   <td><code>INVALID_OPERATION</code></td>
   <td>0x0502</td>
   <td>Returned from <code>getError</code>.</td>
  </tr>
  <tr>
   <td><code>OUT_OF_MEMORY</code></td>
   <td>0x0505</td>
   <td>Returned from <code>getError</code>.</td>
  </tr>
  <tr>
   <td><code>CONTEXT_LOST_WEBGL</code></td>
   <td>0x9242</td>
   <td>Returned from <code>getError</code>.</td>
  </tr>
 </tbody>
</table>

<h3 id="Front_face_directions">Front face directions</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.frontFace()")}}.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>CW</code></td>
   <td>0x0900</td>
   <td>Passed to <code>frontFace</code> to specify the front face of a polygon is drawn in the clockwise direction</td>
  </tr>
  <tr>
   <td><code>CCW</code></td>
   <td>0x0901</td>
   <td>Passed to <code>frontFace</code> to specify the front face of a polygon is drawn in the counter clockwise direction</td>
  </tr>
 </tbody>
</table>

<h3 id="Hints">Hints</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.hint()")}}</p>

<table class="no-markdown">
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>DONT_CARE</code></td>
   <td>0x1100</td>
   <td>There is no preference for this behavior.</td>
  </tr>
  <tr>
   <td><code>FASTEST</code></td>
   <td>0x1101</td>
   <td>The most efficient behavior should be used.</td>
  </tr>
  <tr>
   <td><code>NICEST</code></td>
   <td>0x1102</td>
   <td>The most correct or the highest quality option should be used.</td>
  </tr>
  <tr>
   <td><code>GENERATE_MIPMAP_HINT</code></td>
   <td>0x8192</td>
   <td>Hint for the quality of filtering when generating mipmap images with {{domxref("WebGLRenderingContext.generateMipmap()")}}.</td>
  </tr>
 </tbody>
</table>

<h3 id="Data_types">Data types</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>BYTE</code></td>
   <td>0x1400</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_BYTE</code></td>
   <td>0x1401</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SHORT</code></td>
   <td>0x1402</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_SHORT</code></td>
   <td>0x1403</td>
   <td></td>
  </tr>
  <tr>
   <td><code>INT</code></td>
   <td>0x1404</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_INT</code></td>
   <td>0x1405</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FLOAT</code></td>
   <td>0x1406</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Pixel_formats">Pixel formats</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>DEPTH_COMPONENT</code></td>
   <td>0x1902</td>
   <td></td>
  </tr>
  <tr>
   <td><code>ALPHA</code></td>
   <td>0x1906</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGB</code></td>
   <td>0x1907</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGBA</code></td>
   <td>0x1908</td>
   <td></td>
  </tr>
  <tr>
   <td><code>LUMINANCE</code></td>
   <td>0x1909</td>
   <td></td>
  </tr>
  <tr>
   <td><code>LUMINANCE_ALPHA</code></td>
   <td>0x190A</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Pixel_types">Pixel types</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>UNSIGNED_BYTE</code></td>
   <td>0x1401</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_SHORT_4_4_4_4</code></td>
   <td>0x8033</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_SHORT_5_5_5_1</code></td>
   <td>0x8034</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_SHORT_5_6_5</code></td>
   <td>0x8363</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Shaders">Shaders</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.createShader()")}} or {{domxref("WebGLRenderingContext.getShaderParameter()")}}</p>

<table class="no-markdown">
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>FRAGMENT_SHADER</code></td>
   <td>0x8B30</td>
   <td>Passed to <code>createShader</code> to define a fragment shader.</td>
  </tr>
  <tr>
   <td><code>VERTEX_SHADER</code></td>
   <td>0x8B31</td>
   <td>Passed to <code>createShader</code> to define a vertex shader</td>
  </tr>
  <tr>
   <td><code>COMPILE_STATUS</code></td>
   <td>0x8B81</td>
   <td>Passed to <code>getShaderParameter</code> to get the status of the compilation. Returns false if the shader was not compiled. You can then query <code>getShaderInfoLog</code> to find the exact error</td>
  </tr>
  <tr>
   <td><code>DELETE_STATUS</code></td>
   <td>0x8B80</td>
   <td>Passed to <code>getShaderParameter</code> to determine if a shader was deleted via <code>deleteShader</code>. Returns true if it was, false otherwise.</td>
  </tr>
  <tr>
   <td><code>LINK_STATUS</code></td>
   <td>0x8B82</td>
   <td>Passed to <code>getProgramParameter</code> after calling <code>linkProgram</code> to determine if a program was linked correctly. Returns false if there were errors. Use <code>getProgramInfoLog</code> to find the exact error.</td>
  </tr>
  <tr>
   <td><code>VALIDATE_STATUS</code></td>
   <td>0x8B83</td>
   <td>Passed to <code>getProgramParameter</code> after calling <code>validateProgram</code> to determine if it is valid. Returns false if errors were found.</td>
  </tr>
  <tr>
   <td><code>ATTACHED_SHADERS</code></td>
   <td>0x8B85</td>
   <td>Passed to <code>getProgramParameter</code> after calling <code>attachShader</code> to determine if the shader was attached correctly. Returns false if errors occurred.</td>
  </tr>
  <tr>
   <td><code>ACTIVE_ATTRIBUTES</code></td>
   <td>0x8B89</td>
   <td>Passed to <code>getProgramParameter</code> to get the number of attributes active in a program.</td>
  </tr>
  <tr>
   <td><code>ACTIVE_UNIFORMS</code></td>
   <td>0x8B86</td>
   <td>Passed to <code>getProgramParameter</code> to get the number of uniforms active in a program.</td>
  </tr>
  <tr>
   <td><code>MAX_VERTEX_ATTRIBS</code></td>
   <td>0x8869</td>
   <td>The maximum number of entries possible in the vertex attribute list.</td>
  </tr>
  <tr>
   <td><code>MAX_VERTEX_UNIFORM_VECTORS</code></td>
   <td>0x8DFB</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_VARYING_VECTORS</code></td>
   <td>0x8DFC</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_COMBINED_TEXTURE_IMAGE_UNITS</code></td>
   <td>0x8B4D</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_VERTEX_TEXTURE_IMAGE_UNITS</code></td>
   <td>0x8B4C</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_TEXTURE_IMAGE_UNITS</code></td>
   <td>0x8872</td>
   <td>Implementation dependent number of maximum texture units. At least 8.</td>
  </tr>
  <tr>
   <td><code>MAX_FRAGMENT_UNIFORM_VECTORS</code></td>
   <td>0x8DFD</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SHADER_TYPE</code></td>
   <td>0x8B4F</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SHADING_LANGUAGE_VERSION</code></td>
   <td>0x8B8C</td>
   <td></td>
  </tr>
  <tr>
   <td><code>CURRENT_PROGRAM</code></td>
   <td>0x8B8D</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Depth_or_stencil_tests">Depth or stencil tests</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.depthFunc()")}} or {{domxref("WebGLRenderingContext.stencilFunc()")}}.</p>

<table class="no-markdown">
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>NEVER</code></td>
   <td>0x0200</td>
   <td>Passed to <code>depthFunction</code> or <code>stencilFunction</code> to specify depth or stencil tests will never pass. i.e. Nothing will be drawn.</td>
  </tr>
  <tr>
   <td><code>LESS</code></td>
   <td>0x0201</td>
   <td>Passed to <code>depthFunction</code> or <code>stencilFunction</code> to specify depth or stencil tests will pass if the new depth value is less than the stored value.</td>
  </tr>
  <tr>
   <td><code>EQUAL</code></td>
   <td>0x0202</td>
   <td>Passed to <code>depthFunction</code> or <code>stencilFunction</code> to specify depth or stencil tests will pass if the new depth value is equals to the stored value.</td>
  </tr>
  <tr>
   <td><code>LEQUAL</code></td>
   <td>0x0203</td>
   <td>Passed to <code>depthFunction</code> or <code>stencilFunction</code> to specify depth or stencil tests will pass if the new depth value is less than or equal to the stored value.</td>
  </tr>
  <tr>
   <td><code>GREATER</code></td>
   <td>0x0204</td>
   <td>Passed to <code>depthFunction</code> or <code>stencilFunction</code> to specify depth or stencil tests will pass if the new depth value is greater than the stored value.</td>
  </tr>
  <tr>
   <td><code>NOTEQUAL</code></td>
   <td>0x0205</td>
   <td>Passed to <code>depthFunction</code> or <code>stencilFunction</code> to specify depth or stencil tests will pass if the new depth value is not equal to the stored value.</td>
  </tr>
  <tr>
   <td><code>GEQUAL</code></td>
   <td>0x0206</td>
   <td>Passed to <code>depthFunction</code> or <code>stencilFunction</code> to specify depth or stencil tests will pass if the new depth value is greater than or equal to the stored value.</td>
  </tr>
  <tr>
   <td><code>ALWAYS</code></td>
   <td>0x0207</td>
   <td>Passed to <code>depthFunction</code> or <code>stencilFunction</code> to specify depth or stencil tests will always pass. i.e. Pixels will be drawn in the order they are drawn.</td>
  </tr>
 </tbody>
</table>

<h3 id="Stencil_actions">Stencil actions</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.stencilOp()")}}.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>KEEP</code></td>
   <td>0x1E00</td>
   <td></td>
  </tr>
  <tr>
   <td><code>REPLACE</code></td>
   <td>0x1E01</td>
   <td></td>
  </tr>
  <tr>
   <td><code>INCR</code></td>
   <td>0x1E02</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DECR</code></td>
   <td>0x1E03</td>
   <td></td>
  </tr>
  <tr>
   <td><code>INVERT</code></td>
   <td>0x150A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>INCR_WRAP</code></td>
   <td>0x8507</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DECR_WRAP</code></td>
   <td>0x8508</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Textures">Textures</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.texParameter", "WebGLRenderingContext.texParameteri()")}}, {{domxref("WebGLRenderingContext.texParameter", "WebGLRenderingContext.texParameterf()")}}, {{domxref("WebGLRenderingContext.bindTexture()")}}, {{domxref("WebGLRenderingContext.texImage2D()")}}, and others.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>NEAREST</code></td>
   <td>0x2600</td>
   <td></td>
  </tr>
  <tr>
   <td><code>LINEAR</code></td>
   <td>0x2601</td>
   <td></td>
  </tr>
  <tr>
   <td><code>NEAREST_MIPMAP_NEAREST</code></td>
   <td>0x2700</td>
   <td></td>
  </tr>
  <tr>
   <td><code>LINEAR_MIPMAP_NEAREST</code></td>
   <td>0x2701</td>
   <td></td>
  </tr>
  <tr>
   <td><code>NEAREST_MIPMAP_LINEAR</code></td>
   <td>0x2702</td>
   <td></td>
  </tr>
  <tr>
   <td><code>LINEAR_MIPMAP_LINEAR</code></td>
   <td>0x2703</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_MAG_FILTER</code></td>
   <td>0x2800</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_MIN_FILTER</code></td>
   <td>0x2801</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_WRAP_S</code></td>
   <td>0x2802</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_WRAP_T</code></td>
   <td>0x2803</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_2D</code></td>
   <td>0x0DE1</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE</code></td>
   <td>0x1702</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_CUBE_MAP</code></td>
   <td>0x8513</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_BINDING_CUBE_MAP</code></td>
   <td>0x8514</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_CUBE_MAP_POSITIVE_X</code></td>
   <td>0x8515</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_CUBE_MAP_NEGATIVE_X</code></td>
   <td>0x8516</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_CUBE_MAP_POSITIVE_Y</code></td>
   <td>0x8517</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_CUBE_MAP_NEGATIVE_Y</code></td>
   <td>0x8518</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_CUBE_MAP_POSITIVE_Z</code></td>
   <td>0x8519</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_CUBE_MAP_NEGATIVE_Z</code></td>
   <td>0x851A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_CUBE_MAP_TEXTURE_SIZE</code></td>
   <td>0x851C</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE0 - 31</code></td>
   <td>0x84C0 - 0x84DF</td>
   <td>A texture unit.</td>
  </tr>
  <tr>
   <td><code>ACTIVE_TEXTURE</code></td>
   <td>0x84E0</td>
   <td>The current active texture unit.</td>
  </tr>
  <tr>
   <td><code>REPEAT</code></td>
   <td>0x2901</td>
   <td></td>
  </tr>
  <tr>
   <td><code>CLAMP_TO_EDGE</code></td>
   <td>0x812F</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MIRRORED_REPEAT</code></td>
   <td>0x8370</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Uniform_types">Uniform types</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>FLOAT_VEC2</code></td>
   <td>0x8B50</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FLOAT_VEC3</code></td>
   <td>0x8B51</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FLOAT_VEC4</code></td>
   <td>0x8B52</td>
   <td></td>
  </tr>
  <tr>
   <td><code>INT_VEC2</code></td>
   <td>0x8B53</td>
   <td></td>
  </tr>
  <tr>
   <td><code>INT_VEC3</code></td>
   <td>0x8B54</td>
   <td></td>
  </tr>
  <tr>
   <td><code>INT_VEC4</code></td>
   <td>0x8B55</td>
   <td></td>
  </tr>
  <tr>
   <td><code>BOOL</code></td>
   <td>0x8B56</td>
   <td></td>
  </tr>
  <tr>
   <td><code>BOOL_VEC2</code></td>
   <td>0x8B57</td>
   <td></td>
  </tr>
  <tr>
   <td><code>BOOL_VEC3</code></td>
   <td>0x8B58</td>
   <td></td>
  </tr>
  <tr>
   <td><code>BOOL_VEC4</code></td>
   <td>0x8B59</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FLOAT_MAT2</code></td>
   <td>0x8B5A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FLOAT_MAT3</code></td>
   <td>0x8B5B</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FLOAT_MAT4</code></td>
   <td>0x8B5C</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SAMPLER_2D</code></td>
   <td>0x8B5E</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SAMPLER_CUBE</code></td>
   <td>0x8B60</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Shader_precision-specified_types">Shader precision-specified types</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>LOW_FLOAT</code></td>
   <td>0x8DF0</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MEDIUM_FLOAT</code></td>
   <td>0x8DF1</td>
   <td></td>
  </tr>
  <tr>
   <td><code>HIGH_FLOAT</code></td>
   <td>0x8DF2</td>
   <td></td>
  </tr>
  <tr>
   <td><code>LOW_INT</code></td>
   <td>0x8DF3</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MEDIUM_INT</code></td>
   <td>0x8DF4</td>
   <td></td>
  </tr>
  <tr>
   <td><code>HIGH_INT</code></td>
   <td>0x8DF5</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Framebuffers_and_renderbuffers">Framebuffers and renderbuffers</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>FRAMEBUFFER</code></td>
   <td>0x8D40</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RENDERBUFFER</code></td>
   <td>0x8D41</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGBA4</code></td>
   <td>0x8056</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGB5_A1</code></td>
   <td>0x8057</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGB565</code></td>
   <td>0x8D62</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DEPTH_COMPONENT16</code></td>
   <td>0x81A5</td>
   <td></td>
  </tr>
  <tr>
   <td><code>STENCIL_INDEX8</code></td>
   <td>0x8D48</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DEPTH_STENCIL</code></td>
   <td>0x84F9</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RENDERBUFFER_WIDTH</code></td>
   <td>0x8D42</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RENDERBUFFER_HEIGHT</code></td>
   <td>0x8D43</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RENDERBUFFER_INTERNAL_FORMAT</code></td>
   <td>0x8D44</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RENDERBUFFER_RED_SIZE</code></td>
   <td>0x8D50</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RENDERBUFFER_GREEN_SIZE</code></td>
   <td>0x8D51</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RENDERBUFFER_BLUE_SIZE</code></td>
   <td>0x8D52</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RENDERBUFFER_ALPHA_SIZE</code></td>
   <td>0x8D53</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RENDERBUFFER_DEPTH_SIZE</code></td>
   <td>0x8D54</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RENDERBUFFER_STENCIL_SIZE</code></td>
   <td>0x8D55</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_ATTACHMENT_OBJECT_TYPE</code></td>
   <td>0x8CD0</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_ATTACHMENT_OBJECT_NAME</code></td>
   <td>0x8CD1</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_ATTACHMENT_TEXTURE_LEVEL</code></td>
   <td>0x8CD2</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_ATTACHMENT_TEXTURE_CUBE_MAP_FACE</code></td>
   <td>0x8CD3</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT0</code></td>
   <td>0x8CE0</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DEPTH_ATTACHMENT</code></td>
   <td>0x8D00</td>
   <td></td>
  </tr>
  <tr>
   <td><code>STENCIL_ATTACHMENT</code></td>
   <td>0x8D20</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DEPTH_STENCIL_ATTACHMENT</code></td>
   <td>0x821A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>NONE</code></td>
   <td>0</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_COMPLETE</code></td>
   <td>0x8CD5</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_INCOMPLETE_ATTACHMENT</code></td>
   <td>0x8CD6</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_INCOMPLETE_MISSING_ATTACHMENT</code></td>
   <td>0x8CD7</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_INCOMPLETE_DIMENSIONS</code></td>
   <td>0x8CD9</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_UNSUPPORTED</code></td>
   <td>0x8CDD</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_BINDING</code></td>
   <td>0x8CA6</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RENDERBUFFER_BINDING</code></td>
   <td>0x8CA7</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_RENDERBUFFER_SIZE</code></td>
   <td>0x84E8</td>
   <td></td>
  </tr>
  <tr>
   <td><code>INVALID_FRAMEBUFFER_OPERATION</code></td>
   <td>0x0506</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Pixel_storage_modes">Pixel storage modes</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.pixelStorei()")}}.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>UNPACK_FLIP_Y_WEBGL</code></td>
   <td>0x9240</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNPACK_PREMULTIPLY_ALPHA_WEBGL</code></td>
   <td>0x9241</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNPACK_COLORSPACE_CONVERSION_WEBGL</code></td>
   <td>0x9243</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h2 id="Additional_constants_defined_WebGL_2">Additional constants defined WebGL 2</h2>

<p>These constants are defined on the {{domxref("WebGL2RenderingContext")}} interface. All WebGL 1 constants are also available in a WebGL 2 context.</p>

<h3 id="Getting_GL_parameter_information_2">Getting GL parameter information</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.getParameter()")}} to specify what information to return.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>READ_BUFFER</code></td>
   <td>0x0C02</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNPACK_ROW_LENGTH</code></td>
   <td>0x0CF2</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNPACK_SKIP_ROWS</code></td>
   <td>0x0CF3</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNPACK_SKIP_PIXELS</code></td>
   <td>0x0CF4</td>
   <td></td>
  </tr>
  <tr>
   <td><code>PACK_ROW_LENGTH</code></td>
   <td>0x0D02</td>
   <td></td>
  </tr>
  <tr>
   <td><code>PACK_SKIP_ROWS</code></td>
   <td>0x0D03</td>
   <td></td>
  </tr>
  <tr>
   <td><code>PACK_SKIP_PIXELS</code></td>
   <td>0x0D04</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_BINDING_3D</code></td>
   <td>0x806A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNPACK_SKIP_IMAGES</code></td>
   <td>0x806D</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNPACK_IMAGE_HEIGHT</code></td>
   <td>0x806E</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_3D_TEXTURE_SIZE</code></td>
   <td>0x8073</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_ELEMENTS_VERTICES</code></td>
   <td>0x80E8</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_ELEMENTS_INDICES</code></td>
   <td>0x80E9</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_TEXTURE_LOD_BIAS</code></td>
   <td>0x84FD</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_FRAGMENT_UNIFORM_COMPONENTS</code></td>
   <td>0x8B49</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_VERTEX_UNIFORM_COMPONENTS</code></td>
   <td>0x8B4A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_ARRAY_TEXTURE_LAYERS</code></td>
   <td>0x88FF</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MIN_PROGRAM_TEXEL_OFFSET</code></td>
   <td>0x8904</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_PROGRAM_TEXEL_OFFSET</code></td>
   <td>0x8905</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_VARYING_COMPONENTS</code></td>
   <td>0x8B4B</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAGMENT_SHADER_DERIVATIVE_HINT</code></td>
   <td>0x8B8B</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RASTERIZER_DISCARD</code></td>
   <td>0x8C89</td>
   <td></td>
  </tr>
  <tr>
   <td><code>VERTEX_ARRAY_BINDING</code></td>
   <td>0x85B5</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_VERTEX_OUTPUT_COMPONENTS</code></td>
   <td>0x9122</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_FRAGMENT_INPUT_COMPONENTS</code></td>
   <td>0x9125</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_SERVER_WAIT_TIMEOUT</code></td>
   <td>0x9111</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_ELEMENT_INDEX</code></td>
   <td>0x8D6B</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Textures_2">Textures</h3>

<p>Constants passed to {{domxref("WebGLRenderingContext.texParameter", "WebGLRenderingContext.texParameteri()")}}, {{domxref("WebGLRenderingContext.texParameter", "WebGLRenderingContext.texParameterf()")}}, {{domxref("WebGLRenderingContext.bindTexture()")}}, {{domxref("WebGLRenderingContext.texImage2D()")}}, and others.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>RED</code></td>
   <td>0x1903</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGB8</code></td>
   <td>0x8051</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGBA8</code></td>
   <td>0x8058</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGB10_A2</code></td>
   <td>0x8059</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_3D</code></td>
   <td>0x806F</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_WRAP_R</code></td>
   <td>0x8072</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_MIN_LOD</code></td>
   <td>0x813A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_MAX_LOD</code></td>
   <td>0x813B</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_BASE_LEVEL</code></td>
   <td>0x813C</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_MAX_LEVEL</code></td>
   <td>0x813D</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_COMPARE_MODE</code></td>
   <td>0x884C</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_COMPARE_FUNC</code></td>
   <td>0x884D</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SRGB</code></td>
   <td>0x8C40</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SRGB8</code></td>
   <td>0x8C41</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SRGB8_ALPHA8</code></td>
   <td>0x8C43</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COMPARE_REF_TO_TEXTURE</code></td>
   <td>0x884E</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGBA32F</code></td>
   <td>0x8814</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGB32F</code></td>
   <td>0x8815</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGBA16F</code></td>
   <td>0x881A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGB16F</code></td>
   <td>0x881B</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_2D_ARRAY</code></td>
   <td>0x8C1A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_BINDING_2D_ARRAY</code></td>
   <td>0x8C1D</td>
   <td></td>
  </tr>
  <tr>
   <td><code>R11F_G11F_B10F</code></td>
   <td>0x8C3A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGB9_E5</code></td>
   <td>0x8C3D</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGBA32UI</code></td>
   <td>0x8D70</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGB32UI</code></td>
   <td>0x8D71</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGBA16UI</code></td>
   <td>0x8D76</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGB16UI</code></td>
   <td>0x8D77</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGBA8UI</code></td>
   <td>0x8D7C</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGB8UI</code></td>
   <td>0x8D7D</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGBA32I</code></td>
   <td>0x8D82</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGB32I</code></td>
   <td>0x8D83</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGBA16I</code></td>
   <td>0x8D88</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGB16I</code></td>
   <td>0x8D89</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGBA8I</code></td>
   <td>0x8D8E</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGB8I</code></td>
   <td>0x8D8F</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RED_INTEGER</code></td>
   <td>0x8D94</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGB_INTEGER</code></td>
   <td>0x8D98</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGBA_INTEGER</code></td>
   <td>0x8D99</td>
   <td></td>
  </tr>
  <tr>
   <td><code>R8</code></td>
   <td>0x8229</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RG8</code></td>
   <td>0x822B</td>
   <td></td>
  </tr>
  <tr>
   <td>R16F</td>
   <td>0x822D</td>
   <td></td>
  </tr>
  <tr>
   <td>R32F</td>
   <td>0x822E</td>
   <td></td>
  </tr>
  <tr>
   <td>RG16F</td>
   <td>0x822F</td>
   <td></td>
  </tr>
  <tr>
   <td>RG32F</td>
   <td>0x8230</td>
   <td></td>
  </tr>
  <tr>
   <td>R8I</td>
   <td>0x8231</td>
   <td></td>
  </tr>
  <tr>
   <td>R8UI</td>
   <td>0x8232</td>
   <td></td>
  </tr>
  <tr>
   <td>R16I</td>
   <td>0x8233</td>
   <td></td>
  </tr>
  <tr>
   <td>R16UI</td>
   <td>0x8234</td>
   <td></td>
  </tr>
  <tr>
   <td>R32I</td>
   <td>0x8235</td>
   <td></td>
  </tr>
  <tr>
   <td>R32UI</td>
   <td>0x8236</td>
   <td></td>
  </tr>
  <tr>
   <td>RG8I</td>
   <td>0x8237</td>
   <td></td>
  </tr>
  <tr>
   <td>RG8UI</td>
   <td>0x8238</td>
   <td></td>
  </tr>
  <tr>
   <td>RG16I</td>
   <td>0x8239</td>
   <td></td>
  </tr>
  <tr>
   <td>RG16UI</td>
   <td>0x823A</td>
   <td></td>
  </tr>
  <tr>
   <td>RG32I</td>
   <td>0x823B</td>
   <td></td>
  </tr>
  <tr>
   <td>RG32UI</td>
   <td>0x823C</td>
   <td></td>
  </tr>
  <tr>
   <td>R8_SNORM</td>
   <td>0x8F94</td>
   <td></td>
  </tr>
  <tr>
   <td>RG8_SNORM</td>
   <td>0x8F95</td>
   <td></td>
  </tr>
  <tr>
   <td>RGB8_SNORM</td>
   <td>0x8F96</td>
   <td></td>
  </tr>
  <tr>
   <td>RGBA8_SNORM</td>
   <td>0x8F97</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RGB10_A2UI</code></td>
   <td>0x906F</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_IMMUTABLE_FORMAT </code></td>
   <td>0x912F</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TEXTURE_IMMUTABLE_LEVELS</code></td>
   <td>0x82DF</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Pixel_types_2">Pixel types</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>UNSIGNED_INT_2_10_10_10_REV</code></td>
   <td>0x8368</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_INT_10F_11F_11F_REV</code></td>
   <td>0x8C3B</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_INT_5_9_9_9_REV</code></td>
   <td>0x8C3E</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FLOAT_32_UNSIGNED_INT_24_8_REV</code></td>
   <td>0x8DAD</td>
   <td></td>
  </tr>
  <tr>
   <td>UNSIGNED_INT_24_8</td>
   <td>0x84FA</td>
   <td></td>
  </tr>
  <tr>
   <td><code>HALF_FLOAT</code></td>
   <td>0x140B</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RG</code></td>
   <td>0x8227</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RG_INTEGER</code></td>
   <td>0x8228</td>
   <td></td>
  </tr>
  <tr>
   <td><code>INT_2_10_10_10_REV</code></td>
   <td>0x8D9F</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Queries">Queries</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>CURRENT_QUERY</code></td>
   <td>0x8865</td>
   <td></td>
  </tr>
  <tr>
   <td><code>QUERY_RESULT </code></td>
   <td>0x8866</td>
   <td></td>
  </tr>
  <tr>
   <td><code>QUERY_RESULT_AVAILABLE</code></td>
   <td>0x8867</td>
   <td></td>
  </tr>
  <tr>
   <td><code>ANY_SAMPLES_PASSED</code></td>
   <td>0x8C2F</td>
   <td></td>
  </tr>
  <tr>
   <td><code>ANY_SAMPLES_PASSED_CONSERVATIVE</code></td>
   <td>0x8D6A</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Draw_buffers">Draw buffers</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>MAX_DRAW_BUFFERS</code></td>
   <td>0x8824</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER0</code></td>
   <td>0x8825</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER1</code></td>
   <td>0x8826</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER2</code></td>
   <td>0x8827</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER3</code></td>
   <td>0x8828</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER4</code></td>
   <td>0x8829</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER5</code></td>
   <td>0x882A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER6</code></td>
   <td>0x882B</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER7</code></td>
   <td>0x882C</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER8</code></td>
   <td>0x882D</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER9</code></td>
   <td>0x882E</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER10</code></td>
   <td>0x882F</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER11</code></td>
   <td>0x8830</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER12</code></td>
   <td>0x8831</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER13</code></td>
   <td>0x8832</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER14</code></td>
   <td>0x8833</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER15</code></td>
   <td>0x8834</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_COLOR_ATTACHMENTS</code></td>
   <td>0x8CDF</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT1</code></td>
   <td>0x8CE1</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT2</code></td>
   <td>0x8CE2</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT3</code></td>
   <td>0x8CE3</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT4</code></td>
   <td>0x8CE4</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT5</code></td>
   <td>0x8CE5</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT6</code></td>
   <td>0x8CE6</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT7</code></td>
   <td>0x8CE7</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT8</code></td>
   <td>0x8CE8</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT9</code></td>
   <td>0x8CE9</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT10</code></td>
   <td>0x8CEA</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT11</code></td>
   <td>0x8CEB</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT12</code></td>
   <td>0x8CEC</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT13</code></td>
   <td>0x8CED</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT14</code></td>
   <td>0x8CEE</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT15</code></td>
   <td>0x8CEF</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Samplers">Samplers</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>SAMPLER_3D</code></td>
   <td>0x8B5F</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SAMPLER_2D_SHADOW</code></td>
   <td>0x8B62</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SAMPLER_2D_ARRAY</code></td>
   <td>0x8DC1</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SAMPLER_2D_ARRAY_SHADOW</code></td>
   <td>0x8DC4</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SAMPLER_CUBE_SHADOW</code></td>
   <td>0x8DC5</td>
   <td></td>
  </tr>
  <tr>
   <td><code>INT_SAMPLER_2D</code></td>
   <td>0x8DCA</td>
   <td></td>
  </tr>
  <tr>
   <td><code>INT_SAMPLER_3D</code></td>
   <td>0x8DCB</td>
   <td></td>
  </tr>
  <tr>
   <td><code>INT_SAMPLER_CUBE</code></td>
   <td>0x8DCC</td>
   <td></td>
  </tr>
  <tr>
   <td><code>INT_SAMPLER_2D_ARRAY</code></td>
   <td>0x8DCF</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_INT_SAMPLER_2D</code></td>
   <td>0x8DD2</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_INT_SAMPLER_3D</code></td>
   <td>0x8DD3</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_INT_SAMPLER_CUBE</code></td>
   <td>0x8DD4</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_INT_SAMPLER_2D_ARRAY</code></td>
   <td>0x8DD7</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_SAMPLES</code></td>
   <td>0x8D57</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SAMPLER_BINDING</code></td>
   <td>0x8919</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Buffers_2">Buffers</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>PIXEL_PACK_BUFFER</code></td>
   <td>0x88EB</td>
   <td></td>
  </tr>
  <tr>
   <td><code>PIXEL_UNPACK_BUFFER</code></td>
   <td>0x88EC</td>
   <td></td>
  </tr>
  <tr>
   <td><code>PIXEL_PACK_BUFFER_BINDING</code></td>
   <td>0x88ED</td>
   <td></td>
  </tr>
  <tr>
   <td><code>PIXEL_UNPACK_BUFFER_BINDING </code></td>
   <td>0x88EF</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COPY_READ_BUFFER</code></td>
   <td>0x8F36</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COPY_WRITE_BUFFER</code></td>
   <td>0x8F37</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COPY_READ_BUFFER_BINDING</code></td>
   <td>0x8F36</td>
   <td></td>
  </tr>
  <tr>
   <td><code>COPY_WRITE_BUFFER_BINDING</code></td>
   <td>0x8F37</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Data_types_2">Data types</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>FLOAT_MAT2x3</code></td>
   <td>0x8B65</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FLOAT_MAT2x4</code></td>
   <td>0x8B66</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FLOAT_MAT3x2</code></td>
   <td>0x8B67</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FLOAT_MAT3x4 </code></td>
   <td>0x8B68</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FLOAT_MAT4x2</code></td>
   <td>0x8B69</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FLOAT_MAT4x3</code></td>
   <td>0x8B6A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_INT_VEC2</code></td>
   <td>0x8DC6</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_INT_VEC3</code></td>
   <td>0x8DC7</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_INT_VEC4</code></td>
   <td>0x8DC8</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_NORMALIZED</code></td>
   <td>0x8C17</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SIGNED_NORMALIZED</code></td>
   <td>0x8F9C</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Vertex_attributes_2">Vertex attributes</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>VERTEX_ATTRIB_ARRAY_INTEGER </code></td>
   <td>0x88FD</td>
   <td></td>
  </tr>
  <tr>
   <td><code>VERTEX_ATTRIB_ARRAY_DIVISOR</code></td>
   <td>0x88FE</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Transform_feedback">Transform feedback</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>TRANSFORM_FEEDBACK_BUFFER_MODE</code></td>
   <td>0x8C7F</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_TRANSFORM_FEEDBACK_SEPARATE_COMPONENTS</code></td>
   <td>0x8C80</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TRANSFORM_FEEDBACK_VARYINGS</code></td>
   <td>0x8C83</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TRANSFORM_FEEDBACK_BUFFER_START</code></td>
   <td>0x8C84</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TRANSFORM_FEEDBACK_BUFFER_SIZE</code></td>
   <td>0x8C85</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TRANSFORM_FEEDBACK_PRIMITIVES_WRITTEN</code></td>
   <td>0x8C88</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_TRANSFORM_FEEDBACK_INTERLEAVED_COMPONENTS</code></td>
   <td>0x8C8A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_TRANSFORM_FEEDBACK_SEPARATE_ATTRIBS</code></td>
   <td>0x8C8B</td>
   <td></td>
  </tr>
  <tr>
   <td><code>INTERLEAVED_ATTRIBS</code></td>
   <td>0x8C8C</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SEPARATE_ATTRIBS</code></td>
   <td>0x8C8D</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TRANSFORM_FEEDBACK_BUFFER</code></td>
   <td>0x8C8E</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TRANSFORM_FEEDBACK_BUFFER_BINDING</code></td>
   <td>0x8C8F</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TRANSFORM_FEEDBACK</code></td>
   <td>0x8E22</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TRANSFORM_FEEDBACK_PAUSED</code></td>
   <td>0x8E23</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TRANSFORM_FEEDBACK_ACTIVE</code></td>
   <td>0x8E24</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TRANSFORM_FEEDBACK_BINDING</code></td>
   <td>0x8E25</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Framebuffers_and_renderbuffers_2">Framebuffers and renderbuffers</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>FRAMEBUFFER_ATTACHMENT_COLOR_ENCODING</code></td>
   <td>0x8210</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_ATTACHMENT_COMPONENT_TYPE</code></td>
   <td>0x8211</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_ATTACHMENT_RED_SIZE</code></td>
   <td>0x8212</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_ATTACHMENT_GREEN_SIZE</code></td>
   <td>0x8213</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_ATTACHMENT_BLUE_SIZE</code></td>
   <td>0x8214</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_ATTACHMENT_ALPHA_SIZE</code></td>
   <td>0x8215</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_ATTACHMENT_DEPTH_SIZE</code></td>
   <td>0x8216</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_ATTACHMENT_STENCIL_SIZE</code></td>
   <td>0x8217</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_DEFAULT</code></td>
   <td>0x8218</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DEPTH_STENCIL_ATTACHMENT</code></td>
   <td>0x821A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DEPTH_STENCIL</code></td>
   <td>0x84F9</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DEPTH24_STENCIL8</code></td>
   <td>0x88F0</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_FRAMEBUFFER_BINDING</code></td>
   <td>0x8CA6</td>
   <td></td>
  </tr>
  <tr>
   <td><code>READ_FRAMEBUFFER</code></td>
   <td>0x8CA8</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DRAW_FRAMEBUFFER</code></td>
   <td>0x8CA9</td>
   <td></td>
  </tr>
  <tr>
   <td><code>READ_FRAMEBUFFER_BINDING</code></td>
   <td>0x8CAA</td>
   <td></td>
  </tr>
  <tr>
   <td><code>RENDERBUFFER_SAMPLES</code></td>
   <td>0x8CAB</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_ATTACHMENT_TEXTURE_LAYER</code></td>
   <td>0x8CD4</td>
   <td></td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_INCOMPLETE_MULTISAMPLE</code></td>
   <td>0x8D56</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Uniforms">Uniforms</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>UNIFORM_BUFFER</code></td>
   <td>0x8A11</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_BUFFER_BINDING</code></td>
   <td>0x8A28</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_BUFFER_START</code></td>
   <td>0x8A29</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_BUFFER_SIZE</code></td>
   <td>0x8A2A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_VERTEX_UNIFORM_BLOCKS</code></td>
   <td>0x8A2B</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_FRAGMENT_UNIFORM_BLOCKS</code></td>
   <td>0x8A2D</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_COMBINED_UNIFORM_BLOCKS</code></td>
   <td>0x8A2E</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_UNIFORM_BUFFER_BINDINGS</code></td>
   <td>0x8A2F</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_UNIFORM_BLOCK_SIZE</code></td>
   <td>0x8A30</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_COMBINED_VERTEX_UNIFORM_COMPONENTS</code></td>
   <td>0x8A31</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_COMBINED_FRAGMENT_UNIFORM_COMPONENTS</code></td>
   <td>0x8A33</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_BUFFER_OFFSET_ALIGNMENT</code></td>
   <td>0x8A34</td>
   <td></td>
  </tr>
  <tr>
   <td><code>ACTIVE_UNIFORM_BLOCKS</code></td>
   <td>0x8A36</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_TYPE </code></td>
   <td>0x8A37</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_SIZE</code></td>
   <td>0x8A38</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_BLOCK_INDEX</code></td>
   <td>0x8A3A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_OFFSET</code></td>
   <td>0x8A3B</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_ARRAY_STRIDE</code></td>
   <td>0x8A3C</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_MATRIX_STRIDE</code></td>
   <td>0x8A3D</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_IS_ROW_MAJOR</code></td>
   <td>0x8A3E</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_BLOCK_BINDING</code></td>
   <td>0x8A3F</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_BLOCK_DATA_SIZE</code></td>
   <td>0x8A40</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_BLOCK_ACTIVE_UNIFORMS</code></td>
   <td>0x8A42</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_BLOCK_ACTIVE_UNIFORM_INDICES</code></td>
   <td>0x8A43</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_BLOCK_REFERENCED_BY_VERTEX_SHADER</code></td>
   <td>0x8A44</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNIFORM_BLOCK_REFERENCED_BY_FRAGMENT_SHADER</code></td>
   <td>0x8A46</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Sync_objects">Sync objects</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>OBJECT_TYPE</code></td>
   <td>0x9112</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SYNC_CONDITION</code></td>
   <td>0x9113</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SYNC_STATUS</code></td>
   <td>0x9114</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SYNC_FLAGS</code></td>
   <td>0x9115</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SYNC_FENCE</code></td>
   <td>0x9116</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SYNC_GPU_COMMANDS_COMPLETE</code></td>
   <td>0x9117</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNALED</code></td>
   <td>0x9118</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SIGNALED</code></td>
   <td>0x9119</td>
   <td></td>
  </tr>
  <tr>
   <td><code>ALREADY_SIGNALED</code></td>
   <td>0x911A</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TIMEOUT_EXPIRED</code></td>
   <td>0x911B</td>
   <td></td>
  </tr>
  <tr>
   <td><code>CONDITION_SATISFIED</code></td>
   <td>0x911C</td>
   <td></td>
  </tr>
  <tr>
   <td><code>WAIT_FAILED</code></td>
   <td>0x911D</td>
   <td></td>
  </tr>
  <tr>
   <td><code>SYNC_FLUSH_COMMANDS_BIT</code></td>
   <td>0x00000001</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="Miscellaneous_constants">Miscellaneous constants</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>COLOR</code></td>
   <td>0x1800</td>
   <td></td>
  </tr>
  <tr>
   <td>DEPTH</td>
   <td>0x1801</td>
   <td></td>
  </tr>
  <tr>
   <td><code>STENCIL</code></td>
   <td>0x1802</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MIN</code></td>
   <td>0x8007</td>
   <td></td>
  </tr>
  <tr>
   <td>MAX</td>
   <td>0x8008</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DEPTH_COMPONENT24</code></td>
   <td>0x81A6</td>
   <td></td>
  </tr>
  <tr>
   <td><code>STREAM_READ</code></td>
   <td>0x88E1</td>
   <td></td>
  </tr>
  <tr>
   <td><code>STREAM_COPY</code></td>
   <td>0x88E2</td>
   <td></td>
  </tr>
  <tr>
   <td><code>STATIC_READ</code></td>
   <td>0x88E5</td>
   <td></td>
  </tr>
  <tr>
   <td><code>STATIC_COPY</code></td>
   <td>0x88E6</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DYNAMIC_READ</code></td>
   <td>0x88E9</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DYNAMIC_COPY</code></td>
   <td>0x88EA</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DEPTH_COMPONENT32F</code></td>
   <td>0x8CAC</td>
   <td></td>
  </tr>
  <tr>
   <td><code>DEPTH32F_STENCIL8</code></td>
   <td>0x8CAD</td>
   <td></td>
  </tr>
  <tr>
   <td><code>INVALID_INDEX</code></td>
   <td>0xFFFFFFFF</td>
   <td></td>
  </tr>
  <tr>
   <td><code>TIMEOUT_IGNORED</code></td>
   <td>-1</td>
   <td></td>
  </tr>
  <tr>
   <td><code>MAX_CLIENT_WAIT_TIMEOUT_WEBGL</code></td>
   <td>0x9247</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h2 id="Constants_defined_in_WebGL_extensions">Constants defined in WebGL extensions</h2>

<h3 id="domxref(ANGLE_instanced_arrays)">{{domxref("ANGLE_instanced_arrays")}}</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>VERTEX_ATTRIB_ARRAY_DIVISOR_ANGLE</code></td>
   <td>0x88FE</td>
   <td>Describes the frequency divisor used for instanced rendering.</td>
  </tr>
 </tbody>
</table>

<h3 id="domxref(WEBGL_debug_renderer_info)">{{domxref("WEBGL_debug_renderer_info")}}</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>UNMASKED_VENDOR_WEBGL</code></td>
   <td>0x9245</td>
   <td>Passed to <code>getParameter</code> to get the vendor string of the graphics driver.</td>
  </tr>
  <tr>
   <td><code>UNMASKED_RENDERER_WEBGL</code></td>
   <td>0x9246</td>
   <td>Passed to <code>getParameter</code> to get the renderer string of the graphics driver.</td>
  </tr>
 </tbody>
</table>

<h3 id="domxref(EXT_texture_filter_anisotropic)">{{domxref("EXT_texture_filter_anisotropic")}}</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>MAX_TEXTURE_MAX_ANISOTROPY_EXT</code></td>
   <td>0x84FF</td>
   <td>Returns the maximum available anisotropy.</td>
  </tr>
  <tr>
   <td><code>TEXTURE_MAX_ANISOTROPY_EXT</code></td>
   <td>0x84FE</td>
   <td>Passed to <code>texParameter</code> to set the desired maximum anisotropy for a texture.</td>
  </tr>
 </tbody>
</table>

<h3 id="domxref(WEBGL_compressed_texture_s3tc)">{{domxref("WEBGL_compressed_texture_s3tc")}}</h3>

<table class="no-markdown">
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>COMPRESSED_RGB_S3TC_DXT1_EXT</code></td>
   <td>0x83F0</td>
   <td>A DXT1-compressed image in an RGB image format.</td>
  </tr>
  <tr>
   <td><code>COMPRESSED_RGBA_S3TC_DXT1_EXT</code></td>
   <td>0x83F1</td>
   <td>A DXT1-compressed image in an RGB image format with a simple on/off alpha value.</td>
  </tr>
  <tr>
   <td><code>COMPRESSED_RGBA_S3TC_DXT3_EXT</code></td>
   <td>0x83F2</td>
   <td>A DXT3-compressed image in an RGBA image format. Compared to a 32-bit RGBA texture, it offers 4:1 compression.</td>
  </tr>
  <tr>
   <td><code>COMPRESSED_RGBA_S3TC_DXT5_EXT</code></td>
   <td>0x83F3</td>
   <td>A DXT5-compressed image in an RGBA image format. It also provides a 4:1 compression, but differs to the DXT3 compression in how the alpha compression is done.</td>
  </tr>
 </tbody>
</table>

<h3 id="domxref(WEBGL_compressed_texture_etc)">{{domxref("WEBGL_compressed_texture_etc")}}</h3>

<table class="no-markdown">
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>COMPRESSED_R11_EAC</code></td>
   <td>0x9270</td>
   <td>One-channel (red) unsigned format compression.</td>
  </tr>
  <tr>
   <td><code>COMPRESSED_SIGNED_R11_EAC</code></td>
   <td>0x9271</td>
   <td>One-channel (red) signed format compression.</td>
  </tr>
  <tr>
   <td><code>COMPRESSED_RG11_EAC</code></td>
   <td>0x9272</td>
   <td>Two-channel (red and green) unsigned format compression.</td>
  </tr>
  <tr>
   <td><code>COMPRESSED_SIGNED_RG11_EAC</code></td>
   <td>0x9273</td>
   <td>Two-channel (red and green) signed format compression.</td>
  </tr>
  <tr>
   <td><code>COMPRESSED_RGB8_ETC2</code></td>
   <td>0x9274</td>
   <td>Compresses RBG8 data with no alpha channel.</td>
  </tr>
  <tr>
   <td><code>COMPRESSED_RGBA8_ETC2_EAC</code></td>
   <td>0x9275</td>
   <td>Compresses RGBA8 data. The RGB part is encoded the same as <code>RGB_ETC2</code>, but the alpha part is encoded separately.</td>
  </tr>
  <tr>
   <td><code>COMPRESSED_SRGB8_ETC2</code></td>
   <td>0x9276</td>
   <td>Compresses sRBG8 data with no alpha channel.</td>
  </tr>
  <tr>
   <td><code>COMPRESSED_SRGB8_ALPHA8_ETC2_EAC</code></td>
   <td>0x9277</td>
   <td>Compresses sRGBA8 data. The sRGB part is encoded the same as <code>SRGB_ETC2</code>, but the alpha part is encoded separately.</td>
  </tr>
  <tr>
   <td><code>COMPRESSED_RGB8_PUNCHTHROUGH_ALPHA1_ETC2</code></td>
   <td>0x9278</td>
   <td>Similar to <code>RGB8_ETC</code>, but with ability to punch through the alpha channel, which means to make it completely opaque or transparent.</td>
  </tr>
  <tr>
   <td><code>COMPRESSED_SRGB8_PUNCHTHROUGH_ALPHA1_ETC2</code></td>
   <td>0x9279</td>
   <td>Similar to <code>SRGB8_ETC</code>, but with ability to punch through the alpha channel, which means to make it completely opaque or transparent.</td>
  </tr>
 </tbody>
</table>

<h3 id="domxref(WEBGL_compressed_texture_pvrtc)">{{domxref("WEBGL_compressed_texture_pvrtc")}}</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>COMPRESSED_RGB_PVRTC_4BPPV1_IMG</code></td>
   <td>0x8C00</td>
   <td>RGB compression in 4-bit mode. One block for each 4×4 pixels.</td>
  </tr>
  <tr>
   <td><code>COMPRESSED_RGBA_PVRTC_4BPPV1_IMG</code></td>
   <td>0x8C02</td>
   <td>RGBA compression in 4-bit mode. One block for each 4×4 pixels.</td>
  </tr>
  <tr>
   <td><code>COMPRESSED_RGB_PVRTC_2BPPV1_IMG</code></td>
   <td>0x8C01</td>
   <td>RGB compression in 2-bit mode. One block for each 8×4 pixels.</td>
  </tr>
  <tr>
   <td><code>COMPRESSED_RGBA_PVRTC_2BPPV1_IMG</code></td>
   <td>0x8C03</td>
   <td>RGBA compression in 2-bit mode. One block for each 8×4 pixe</td>
  </tr>
 </tbody>
</table>

<h3 id="domxref(WEBGL_compressed_texture_etc1)">{{domxref("WEBGL_compressed_texture_etc1")}}</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>COMPRESSED_RGB_ETC1_WEBGL</code></td>
   <td>0x8D64</td>
   <td>Compresses 24-bit RGB data with no alpha channel.</td>
  </tr>
 </tbody>
</table>

<h3 id="domxref(WEBGL_depth_texture)">{{domxref("WEBGL_depth_texture")}}</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>UNSIGNED_INT_24_8_WEBGL</code></td>
   <td>0x84FA</td>
   <td>Unsigned integer type for 24-bit depth texture data.</td>
  </tr>
 </tbody>
</table>

<h3 id="domxref(OES_texture_half_float)">{{domxref("OES_texture_half_float")}}</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>HALF_FLOAT_OES</code></td>
   <td>0x8D61</td>
   <td>Half floating-point type (16-bit).</td>
  </tr>
 </tbody>
</table>

<h3 id="domxref(WEBGL_color_buffer_float)">{{domxref("WEBGL_color_buffer_float")}}</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>RGBA32F_EXT</code></td>
   <td>0x8814</td>
   <td>RGBA 32-bit floating-point color-renderable format.</td>
  </tr>
  <tr>
   <td><code>RGB32F_EXT</code></td>
   <td>0x8815</td>
   <td>RGB 32-bit floating-point color-renderable format.</td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_ATTACHMENT_COMPONENT_TYPE_EXT</code></td>
   <td>0x8211</td>
   <td></td>
  </tr>
  <tr>
   <td><code>UNSIGNED_NORMALIZED_EXT</code></td>
   <td>0x8C17</td>
   <td></td>
  </tr>
 </tbody>
</table>

<h3 id="domxref(EXT_blend_minmax)">{{domxref("EXT_blend_minmax")}}</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>MIN_EXT</code></td>
   <td>0x8007</td>
   <td>Produces the minimum color components of the source and destination colors.</td>
  </tr>
  <tr>
   <td><code>MAX_EXT</code></td>
   <td>0x8008</td>
   <td>Produces the maximum color components of the source and destination colors.</td>
  </tr>
 </tbody>
</table>

<h3 id="domxref(EXT_sRGB)">{{domxref("EXT_sRGB")}}</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>SRGB_EXT</code></td>
   <td>0x8C40</td>
   <td>Unsized sRGB format that leaves the precision up to the driver.</td>
  </tr>
  <tr>
   <td><code>SRGB_ALPHA_EXT</code></td>
   <td>0x8C42</td>
   <td>Unsized sRGB format with unsized alpha component.</td>
  </tr>
  <tr>
   <td><code>SRGB8_ALPHA8_EXT</code></td>
   <td>0x8C43</td>
   <td>Sized (8-bit) sRGB and alpha formats.</td>
  </tr>
  <tr>
   <td><code>FRAMEBUFFER_ATTACHMENT_COLOR_ENCODING_EXT</code></td>
   <td>0x8210</td>
   <td>Returns the framebuffer color encoding.</td>
  </tr>
 </tbody>
</table>

<h3 id="domxref(OES_standard_derivatives)">{{domxref("OES_standard_derivatives")}}</h3>

<table class="no-markdown">
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>FRAGMENT_SHADER_DERIVATIVE_HINT_OES</code></td>
   <td>0x8B8B</td>
   <td>Indicates the accuracy of the derivative calculation for the GLSL built-in functions: <code>dFdx</code>, <code>dFdy</code>, and <code>fwidth</code>.</td>
  </tr>
 </tbody>
</table>

<h3 id="domxref(WEBGL_draw_buffers)">{{domxref("WEBGL_draw_buffers")}}</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>COLOR_ATTACHMENT0_WEBGL</code></td>
   <td>0x8CE0</td>
   <td>Framebuffer color attachment point</td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT1_WEBGL</code></td>
   <td>0x8CE1</td>
   <td>Framebuffer color attachment point</td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT2_WEBGL</code></td>
   <td>0x8CE2</td>
   <td>Framebuffer color attachment point</td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT3_WEBGL</code></td>
   <td>0x8CE3</td>
   <td>Framebuffer color attachment point</td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT4_WEBGL</code></td>
   <td>0x8CE4</td>
   <td>Framebuffer color attachment point</td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT5_WEBGL</code></td>
   <td>0x8CE5</td>
   <td>Framebuffer color attachment point</td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT6_WEBGL</code></td>
   <td>0x8CE6</td>
   <td>Framebuffer color attachment point</td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT7_WEBGL</code></td>
   <td>0x8CE7</td>
   <td>Framebuffer color attachment point</td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT8_WEBGL</code></td>
   <td>0x8CE8</td>
   <td>Framebuffer color attachment point</td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT9_WEBGL</code></td>
   <td>0x8CE9</td>
   <td>Framebuffer color attachment point</td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT10_WEBGL</code></td>
   <td>0x8CEA</td>
   <td>Framebuffer color attachment point</td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT11_WEBGL</code></td>
   <td>0x8CEB</td>
   <td>Framebuffer color attachment point</td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT12_WEBGL</code></td>
   <td>0x8CEC</td>
   <td>Framebuffer color attachment point</td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT13_WEBGL</code></td>
   <td>0x8CED</td>
   <td>Framebuffer color attachment point</td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT14_WEBGL</code></td>
   <td>0x8CEE</td>
   <td>Framebuffer color attachment point</td>
  </tr>
  <tr>
   <td><code>COLOR_ATTACHMENT15_WEBGL</code></td>
   <td>0x8CEF</td>
   <td>Framebuffer color attachment point</td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER0_WEBGL</code></td>
   <td>0x8825</td>
   <td>Draw buffer</td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER1_WEBGL</code></td>
   <td>0x8826</td>
   <td>Draw buffer</td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER2_WEBGL</code></td>
   <td>0x8827</td>
   <td>Draw buffer</td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER3_WEBGL</code></td>
   <td>0x8828</td>
   <td>Draw buffer</td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER4_WEBGL</code></td>
   <td>0x8829</td>
   <td>Draw buffer</td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER5_WEBGL</code></td>
   <td>0x882A</td>
   <td>Draw buffer</td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER6_WEBGL</code></td>
   <td>0x882B</td>
   <td>Draw buffer</td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER7_WEBGL</code></td>
   <td>0x882C</td>
   <td>Draw buffer</td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER8_WEBGL</code></td>
   <td>0x882D</td>
   <td>Draw buffer</td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER9_WEBGL</code></td>
   <td>0x882E</td>
   <td>Draw buffer</td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER10_WEBGL</code></td>
   <td>0x882F</td>
   <td>Draw buffer</td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER11_WEBGL</code></td>
   <td>0x8830</td>
   <td>Draw buffer</td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER12_WEBGL</code></td>
   <td>0x8831</td>
   <td>Draw buffer</td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER13_WEBGL</code></td>
   <td>0x8832</td>
   <td>Draw buffer</td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER14_WEBGL</code></td>
   <td>0x8833</td>
   <td>Draw buffer</td>
  </tr>
  <tr>
   <td><code>DRAW_BUFFER15_WEBGL</code></td>
   <td>0x8834</td>
   <td>Draw buffer</td>
  </tr>
  <tr>
   <td><code>MAX_COLOR_ATTACHMENTS_WEBGL</code></td>
   <td>0x8CDF</td>
   <td>Maximum number of framebuffer color attachment points</td>
  </tr>
  <tr>
   <td><code>MAX_DRAW_BUFFERS_WEBGL</code></td>
   <td>0x8824</td>
   <td>Maximum number of draw buffers</td>
  </tr>
 </tbody>
</table>

<h3 id="domxref(OES_vertex_array_object)">{{domxref("OES_vertex_array_object")}}</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>VERTEX_ARRAY_BINDING_OES</code></td>
   <td>0x85B5</td>
   <td>The bound vertex array object (VAO).</td>
  </tr>
 </tbody>
</table>

<h3 id="domxref(EXT_disjoint_timer_query)">{{domxref("EXT_disjoint_timer_query")}}</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Constant name</th>
   <th scope="col">Value</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>QUERY_COUNTER_BITS_EXT</code></td>
   <td>0x8864</td>
   <td>The number of bits used to hold the query result for the given target.</td>
  </tr>
  <tr>
   <td><code>CURRENT_QUERY_EXT</code></td>
   <td>0x8865</td>
   <td>The currently active query.</td>
  </tr>
  <tr>
   <td><code>QUERY_RESULT_EXT</code></td>
   <td>0x8866</td>
   <td>The query result.</td>
  </tr>
  <tr>
   <td><code>QUERY_RESULT_AVAILABLE_EXT</code></td>
   <td>0x8867</td>
   <td>A Boolean indicating whether or not a query result is available.</td>
  </tr>
  <tr>
   <td><code>TIME_ELAPSED_EXT</code></td>
   <td>0x88BF</td>
   <td>Elapsed time (in nanoseconds).</td>
  </tr>
  <tr>
   <td><code>TIMESTAMP_EXT</code></td>
   <td>0x8E28</td>
   <td>The current time.</td>
  </tr>
  <tr>
   <td><code>GPU_DISJOINT_EXT</code></td>
   <td>0x8FBB</td>
   <td>A Boolean indicating whether or not the GPU performed any disjoint operation.</td>
  </tr>
 </tbody>
</table>

<h2 id="Specifications">Specifications</h2>

<table>
 <tbody>
  <tr>
   <th scope="col">Specification</th>
   <th scope="col">Status</th>
   <th scope="col">Comment</th>
  </tr>
  <tr>
   <td>{{SpecName('WebGL', "#5.14", "WebGLRenderingContext")}}</td>
   <td>{{Spec2('WebGL')}}</td>
   <td>Initial definition</td>
  </tr>
  <tr>
   <td>{{SpecName('WebGL2', "#3.7", "WebGL2RenderingContext")}}</td>
   <td>{{Spec2('WebGL2')}}</td>
   <td>Defines additional constants.</td>
  </tr>
 </tbody>
</table>

<h2 id="See_also">See also</h2>

<ul>
 <li>{{domxref("WebGLRenderingContext")}}</li>
</ul>