# Dart

usage: **\`\`\`dart**

renders:

```dart
// comment
/*
multiline
comment
*/


library dart_example;
import 'package:http/http.dart' as http;
import "dart:io" show HttpClient, RedirectInfo;
part 'foo.dart';
part of bar;

var str = 'Test';
String str2 = "Test";
String strWithNewline = "test\n";
String multiline = '''
this
is
multiline string
''';
var rawString = r"raw string";
var stringWithInterpolation = 'Value: $value';
var expressionInString = 'Value: ${value + 1}';

var symbol = #symbol;

assert(str == str2);
final x = 10;
const y = 500 * x;
var hex = 0xff;
double z = 1.22e-17;

fun(num x) {
  print('The argument is x');
}

class A {
  @override
  void fooMethod {
  }
}


class B {
}

class C extends A implements B {
}

void main() {
  var collection=[1,2,3,4,5];
  for(var a in collection) {
    if (a != 7) {
      print(a);
    } else {
      print(a + 1);
    }
  }
}
