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

# min, max
```jsx
import _ from 'lodash';

function testDynamicScaleOptions(bounds) {
  const min = _.isFinite(_.toNumber(bounds[0])) ? bounds[0] : undefined;
  const max = _.isFinite(_.toNumber(bounds[1])) ? bounds[1] : undefined;

  const isValidValue = (value) => {
    return value !== undefined && value !== '';
  };

  const scaleOptions = {
    ...(isValidValue(min) && { min }),
    ...(isValidValue(max) && { max }),
  };

  console.log(`Testing with bounds: [${bounds}]`);
  console.log(`Resulting scale options: `, scaleOptions);
}

// 테스트 케이스 실행
testDynamicScaleOptions(['10', '20']); // 유효한 숫자 문자열
testDynamicScaleOptions(['not a number', '20']); // 유효하지 않은 값과 유효한 값
testDynamicScaleOptions([undefined, '30']); // undefined와 유효한 값
testDynamicScaleOptions(['40', undefined]); // 유효한 값과 undefined
testDynamicScaleOptions(['not a number', 'also not a number']); // 유효하지 않은 값들
```
* isValidValue 함수 추가
