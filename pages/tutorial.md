<h1>Tutorial<span><img src="/images/bam.gif" style="height:50px;width:50px;" /></span></h1>
---
### Install

* [Install NodeJs](http://nodejs.org)
* Install Bam

```
npm install bam -g
```

<h3 style="margin-top:10px;">Getting Started</h3>

---

#### Step 1. Create New Project

Currently, BAM has two default responsive templates to get started with.

* [Skeleton (default)](http://getskeleton.com)
* [Bootstrap (twitter-bootstrap)](http://twitter.github.com/bootstrap/)

To start a new project just type `bam new [project name]`, if you want to use the `bootstrap` template then type `bam new [project name] bootstrap`.

> For Skeleton

``` sh
bam new foosite
```

> For Bootstrap

``` sh
bam new foosite bootstrap
``` 

> Output

> Building Folders...
> Creating Files...
> Creating Layout...
> Creating Assets...

---

#### Step 2. Create Index Page

After creating your new static site project, change into the directory that was created as your project name.

``` sh
cd foosite
ls
```

> 404.html	javascripts	package.json	robots.txt	server.js
>images		layout.html	pages		s3.json		stylesheets

Use your favorite text editor to create a new file in the pages directory.

> pages/index.md

The md extension indicates that the file uses [markdown](http://daringfireball.net/projects/markdown/), a markup language that converts to html.  Lets do a simple h1 tag that says hello world.

<p># Hello World</p>

Now lets save the file.  When Bam generates the static site, it will convert any file in the pages folder with the extension of md to an html file.

---

#### Step 3. Run our site in Development mode

To run the site in development mode, which will allow us to see the changes as we work.  Simply, go back to your console and type:

```
bam run
```
> Listening on 3000
> CTRL-C to quit.

This will start up a nodejs server running on port 3000.  You can access your site by opening a browser and typing: http://localhost:3000.

![step3](/images/step3.png)

---

#### Step 4. Generating the static site

To Generate the static site simply type `bam gen` in your console.

```
bam gen
```

The gen command will generate all the static content for your project in the gen directory.  To deploy your site, simply copy the gen directory to your web server and its online.  Make changes, type `bam gen`, then copy the gen folder up and `bam` your site is updated.  

---

#### Step 5. Testing your static content

```
bam serve
```

Open your browser on http://localhost:3000

---

#### Step 6. Deploying to S3

Amazon Web Services Simple Storage Service (S3) has the ability to serve webpages from the S3 buckets, and Bam come with a simple way to update your s3 bucket with the static site, as well as post the proper settings to your account to create your website.

Edit the s3.json file in your project directory with your key and secret key and your website bucketname, which should be your website's name (www.foosite.com).

```
{
  key: XXXX
  secret: XXXX
  bucket: www.foosite.com
}
```

To deploy your static site run the `bam deploy` command.

```
bam deploy s3
```
