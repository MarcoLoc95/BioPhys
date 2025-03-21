---
jupytext:
    formats: md:myst
    text_representation:
        extension: .md
        format_name: myst
kernelspec:
    display_name: Python 3 (ipykernel)
    language: python
    name: python3
---

# Scaling laws

Scaling laws on Log-Log plots

```{code-cell} ipython3
:tags: [remove-input]

import plotly.graph_objects as go

def f_vdw_doubleprime(rho, a, b):
    """
    Calculates the second derivative of the free energy density for a
    Van der Waals fluid.
    """
    return kbt/(rho*(1-b*rho)) + kbt*b/(1-b*rho)**2 - 2*a

range_a = np.arange(27.0/8.0, 5, 0.1)

## Create plot
fig = go.Figure()

base_traces = 0 # Number of traces that are always visible

# Add traces, one for each slider step
for a in range_a:
    rhosol = fsolve(conditions_for_coexistence, x0=[0.05, 0.7], args=(a,b))
    rho_turningpoints = fsolve(f_vdw_doubleprime, x0=[0.1, 0.5], args=(a,b))    
    fig.add_trace(
        go.Scatter(
            visible=False,
            x=[rhosol[0], rhosol[0], rho_turningpoints[0], rho_turningpoints[0]],
            y=[0, -1, -1, 0],
            fill="toself",
            mode='lines',
            name='nucleation and growth',
            line=dict(color=nucleatn_color)))
    fig.add_trace(
        go.Scatter(
            visible=False,
            x=[rho_turningpoints[1], rho_turningpoints[1], rhosol[1], rhosol[1]],
            y=[0, -1, -1, 0],
            fill="toself",
            mode='lines',
            name='nucleation and growth',
            line=dict(color=nucleatn_color),
            showlegend=False))    
    fig.add_trace(
        go.Scatter(
            visible=False,
            x=[rho_turningpoints[0], rho_turningpoints[0], rho_turningpoints[1], rho_turningpoints[1]],
            y=[0, -1, -1, 0],
            fill="toself",
            mode='lines',
            name='spinodal decomposition',
            line=dict(color=spinodal_color)))    
    fig.add_trace(        
        go.Scatter(
            visible=False,
            x=rho,
            y=f_vdw(rho, a, b),
            line=dict(color=line),
            mode='lines',
            name='VdW fluid'))
    fig.add_trace(  
        go.Scatter(
            visible=False,
            x=rho,
            y=f_mix(rho, a, b),
            line=dict(color='#000000'),
            mode='lines',
            name='phase separated'))

traces_per_step = 5 # Number of traces per value of a

# Show the traces for one value of a when loading the plot (initial setup)
active_a_index = 5
for i in range(traces_per_step):
    curr_idx = int(base_traces + active_a_index*traces_per_step + i)
    fig.data[curr_idx].visible = True

# Create and add slider
steps = []
for i in range(0, range_a.shape[0]):
    visarray = [False] * len(fig.data)
    visarray[0:base_traces] = [True] * base_traces
    curr_idx = int(base_traces + i * traces_per_step)
    next_idx = int(base_traces + (i+1) * traces_per_step)
    visarray[curr_idx:next_idx] = [True] * traces_per_step
    step = dict(
        method="update",
        args=[{"visible": visarray}],
        label=round(range_a[i], 1)
    )
    steps.append(step)

sliders = [dict(
    active=active_a_index,
    currentvalue={"prefix": "a/b: "},
    steps=steps
)]

fig.update_layout(
    sliders=sliders,
    legend_title="Legend",
)

fig.update_xaxes(title_text=r'density $\rho$', range=[rho[0], rho[-1]])

# Update yaxis properties
fig.update_yaxes(title_text=r'free energy density $f$', range=[-1, 0])

fig
```