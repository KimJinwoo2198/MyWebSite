
<link href="https://fonts.googleapis.com/css?family=Montserrat:400" rel="stylesheet">
<link href="https://fonts.googleapis.com/css?family=Chango" rel="stylesheet">
<script>
    let homepageLink = "https://kimjinwoo.me";
    // let resumeLink = "https://resume.paulkim.me";
    // let learnMoreLink = "https://cs50.paulkim.me/hello_world/";
    let blogLink = "https://blog.kimjinwoo.me";
</script>

<style>
    * {
        -webkit-box-sizing: border-box;
        box-sizing: border-box;
    }

    body {
        padding: 0;
        margin: 0;
    }

    #notfound {
        position: relative;
        height: 100vh;
    }

    #notfound .notfound {
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
    }

    .notfound {
        max-width: 520px;
        width: 100%;
        line-height: 1.4;
    }

    .notfound>div:first-child {
        padding-left: 200px;
        padding-top: 12px;
        height: 170px;
        margin-bottom: 20px;
    }

    .notfound .notfound-404 {
        position: absolute;
        left: 0;
        top: 0;
        width: 170px;
        height: 170px;
        background: #e01818;
        border-radius: 7px;
        box-shadow: 0px 0px 0px 10px #e01818 inset, 0px 0px 0px 20px #fff inset;
    }

    .notfound .notfound-404 h1 {
        font-family: 'Chango', cursive;
        color: #fff;
        font-size: 118px;
        margin: 0px;
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
        display: inline-block;
        height: 60px;
        line-height: 60px;
    }

    .notfound h2 {
        font-family: 'Chango', cursive;
        font-size: 68px;
        color: #222;
        font-weight: 400;
        text-transform: uppercase;
        margin: 0px;
        line-height: 1.1;
    }

    .notfound p {
        font-family: 'Montserrat', sans-serif;
        font-size: 16px;
        font-weight: 400;
        color: #222;
        margin-top: 5px;
    }

    .notfound a {
        font-family: 'Montserrat', sans-serif;
        color: #e01818;
        font-weight: 400;
        text-decoration: none;
    }

    @media only screen and (max-width: 480px) {
        .notfound {
            padding-left: 15px;
            padding-right: 15px;
        }

        .notfound>div:first-child {
            padding: 0px;
            height: auto;
        }

        .notfound .notfound-404 {
            position: relative;
            margin-bottom: 15px;
        }

        .notfound h2 {
            font-size: 42px;
        }
    }
</style>

<div id="notfound">
    <div class="notfound">
        <div>
            <div class="notfound-404">
                <h1>!</h1>
            </div>
            <h2>Error<br>404</h2>
        </div>
        <p>Sorry! You've reached a page that doesn't exist.</p>
        <!-- <p><a href={homepageLink}>Back to homepage | </a> <a href={resumeLink}>Back to resume | </a><a href={blogLink}>Back to blog</a></p> -->
        <!-- <p>Don't know or unsure what 404 means? <a href={learnMoreLink}>Learn more.</a></p> -->
    </div>
</div>
