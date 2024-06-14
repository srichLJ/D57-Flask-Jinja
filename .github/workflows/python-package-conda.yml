from flask import Flask, render_template
import requests


app = Flask(__name__)

@app.route('/')
def home():
    response_blog = requests.get("https://api.npoint.io/c790b4d5cab58020d391")
    if response_blog.status_code == 200:
        all_posts = response_blog.json()
    return render_template('index.html', posts=all_posts)


@app.route('/post/<blog_id>')
def get_post(blog_id):
    response_blog = requests.get("https://api.npoint.io/c790b4d5cab58020d391")
    if response_blog.status_code == 200:
        all_posts = response_blog.json()
        id_int = int(blog_id)-1
        blog_choice = all_posts[id_int]
    return render_template('post.html', post=blog_choice)

if __name__ == "__main__":
    app.run(debug=True)
