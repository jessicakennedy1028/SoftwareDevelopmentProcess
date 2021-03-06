# C++

usage: **\`\`\`cpp**

renders:

```cpp
int quote_delims = 100'000'000
int float_delims = 100.00'00
int hex_delims = 0xFF'Fa12

// string literal with encoding-prefix
char str1[] = u8"UTF-8 string";
char16_t str2[] = u"UTF-16 string";
char32_t str3[] = U"UTF-32 string";

// Raw string literal
char raw_str1[] = R"(foo
bar
baz)";
char raw_str2[] = R"delim(\w+ \d+)delim";
char16_t raw_str3[] = uR"(\w+ \d+)";

// try-block
try {
  throw std::runtime_error("Runtime error!");
} catch (std::exception& e) {
  std::cerr << e.what() << std::endl;
}

constexpr int factorial(int n) {
  return n > 0 ? n * factorial(n - 1) : 1;
}

/* foo */ #if 0
 this is commented
#endif

/* it shouldn't hang */        /* trying to lex this */
/*{"ahg/awn/xan?",     HB_TAG('A','G','W',' ')},*/     /* Agaw */
/*{"gsw?/gsw-FR?",     HB_TAG('A','L','S',' ')},*/     /* Alsatian */
/*{"krc",      HB_TAG('B','A','L',' ')},*/     /* Balkar */
/*{"??",       HB_TAG('B','C','R',' ')},*/     /* Bible Cree */
/*{"sgw?",     HB_TAG('C','H','G',' ')},*/     /* Chaha Gurage */
/*{"acf/gcf?", HB_TAG('F','A','N',' ')},*/     /* French Antillean */
/*{"vls/nl-be",        HB_TAG('F','L','E',' ')},*/     /* Flemish */
/*{"enf?/yrk?",        HB_TAG('F','N','E',' ')},*/     /* Forest Nenets */
/*{"fuf?",     HB_TAG('F','T','A',' ')},*/     /* Futa */
/*{"ar-Syrc?", HB_TAG('G','A','R',' ')},*/     /* Garshuni */
/*{"cfm/rnl?", HB_TAG('H','A','L',' ')},*/     /* Halam */
/*{"ga-Latg?/Latg?",   HB_TAG('I','R','T',' ')},*/     /* Irish Traditional */
/*{"krc",      HB_TAG('K','A','R',' ')},*/     /* Karachay */
/*{"alw?/ktb?",        HB_TAG('K','E','B',' ')},*/     /* Kebena */
/*{"Geok",     HB_TAG('K','G','E',' ')},*/     /* Khutsuri Georgian */
/*{"kca",      HB_TAG('K','H','K',' ')},*/     /* Khanty-Kazim */
/*{"kca",      HB_TAG('K','H','S',' ')},*/     /* Khanty-Shurishkar */

class Base
{
public:
  Base () = default;
  virtual ~Base () = default;

  virtual void foo () = 0;
};

class Derived final : public Base
{
public:
  Derived () = default;
  virtual ~Derived () = default;

  virtual void foo () override
  {
     auto a = 1 + 2;
  }
};

#define foo bar
#define baz zot

class Highlighter : public QSyntaxHighlighter
{
   class InnerClass {}

   Q_OBJECT

public:
   Highlighter(QTextDocument *parent = 0);

protected:
   void highlightBlock(const QString &text);

private:
   struct HighlightingRule
   {
       QRegExp pattern;
       QTextCharFormat format;
   };
   QVector<HighlightingRule> highlightingRules;

   QRegExp commentStartExpression;
   QRegExp commentEndExpression;

   QTextCharFormat keywordFormat;
   QTextCharFormat classFormat;
   QTextCharFormat singleLineCommentFormat;
   QTextCharFormat multiLineCommentFormat;
   QTextCharFormat quotationFormat;
   QTextCharFormat functionFormat;
};
