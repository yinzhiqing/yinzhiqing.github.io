---
layout: links
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_links

# publish date (used for seo)
# if not specified, site.time will be used.
#date: 2022-03-03 12:32:00 +0000

# for override items in _data/lang/[language].yml
#title: My title
#button_name: "My button"
# for override side_and_top_nav_buttons in _data/conf/main.yml
#icon: "fa fa-bath"

# seo
# if not specified, date will be used.
#meta_modify_date: 2022-03-03 12:32:00 +0000
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# if you enabled image_viewer_posts you don't need to enable this. This is only if image_viewer_posts = false
#image_viewer_on: true
# if you enabled image_lazy_loader_posts you don't need to enable this. This is only if image_lazy_loader_posts = false
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: false


# you can always move this content to _data/content/ folder
# just create new file at _data/content/links/[language].yml and move content below.
###########################################################
#                Links Page Data
###########################################################
page_data:
  main:
    header: "Links"
    info: "Your Links page description."

  # To change order of the Categories, simply change order. (you don't need to change list order.)
  category:
    - title: "JekyII / Liquid"
      type: id_jekyiiliquid
      color: "gray"
    - title: "Web Design"
      type: id_webdesign
      color: "#F4A273"
    - title: "Programming"
      type: id_programming
      color: "#62b462"
    - title: "linux command"
      type: id_linuxcommand
      color: "#62c462"
    - title: "Languages"
      type: id_liquid
      color: "#62d462"
    - title: "kubernetes"
      type: id_kubernetes
      color: "#62d462"
    - title: "docker"
      type: id_docker
      color: "#62d462"


  list:
    -
    # programming
    - type: id_programming
      title: "Stack OverFlow"
      url: "https://stackoverflow.com/"
      info: "Stack Overflow is a question and answer website for professional and enthusiastic programmers."

    # jekyiiliquid
    - type: id_jekyiiliquid
      title: "Jekyll"
      url: "https://jekyllrb.com/"
      info: "Transform your plain text into static websites and blogs."
    - type: id_jekyiiliquid
      title: "Jekyll Cheat Sheet"
      url: "https://cloudcannon.com/community/jekyll-cheat-sheet/"
      info: "There are so many Jekyll variables and filters to remember and it can be tricky to keep it all in your head. This cheat sheet serves as a quick reference of everything Jekyll can do."
    - type: id_jekyiiliquid
      title: "Liquid for Designers"
      url: "https://github.com/Shopify/liquid/wiki/Liquid-for-Designers"
      info: "Liquid for Designers wiki on GitHub"
    - type: id_jekyiiliquid
      title: "Liquid for Programmers"
      url: "https://github.com/Shopify/liquid/wiki/Liquid-for-Programmers"
      info: "Liquid for Programmers wiki on GitHub"
    - type: id_jekyiiliquid
      title: "Liquid Reference"
      url: "https://shopify.dev/api/liquid/"
      info: "Liquid is a template language created by Shopify and written in Ruby. It is now available as an open source project on GitHub"

    # webdesign
    - type: id_webdesign
      title: "W3Schools"
      url: "https://www.w3schools.com/"
      info: "W3Schools offers free online tutorials, references and exercises in all the major languages of the web. Covering popular subjects like HTML, CSS, JavaScript, Python, SQL, Java, and many more."

    # linuxcommand
    - type: id_linuxcommand
      title: "GNU Coreutils"
      url: "https://www.gnu.org/software/coreutils/manual/html_node/index.html"
      info: "This manual documents version 9.1 of the GNU core utilities, including the standard programs for text and file manipulation."

    # tools
    - type: id_terminator
      title: "terminator"
      url: "https://gnome-terminator.readthedocs.io/en/latest/"
      info: "If you live at the command-line, or are logged into 10 different remote machines at once, you should definitely try out Terminator."

    # languages
    - type: id_liquid
      title: "liquid"
      url: "https://shopify.github.io/liquid/"
      info: "Liquid is an open-source template language created by Shopify and written in Ruby. It is the backbone of Shopify themes and is used to load dynamic content on storefronts"

    # kubernetes
    - type: id_kubernetes
      title: "kubernetes docs"
      url: https://kubernetes.io/zh-cn/docs/home/
      info: "iKubernetes 是一个开源的容器编排引擎，用来对容器化应用进行自动化部署、 扩缩和管理。该项目托管在 CNCF。"

    # docker
    - type: id_docker
      title: "docker docs"
      url: https://docs.docker.com/reference/
      info: "包括Docker平台的各种API，CLIS，驱动程序和规格以及文件格式的参考文档。"

---
