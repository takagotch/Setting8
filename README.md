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
vi app/views/hello/index.html.erb
+<p>Current Time: <%= @time %></p>
curl https://localhost:3000/hello/index
```

```sh
rails new webapp2
cd webapp2
rails g scaffold book title:string memo:text
rails db:migrate
rails s
curl https://localhost:3000/books

rails g scaffold book title:string memo:text
vi config/routes.rb
vi app/controllers/books_controller.rb
vi app/controllers/books_controller.rb
vi app/views/books/new.html.erb
vi app/views/books/_form.html.erb
vi app/controllers/books_controller.rb

rails c
book = Book.new(title: "TITLE", memo: "text")
book.save
Book.last
rails s
curl https://localhost:3000/books

vi app/models/book.rb
rails g scaffold book title:string memo:text
rails db:migrate
vi db/migrate/[timestamp]_create_books.rb

rails g migration AddAuthorToBooks author:string
rails g migration AddAuthorToBooks author:string
vi db/migrate/[timestamp]_add_author_to_books.rb
rails db:migrate
vi app/views/books/_form.html.erb
+ <div>
+   <%= f.label :author %><br>
+   <%= f.text_field :author %>
+ </div>
vi app/views/books/show.html.erb
+ <p>
+   <strong>Author:</strong>
+   <%= @book.author %>
+ </p>
vi app/views/books/index.html.erb
+ <th>Author</th>
+ <td><%= book.author %></td>
vi app/controllers/books_controller.rb
+ params.require(:book).permit(:title, :memo, :author)
curl https://localhost:3000/
```

```sh
rails g migration AddPictureToBooks picture:string
rails g migration AddPictureToBooks picture:string
vi db/migrate/[timestamp]_create_add_picture_to_books.rb
rails db:migrate
vi Gemfile
bundle
bin/spring stop
rails g uploader Picture
vi app/models/books.rb
+ mount_uploader :picture, PictureUploader
vi app/controllers/books_controller.rb
+ params.require(:book).permit(:title, :memo, :author, :picture)
vi app/views/books/_form.html.erb
+ <div>
+   <%= f.label :picture %><br>
+   <%= f.file_field :picture %>
+ </div>
vi app/views/books/show.html.erb
+ <p>
+   <strong>Picture:</strong>
+   <%= image_tag(@book.picture_url) if @book.picture.present? %>
+ </p>
vi app/views/books/index.html.erb
+ <th>Picture</th>
+ <td><%= book.picture %></td>
curl https://localhost:3000/books
rails s
```

```
rails g migration AddAuthorToBooks author:string
rails g model book title:string memo:text
rails g controller books index
rails g scaffold book string memo:text

```
```
git clone https://github.com/rbenv/rbenv.git
git clone https://github.com/ruby-build/ruby-build.git
echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
echo 'export PATH="$HOME/.rbenv/shims:$PATH"' >> ~/.bash_profile
source ~/.bash_profile
rbenv install 2.7.1
rbenv rehash
rbenv global 2.7.1
source ~/.bash_profile
```
```
vi Gemfile
bundle

rails c
```

