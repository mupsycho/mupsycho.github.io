# 主题切换

<div class="demo-theme-preview">
  <a data-theme="vue">Vue</a>
  <a data-theme="buble">Buble</a>
  <a data-theme="dark">黑色风格</a>
  <a data-theme="pure">Pure</a>
</div>

<style>
  .demo-theme-preview a {
    padding-right: 10px;
  }

  .demo-theme-preview a:hover {
    cursor: pointer;
    text-decoration: underline;
  }
</style>

<script>
  var preview = Docsify.dom.find('.demo-theme-preview');
  var themes = Docsify.dom.findAll('[rel="stylesheet"]');

  preview.onclick = function (e) {
    var title = e.target.getAttribute('data-theme');

    themes.forEach(function (theme) {
      theme.disabled = theme.title !== title;
      if(theme.title == "gitalk") {
        theme.disabled = false;
      }
      localStorage.setItem("data-theme", title);
    });
  };
</script>