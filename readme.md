# Javascript [Creole](http://www.wikicreole.org/) Wiki Engine with Latex Support
Hacked [veged/jscreole](https://github.com/veged/jscreole) to support rendering mathematics in Latex notation with [MathJax](http://www.mathjax.org/)

# Creole Syntax Extensions
    \( INLINE MATH \)
    \[ DISPLAY MODE MATH \]

# Example
    <div id="wiki"></div>

    <script src="mathjax/MathJax.js">
    MathJax.Hub.Config({
    		jax: ['input/TeX', 'output/HTML-CSS'],
    });
    </script>
    <script src="creole.js">
    creole = new Parse.Simple.Creole({
        forIE: document.all,
    });
    var markup = '= Title\ninline math: \\(\\frac{-b\\pm\\sqrt{b^2-4ac}}{2a}\\)\n';
    var div = document.getElementById('wiki');
    creole.parse(div, markup);
    MathJax.Hub.Queue(['Typeset', MathJax.Hub, div]);
    </script>
