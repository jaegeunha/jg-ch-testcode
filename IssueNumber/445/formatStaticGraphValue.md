
```
export const formatStaticGraphValue = (axes, value) => {
  let formattedValue;

  switch (axes?.y?.base) {
    case 'raw':
      if (value >= 1e5) {
        formattedValue = value.toExponential(2);
      } else {
        formattedValue = value;
      }
      break;
    case '10':
      if (value >= 1e9) {
        formattedValue = (value / 1e9).toFixed(2) + ' B';
      } else if (value >= 1e6) {
        formattedValue = (value / 1e6).toFixed(2) + ' M';
      } else if (value >= 1e3) {
        formattedValue = (value / 1e3).toFixed(2) + ' K';
      } else {
        formattedValue = value;
      }
      break;
    case '2':
    default:
      if (value >= 1024 * 1024 * 1024) {
        formattedValue = (value / (1024 * 1024 * 1024)).toFixed(2) + ' GB';
      } else if (value >= 1024 * 1024) {
        formattedValue = (value / (1024 * 1024)).toFixed(2) + ' MB';
      } else if (value >= 1024) {
        formattedValue = (value / 1024).toFixed(2) + ' KB';
      } else {
        formattedValue = value + ' B';
      }
      break;
  }

  const prefix = axes?.y?.prefix ? axes.y.prefix : '';
  const suffix = axes?.y?.suffix ? axes.y.suffix : '';
  return prefix + formattedValue + suffix;
};

const axes = {
  x: {
    bounds: ['', ''],
    label: '',
    prefix: '',
    suffix: '',
    base: '10',
    scale: 'linear',
  },
  y: {
    bounds: ['', ''],
    label: '',
    prefix: '',
    suffix: '',
    base: '10',
    scale: 'linear',
  },
  y2: {
    bounds: ['', ''],
    label: '',
    prefix: '',
    suffix: '',
    base: '10',
    scale: 'linear',
  },
};
console.log(formatStaticGraphValue(axes, 5570568192.0));
console.log(formatStaticGraphValue(axes, 7035438421.33));

const baseAxes = {
  x: {
    bounds: ['', ''],
    label: '',
    prefix: '',
    suffix: '',
    base: '2',
    scale: 'linear',
  },
  y: {
    bounds: ['', ''],
    label: '',
    prefix: '',
    suffix: '',
    base: '2',
    scale: 'linear',
  },
  y2: {
    bounds: ['', ''],
    label: '',
    prefix: '',
    suffix: '',
    base: '10',
    scale: 'linear',
  },
};
console.log(formatStaticGraphValue(baseAxes, 5570568192.0));
console.log(formatStaticGraphValue(baseAxes, 7035438421.33));

```