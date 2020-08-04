### Setting8
---



```
```

```
rails new tkyapp
cd tkyapp
rails g scaffold entry title description:text picture
rails db:migrate
rails s
curl https://localhost:3000/entries

vi Gemfile
+ gem 'carrierwave'
bundle install
bin/spring stop
rails g uploader Picture
vi app/models/entry.rb
+ mount_uploader :picture, PictureUploader
vi app/views/entries/_form.html.erb
- <%= f.text_field :picture %>
+ <%= f.file_field :picture %>
- <%= @entry.picture %>
+ <%= image_tag(@entry.picture_url) if @entry.picture.present? %>
rails s
curl https://localhost:3000/entries
```

```sh
rails new webapp
cd webapp
rails s
curl https://localhost:3000/
rails g controller hello index
rails s
curl https://localhost:3000/hello/index
vi app/views/hello/index.html.erb
+ <p><%= Time.now %></p>
vi app/controllers/hello_controller.rb
+ @time = Time.now









```

```sh

```

```
rbenv install 2.4.0
```


