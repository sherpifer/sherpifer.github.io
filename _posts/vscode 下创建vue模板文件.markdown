---
layout:     post
title:      "vscode 下创建vue模板文件"
date:       "
author:     "Sherpifer"
header-img: "img/post-bg-2015.jpg"
tags:
    - vscode vue模板
---

菜单栏文件>>首选项>>用户代码片段>>输入vue>>选择vue.json(Vue)
ctrl+shift+p >> 输入用户代码片段>>输入vue>>选择vue.json(Vue)

```json
{
  "vue-template": {
    "prefix": "vue",
    "body": [
      "<template>",
      "  <div class=\"\">",
      "",
      "  </div>",
      "</template>",
      "",
      "<script>",
      "export default {",
      "  components:{",
      "  },",
      "  data() { ",
      "    return {",
      "",
      "    }",
      "  },",
      "  created() {",
      "",
      "  },",
      "  mounted() {",
      "",
      "  },",
      "  beforeDestroy() {",
      "",
      "  },",
      "  destroyed() {",
      "",
      "  },",
      "  computed: {",
      "",
      "  },",
      "  watch: {",
      "",
      "  },",
      "  methods:{",
      "",
      "  },",
      " }",
      "</script>",
      "",
      "<style lang=\"\" scoped>",
      "",
      "</style>"
    ],
    "description": "my vue template"
  }
}
```