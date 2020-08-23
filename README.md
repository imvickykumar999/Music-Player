<!DOCTYPE html>
<html lang="en-US">
<head profile="http://www.w3.org/2005/10/profile">
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<title>Tiny HTML5 Music Player by Themistokle Benetatos</title>
<meta name="description" content="Tiny HTML5 Music Player by Themistokle Benetatos: http://mrt-prodz.com">
<link rel="stylesheet" media="all" type="text/css" href="./css/tinyplayer.css">
<script src="./js/tinyplayer.js"></script>
<script>
	/* Tiny HTML5 Music Player by Themistokle Benetatos */
	TrackList = 
		[
			{
				url:'http://www.mrt-prodz.com/public/mp3/whwd.mp3',
				title:'What Have We Done',
				year:'2007'
			},
			{
				url:'http://www.mrt-prodz.com/public/mp3/right-of-stupidity.mp3',
				title:'Right of Stupidity',
				year:'2004'
			}
		];
		
	//Make a player and display help
	//player([tracklist], [show waveform?], [show help?])
	tinyplayer(TrackList, true, true);
</script>
<style>
pre{
    white-space: pre-wrap;       /* css-3 */
    white-space: -moz-pre-wrap;  /* Mozilla, since 1999 */
    white-space: -pre-wrap;      /* Opera 4-6 */
    white-space: -o-pre-wrap;    /* Opera 7 */
    word-wrap: break-word;       /* Internet Explorer 5.5+ */
}
</style>
</head>
<body>
	<div class="wrapper">
		<h2>Tiny HTML5 Mp3 Player</h2>
		<p>Trying to keep it simple and under 10KB with no dependencies, you just need a modern HTML5 compatible browser. The waveforms were generated with <a href="http://sox.sourceforge.net/" target="_blank">SoX</a> and <a href="http://www.gnuplot.info" target="_blank">gnuplot</a>, both available for free on Linux, Windows and OSX.</p>
		<p>Bash script to generate waveforms of all mp3 in the current folder:<p>
		<pre><code>
#!/bin/bash
# Generates waveforms of all mp3 in current folder
# PNG resolution: 980 x 60
# Dependencies: sox and gnuplot

FILES="./*.mp3"

for f in $FILES
do
	sox $f -G -r 4000 -c 1 test.dat && tail -n+3 test.dat > test.datclean

	gnuplot -p -e "set terminal png transparent size 980,60 enhanced; set yr [-1:1]; unset key; unset tics; unset border; set lmargin 0; set rmargin 0; set tmargin 0; set bmargin 0; set output '$f.png'; plot 'test.datclean' using 1:2 every 50 with lines lc rgbcolor '#000000'"
done

rm test.dat
rm test.datclean
		</code></pre>
		<p>Import both tinyplayer.css and tinyplayer.js and add this script to your page.<br/>Usage:</p>
		<pre><code>
TrackList = 
	[
		{
			url:'http://www.mrt-prodz.com/public/mp3/whwd.mp3',
			title:'What Have We Done',
			year:'2007'
		},
		{
			url:'http://www.mrt-prodz.com/public/mp3/right-of-stupidity.mp3',
			title:'Right of Stupidity',
			year:'2004'
		}
	];
//player([tracklist], [show waveform?], [show help?])
tinyplayer(TrackList, true, true);
		</code></pre>
		<div id="all_tracks"></div>
	</div>
</div>
</body>
</html>
