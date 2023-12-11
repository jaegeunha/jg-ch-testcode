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


## 정규표현식 적용
```jsx
// lodash 라이브러리 임포트
const _ = require('lodash');

// 테스트할 함수 정의
function calculateMin(value) {
  const bounds = [value]; // bounds[0] 설정
  const min =
    /^-?\d+(\.\d+)?$/.test(bounds[0]) && _.isFinite(_.toNumber(bounds[0]))
      ? _.toNumber(bounds[0])
      : undefined;
  return min;
}

// 테스트 케이스 정의
const testCases = [
  { value: '123', expected: 123 },
  { value: '-123.45', expected: -123.45 },
  { value: 'abc', expected: undefined },
  { value: '', expected: undefined },
  { value: ' ', expected: undefined },
  { value: null, expected: undefined },
  { value: undefined, expected: undefined },
  { value: {}, expected: undefined },
  { value: [], expected: undefined },
  { value: true, expected: undefined },
  { value: false, expected: undefined }
];

// 테스트 실행
testCases.forEach(({ value, expected }) => {
  const result = calculateMin(value);
  console.log(`Value: ${value}, Expected: ${expected}, Result: ${result}, Test Passed: ${result === expected}`);
});

```
