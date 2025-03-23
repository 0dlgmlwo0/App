## 1. 구구단을 출력하라.

```dart
void main() {
  StringBuffer mdBuffer = StringBuffer();
  mdBuffer.writeln('# 구구단');

  for (int i = 2; i <= 9; i++) {
    mdBuffer.writeln('\n## ${i}단');
    for (int j = 1; j <= 9; j++) {
      mdBuffer.writeln('- **$i x $j** = ${i * j}');
    }
  }

  print(mdBuffer.toString());
}
```

## 2. 정사각형의 길이를 입력하고 사각형을 출력하라

```dart
void main() {
  var n = 10;
  var result = '';
  for (var y = 0; y < n; y++) {
    for (var x = 0; x < n; x++) {
      if (f1(x, y, n) || f2(x, y, n) || x == y || x == n - y - 1) {
        result += '=';
      } else {
        result += ' ';
      }
    }
    result += '\n';
  }
  print(result);
}

bool f1(int x, int y, int size) {
  return x == 0 || y == 0 || x == size - 1 || y == size - 1;
}

bool f2(int x, int y, int size) {
  return x == 0 || y == 0 || x == size - 1 || y == size - 1;
}
```

## 3. 년/월/일을 입력하면 요일을 출력하라

```dart
void main() {
  var input = '2025-03-11';
  print(getWeekday(input));
}

String getWeekday(String date) {
  DateTime parsedDate = DateTime.parse(date);
  List<String> weekdays = ['월', '화', '수', '목', '금', '토', '일'];
  return weekdays[parsedDate.weekday - 1] + '요일';
}