# CascadingParameters Performance

A simple project aiming to measure the effect of CascadingParameters to the RenderBatch size in a Blazor Server scenario.

The project consists of 3 pages, each rendering a table with 20 columns and 200 rows. Each page is using a separate 'set' of components - a set without any cascading parameters, a set with cascading parameters with `IsFixed=true`, and a set of components with cascading parameters and `IsFixed=false`

## Results
The results below have been measured by simply inspecting the blazor signalR websocket hub

### Initial page load - RenderBatch Size

| No Cascading |Cascading(IsFixed=true) | Cascading(IsFixed=false) |
| :----: | :----:| :----:|
| 1.1MB | 1.3MB | 1.2MB |

### StateHasChanged call from the top-level component - RenderBatchSize

| No Cascading |Cascading(IsFixed=true) | Cascading(IsFixed=false) |
| :----: |:----:| :----:|
| 50.6kB | 101kB | 247kB |