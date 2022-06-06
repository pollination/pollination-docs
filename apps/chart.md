# Create a Simple Chart

In this section, we will see how you can visualize the yearly dry bulb temperature data from an [EPW](https://bigladdersoftware.com/epx/docs/8-3/auxiliary-programs/energyplus-weather-file-epw-data-dictionary.html) as a Plotly chart in a Pollination app. We're using the [ladybug-charts](https://github.com/ladybug-tools/ladybug-charts) library of Ladybug Tools to to create this chart here. This library can help you create, ladybug monthly charts, daily charts, sun path, wind rose, pyschrometric chart, and more.

Install the following libraries first

```
pip install ladybug-charts streamlit
```

Start by importing the libraries

```python
import streamlit as st
from ladybug.epw import EPW
```

Set the title of the page and layout

```python
st.set_page_config(
    page_title='Dry bulb temperature', layout='wide'
)
```

Create an EPW object from an EPW file and then get the `heatmap` figure. This method returns a Plotly figure with the dry bulb temperature data.

```python
epw = EPW("file path to epw file")
figure = epw.dry_bulb_temperature.heat_map()
```

Finally, add the title to the page and visualize dry bulb temperature as a Plotly chart.

```python
st.plotly_chart(figure, use_container_width=True)
```

You should see an annual heatmap appear in the Streamlit app.&#x20;

![](../.gitbook/assets/pollination-apps/dbt.png)
