# log
```jsx
import _ from 'lodash';

  const type = axes?.y?.scale === 'log' ? 'logarithmic' : undefined


  const dynamicOption = {
    ...STATIC_GRAPH_OPTIONS,
    scales: {
      ...STATIC_GRAPH_OPTIONS.scales,
      x: {
        ...STATIC_GRAPH_OPTIONS.scales?.x,
        title: {
          ...STATIC_GRAPH_OPTIONS.scales?.x?.title,
          text: xAxisTitle,
        },
        ticks: {
          ...STATIC_GRAPH_OPTIONS.scales?.x?.ticks,
          callback: function (value) {
            return (
              axes?.x?.prefix + this.getLabelForValue(value) + axes?.x?.suffix
            )
          },
        },
      },
      y: {
        ...STATIC_GRAPH_OPTIONS.scales?.y,
        ...(isValidValue(min) && {min}),
        ...(isValidValue(max) && {max}),
        // ...(type && {type}),
        title: {
          ...STATIC_GRAPH_OPTIONS.scales?.y?.title,
          text: yAxisTitle,
        },
        ticks: {
          ...STATIC_GRAPH_OPTIONS.scales?.y?.ticks,
          callback: function (value) {
            return (
              axes?.y?.prefix + this.getLabelForValue(value) + axes?.y?.suffix
            )
          },
        },
      },
    },
  }
```

