# Integrate Pollination Viewer

### Pollination Viewer Usage

Pollination App developers can easily integrate the same high performance 3D web viewer that we use throughout our apps in their own work. We offer both a Streamlit component and a React component that can be used by the Pollination community.

The Streamlit component is [published on PyPi](https://pypi.org/project/pollination-streamlit-viewer/), and our React component is [available on npmjs](https://www.npmjs.com/package/lavender-vtkjs).

The Streamlit component can be installed like this:

```shell
pip install pollination-streamlit-viewer
```

This guide will focus on the Streamlit component because that what will be most useful to developers of Pollination Apps. If you're interested in learning more about the React component, please reach out through our forums.

The first resource you should know about is the sample viewer app:\
https://app.pollination.cloud/pollination/apps/viewer-sample-app/?tab=live+app

The code for this app is located here:\
https://github.com/pollination-apps/pollination-viewer-sample/blob/main/app.py

This app exposes all the configurations and features of pollination-streamlit-viewer.

Here's a screenshot of the viewer itself:

![](../.gitbook/assets/integrating-the-pollination-viewer/pollination-viewer-model-loaded.png)

### Instantiating the Viewer in Streamlit

```python
from pollination-streamlit-viewer import viewer

#...

def viewer(
     key: str, *,
     content: bytes = None,
     toolbar: bool = True,
     sidebar: bool = True,
     subscribe: bool = False,
     clear: bool = True,
     action_stack: list = [],
     style: Dict = None)
```

| Argument | Description |
| --- | --- |
| key | A unique string for each instance of the viewer. |
| content | A `.vtkjs` file (see the section below Loading a File) |
| toolbar | A `boolean` that toggles the toolbar visibility. Default is `True`. |
| sidebar | A boolean that toggles the sidebar visiblity. Default is `True`. |
| subscribe | A boolean that toggles subscription to the VTKJS camera and renderer content. Default is `False`. |
| clear | A boolean to clear the current contents from the viewer before loading new content. Default is `True`. |
| action_stack | The action stack is an advanced feature that allows the streamlit component to send actions to the React component's dispatch function. A set of useful actions are demonstrated in the sample app. |
| style | A dictionary to set the style for the viewer. The key and values can be any CSS style attribute. Default is: `{"border": "1px solid #d0d7de", "borderRadius": "2px"}` |

### Return Value

The value returned by `viewer` represents the scene that has been loaded into the viewer. This object is represented as a deeply nested dictionary with fields that often follow the structure of vtk.js objects. By default, this state will contain a single value called scene with an array of all the actors in the scene. This default return value will not update as you update the scene using the viewer controls. This is useful for reading default values, and `actor[id]`s. Those `actor[id]`s are used by some actions to modify actor properties.

If you want to read and respond to values as the viewer state changes, use the `subscribe` toggle described below.

#### Loading a File

You can make use of the Streamlit provided st.file_uploader component to load a .vtkjs file.

```python
_file = st.file_uploader(
     label=".vtkjs scene uploader",
     type=["vtkjs", "vtk", "vtp"],
     help="Upload a .vtkjs scene file"
)

#...

content = _file.getvalue() if _file else None
```

### Subscribe Toggle

The subscribe toggle is a powerful feature that may be easy to misuse. If set, the value returned by st_vtkjs will contain additional fields.

![](../.gitbook/assets/integrating-the-pollination-viewer/subscribe-toggle.png)

These fields contain information about the renderer, legend, and "widgets" (the compass rose and section planes) and will update as the you make changes to the scene. Be warned! This toggle can easily cause your app to go into an infinite rendering loop as the component responds to changes and returns new values. See the last section of this guide Gotchas: Controlling Component Re-rendering.

None of the features in the Sample Viewer App require the subscribe toggle to be set to True, so it shouldn't be necessary in most apps. A scenario in which it might be useful would be if you had a chart elsewhere in the app, and you wanted its min / max values (or color scheme) to stay in sync with the viewer legend's min / max values.

### Action Stack

The action stack is an advanced feature that allows you to send actions to the viewer's dispatch function. Under the hood the viewer's state manage follows a pattern first developed by Redux and is common to React state management. Our Streamlit component executes each action once as they are added to the `action_stack` array. There are a bunch of examples of common things you might want to do in the Sample Viewer App, the full list of available actions will develop over time with the viewer itself. Check the viewer's reducer function for the full list of available actions.

Here's an example of how to set the colorset from streamlit using the `action_stack`:

```python
def handle_colorset ():
    if 'colorset_select' in st.session_state:
        st.session_state.action_stack.append({
        'type': 'color-set',
        'value': st.session_state.colorset_select,
    })

#...

st.selectbox('Color sets', COLORSETS, key='colorset_select', on_change=handle_colorset)
```

This renders the select box in the right hand sidebar:

![](../.gitbook/assets/integrating-the-pollination-viewer/colorset-selector.png)

Please be aware, that if you've set the `subscribe` toggle to `True` this will cause the component to rerender. Please see the previous section on the Subscribe Toggle or the next section Gotchas: Controlling Component Re-Rendering for more information.

### Gotchas: Controlling Component Re-Rendering

By default when the value of variables in Streamlit change, often in response to user input, the component will re-render. When a component like `st_vtkjs` returns input back to Streamlit, it can easily cause an infinite loop of rendering that will cause the Streamlit app to report "Running..." in the top right corner of the app. This will eventually cause the app to fail. To control this behavior there are two techniques that you should employ.

First, use `st.session_state` to prevent a variable from being reinitialize when the app responds to other changing values. st.session_state is a feature of Streamlit, and you can look to their docs to learn more about this feature.

Each Streamlit input component can use it's own session state automatically.

```python
toolbar = st.checkbox('Toolbar', value=True, key='toolbar_toggle', help='Show/Hide the toolbar.')

#...

vtkjs = st_vtkjs(
    toolbar=st.session_state.toolbar_toggle,
)
```

You can also use `st.session_state` yourself.

```python
if 'action_stack' not in st.session_state:
  st.session_state['action_stack'] = []

#...

with vtkjs_container:
  vtkjs = st_vtkjs(
        action_stack=st.session_state.action_stack,
    )
```

The second strategy: don't set the `subscribe` toggle unless you absolutely need to. All of the controls in the Viewer Sample work without this toggle. It is rarely necessary and if you choose to use it, you should know the ins and outs of this problem.

### Report Bugs

These software are both under active development, please report bugs on the [Pollination forum](https://discourse.pollination.cloud/).
