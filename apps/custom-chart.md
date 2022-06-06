# Create a Custom Chart

In this section, we will see how you can add a customized chart to your Pollination app. We will filter the dry bulb temperature data coming out of an EPW file and will visualize it as a Plotly chart in a Pollination app.

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

Create an EPW object from an epw file and get the dry bulb temperature.

```python
epw = EPW("file path to epw file")
dbt = epw.dry_bulb_temperature
```

Apply some customizations to the dry bulb temperature. for example, let's visualize the dry bulb temperature between 18 and 24 degrees Celsius during 9am to 5pm all year.

```python
dbt_work_hours = dbt.filter_by_analysis_period(
    AnalysisPeriod(1, 1, 9, 12, 31, 17)).filter_by_conditional_statement('a>=18 and a<=24')
```

Create a Plotly figure from the customized chart

```python
figure = dbt_work_hours.heat_map()
```

Visualize the customized dry bulb temperature chart

```python
st.title("Dry bulb temperature")
st.plotly_chart(figure, use_container_width=True)
```

You should see a customized annual heatmap appear in the Streamlit app.&#x20;

![](../.gitbook/assets/pollination-apps/dbt\_custom.png)
