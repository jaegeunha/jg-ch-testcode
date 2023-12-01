# min, max
## 1번안
```jsx
function testDynamicScaleOptions(minInput, maxInput) {
  // 테스트할 min, max 값
  const [min, max] = [minInput, maxInput];

  // 동적으로 min, max를 포함시키는 객체
  const scaleOptions = {
    ...(typeof min === 'number' && !isNaN(min) && { min }),
    ...(typeof max === 'number' && !isNaN(max) && { max }),
  };

  // 결과 출력
  console.log(`Testing with min: ${min}, max: ${max}`);
  console.log(scaleOptions);
}

// 테스트 실행
testDynamicScaleOptions(10, 20); // 유효한 숫자 값
testDynamicScaleOptions(undefined, undefined); // 정의되지 않은 값
testDynamicScaleOptions('not a number', 30); // 유효하지 않은 값과 유효한 값
testDynamicScaleOptions(NaN, NaN); // NaN 값

```

## 2번안
```jsx
import _ from 'lodash';

function testDynamicScaleOptions(bounds) {
  const min = _.isFinite(_.toNumber(bounds[0])) ? bounds[0] : undefined;
  const max = _.isFinite(_.toNumber(bounds[1])) ? bounds[1] : undefined;

  const scaleOptions = {
    ...(min !== undefined && { min }),
    ...(max !== undefined && { max }),
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
