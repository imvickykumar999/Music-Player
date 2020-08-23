# Music-Player
Weblink : (soon)

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">

<title>Music Player</title>
<meta name="description" content="">
<meta name="author" content="">

<!-- Load JS -->
<script src="mplayer.js"></script>

<!-- Load CSS -->
<link rel="stylesheet" href="mplayer.css">
<link rel="stylesheet" href="http://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.0.3/css/font-awesome.min.css">

<!--[if lt IE 9]>
<script src="http://html5shiv.googlecode.com/svn/trunk/html5.js"></script>
<![endif]-->

 </head>
<body>

<div id="mplayer-container">
	<div id="mplayer">
        <div id="mplayer-details" class="animated">
            <span id="mplayer-songname">Can't remember to forget you</span>
            <span id="mplayer-artist">Shakira feat. Rihanna</span>
        </div>
        <div id="mplayer-cover">
            <img src="http://www.jyvhouse.co.uk/wp-content/uploads/2014/01/Shakira-ft-Rihanna-Cant-Remember-To-Forget-You-Jyvhouse-Extended-Bass-Remix.png">    
        </div>
		<div id="mplayer-nav">
            <div id="m-progress"></div>
            <span class="m-nav" id="m-nav-left"><i class="fa fa-chevron-left"></i></span>
            <div class="m-nav">
                <div id="m-nav-playbg">
                    <span id="m-nav-play"><i class="fa fa-play"></i></span>
                    <span id="m-nav-pause"><i class="fa fa-pause"></i></span>
                </div>
            </div>
            <span class="m-nav" id="m-nav-right"><i class="fa fa-chevron-right"></i></span>
        </div>
	</div>
	<div id="mplayer-button">
		<i class="fa fa-headphones"></i>
	</div>
</div>

</body>
</html>
