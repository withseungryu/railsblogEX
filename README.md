### Rails를 이용하여 CRUD를 이용한 POST기능을 배우고, 만들어봤습니다.

## 2018-05-30 멋쟁이 사자처럼 Rails 강의에서..

Application.hmtl 참조 이유 코드 양을 줄이기 위해
-><%=yield%> 위에 넣으면 된다.
Footer 는 아래에 넣는다.

File -> local file upload  asset 폴더 아래 stylesheet 와 javascript 에 넣는다
Assets pipe 라인의 기술로 인해 
<%= stylesheet_link_tag    'application', media: 'all', 'data-turbolinks-track' => true %>
  <%= javascript_include_tag 'application', 'data-turbolinks-track' => true %>
<%= csrf_meta_tags %>
# 이 코드로 이용해 바로 불러올 수 있다.

<link href="/assets/css/bootstrap.css" rel="stylesheet">


    <!-- Custom styles for this template -->
    <link href="/assets/css/main.css" rel="stylesheet">

    <script src="https://code.jquery.com/jquery-1.10.2.min.js"></script>
    <script src="/assets/js/hover.zoom.js"></script>
    <script src="/assets/js/hover.zoom.conf.js"></script>
# 이 코드로 이용해  사용할 수 있따.  /assets@!!!! 기억 할 것

<!--<li><a href="/posts/index">Post</a></li>--> 이것을 대신하여
# 루비언어를 사용해서 아래와 같이 표현 할 수 있다.
   <li><%= link_to "Post" "/posts/index" %></li>

<%= post.created_at %>
#  데이터가 작성된 시간

# 글 순서는 생성된 순으로 바꿔주기
@posts = Post.all.order(created_at: :desc)
Asc ->오름차순
Desc 내림차순
Order의 default값은 오름차순이다. 
따라서 내림차순으로 변경
### @@@@find는 id값만 찾을수있다@@@@
# 다른 값을 찾기 위해서는 find_by_title 이런식으로 찾는다.==>구글링

# show파일로 가봤자 모두 동일한 페이지 내용이 나온다
# 따라서 routes.rb파일로 가서 
‘Posts/show/:id’ =>’posts#show’  show 컨트롤러로 간다.
Form helper??/


	<%= form_tag 'posts/create' do %>
<%= text_field_tag  'title', nil, class:"form-control"%>
<%= text_area_tag 'body', nil, class:"form-control" %>
<%= submit_tag 'SUBMIT', class:"btn btn=success" %>
# nil이란 value값 순서가 또박또박 이라 value값 nil을 넣어줘야한다.
# = X : O


