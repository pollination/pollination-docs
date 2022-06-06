# Visualize Results on the Web

In [this](download-output.md) section we downloaded the "visualization" output of the daylight-factor study that we ran, which downloaded a file named "daylight\_factor.vtkjs". We will now visualize that file in the Pollination web app.

Install the following libraries first

```python
pip install streamlit-vtkjs
```

Visualize the vtkjs file in the web app

```python
from streamlit_vtkjs import st_vtkjs
from pathlib import Path

vtkjs_path = Path('daylight_factor.vtkjs')
st_vtkjs(content=vtkjs_path.read_bytes(), key='df')
```

This should render the model inside the Pollination viewer in the web app;&#x20;

![](../.gitbook/assets/pollination-apps/viewer.png)

In order to learn more about how to integrate the Pollination viewer in your app, read this [section](integrating-the-pollination-viewer.md).
