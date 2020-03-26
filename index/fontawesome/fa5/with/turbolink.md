

# Turbolinks

Font Awesome与大多数经常与Rails搭配使用的工具很好地集成在一起，通过换出&lt;body&gt;并合并HTML页面的&lt;head&gt;来提高页面性能。



> ### 这仅在您将SVG与JS结合使用时比较棘手
> 
> 如果您在CSS中使用webfonts，则无需担心此设置。 将SVG与JS结合会带来多余的工作



## 我们需要通过集成解决的一些问题

在安装了带有JS版本的Font Awesome的SVG并将第一页加载到Rails应用中。

*   1.Font Awesome会搜索任何&lt;i&gt;元素并将其替换为&lt;svg&gt;元素

*   2.它将创建一个MutationObserver，监视页面中的更改以进行实时的替换

当Turbolinks用新内容替换页面的&lt;body&gt;时，Font Awesome会自动将此MutationObserver重新连接到新内容。

问题出在这里：闪烁的图标消失了，然后迅速出现。 这看起来很麻烦，但是我们可以轻松修复它。

将mutateApproach配置设置为同步（在5.8.0或更高版本中可用）提供了一种方法，可以在Turbolinks收到新主体后立即渲染它们，从而跳过丢失的图标。

## Rails

首先，假设您已经安装了Turbolinks并在Rails应用程序中对其进行了配置。

## 使用我们的CDN或您自己进行托管

如果您通过修改Rails布局安装了Font Awesome，则可能包含&lt;script&gt;标签。

添加data-mutate-approach ="sync"。

          <!DOCTYPE html>
          <html>
            <head>
              <title>My app</title>
              <%= csrf_meta_tags %>
              <%= csp_meta_tag %>

              <%= stylesheet_link_tag    'application', media: 'all', 'data-turbolinks-track': 'reload' %>
              <%= javascript_include_tag 'application', 'data-turbolinks-track': 'reload' %>
              <script src="https://use.fontawesome.com/releases/v5.11.2/js/all.js" data-mutate-approach="sync"></script>
            </head>

            <body>
              <%= yield %>
            </body>
          </html>
        
    

## 使用asset pipeline

安装Font Awesome的另一种常见方法是将源文件放置在vendor/assets/javascripts目录中，然后修改app/assets/javascripts/application.js 来引入// =require fontawesome/all。 然后，Font Awesome将引入到您的Rails布局已包含的应用程序包中。

您可以在布局中添加&lt;script&gt;标记以更改配置。

            <!DOCTYPE html>
            <html>
              <head>
                <title>My app</title>
                <%= csrf_meta_tags %>
                <%= csp_meta_tag %>

                <script>
                  FontAwesomeConfig = {
                    mutateApproach: 'sync'
                  }
                </script>

                <%= stylesheet_link_tag    'application', media: 'all', 'data-turbolinks-track': 'reload' %>
                <%= javascript_include_tag 'application', 'data-turbolinks-track': 'reload' %>
              </head>

              <body>
                <%= yield %>
              </body>
            </html>
        
    

但是，也许最好的方法是直接在application.js文件中进行配置。

       
          // This is a manifest file that'll be compiled into application.js, which will include all the files
          // listed below.
          //
          // Any JavaScript/Coffee file within this directory, lib/assets/javascripts, or any plugin's
          // vendor/assets/javascripts directory can be referenced here using a relative path.
          //
          // It's not advisable to add code directly here, but if you do, it'll appear at the bottom of the
          // compiled file. JavaScript code in this file should be added after the last require_* statement.
          //
          // Read Sprockets README (https://github.com/rails/sprockets#sprockets-directives) for details
          // about supported directives.
          //
          //= require rails-ujs
          //= require activestorage
          //= require turbolinks
          //= require fontawesome/all
          //= require_tree .

          FontAwesome.config.mutateApproach = 'sync'
        
    

## 使用Webpacker和@fortawesome/fontawesome-svg-core

如果使用Webpacker和NPM来安装Font Awesome，则可以使用摇树来创建子集图标。

您的安装可能看起来像这样，在这种情况下，我们只需使用API更改配置即可。

       
          import { config, library, dom } from '@fortawesome/fontawesome-svg-core'

          # Change the config to fix the flicker
          config.mutateApproach = 'sync'

          # An example icon
          import {
            faGithub
          } from '@fortawesome/free-brands-svg-icons'

          library.add(
            faGithub
          )

          dom.watch()
        

