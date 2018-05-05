<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" xml:lang="en">
<head>
<title>Armored Arcane Casting</title>
<meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1" />
<link rel="stylesheet" href="style/g3readme_cam.css" type="text/css" />
<link href="style/g3icon.ico" rel="icon" type="image/bmp" />
</head>
<body>
<h1>Armored Casting Macro for BG/IWD</h1>
<div class="section">
  <p><strong>Author:</strong> <a href="http://forums.gibberlings3.net/index.php?showuser=6306">Duns Scotus, the SubtleDoctor</a><br />
</p>
  <p><strong> Version 2.0 </strong><br />
    <strong> Languages:</strong> English<br />
    <strong>Platforms: </strong>WeiDU</p>
</div>
<h2>WHAT THIS IS</h2>
<div class="section">
  <p>this is a drop-in utility that lets anyone enable creatures, kits, or classes cast arcane spells in armor.  It works like this:</p>
  <p>It moves the "disable arcane casting" (opcode 145) effects in armor .ITM files out into external .EFF files.  There are three variants, which are identical except for their names.  One of the three is used in leather armors, one of them is used in chain armors, and one is used in plate armors.  They are "d5arcaL," "d5arcaC," and "d5arcaP."</p>
  <p>Then, it creates three spells, each of which blocks one of the above effects.  "d5arca1" blocks "d5arcaL," and thus allows casting spells in leather armor.  "d5arca2" blocks "d5arcaC," and thus allows casting in chain armor.  And "d5arca3" blocks "d5arcaP," and thus allows casting in plate armor.</p>
  <p>It also create three .EFF files that are functionally identical to those three spells.</p>
  <p>The spells have permanent timing, so they can be applied as a kit ability, or patched onto a .CRE file, or whatever.  Beings affected by "d5arca1.spl" for example, will be able to cast arcane spells in any leather armor.  The Tome & Blood Magus kit uses this method to cast spells in any kind of armor.</p>
  <p>The ...1/...2/...3 .EFF files have "while equipped" timing, so they can be inserted into armor .ITM files before the ...L/...C/...P 177 effects, in order to exempt categories of people from the restriction.  For example, the Bardic Armored Casting component of Tome & Blood applies "d5arca1.eff" via a 177 effect targeting bards; this allows bards to cast spells in leather armor.</p>
  <p>In EE games with the v2.0+ engine, you can use opcode 318 effects protecting against "d5arcaL/C/P," for even more fine-tuned filtering.  Sky's the limit.</p>
</div>
<h2>TO USE THIS</h2>
<div class="section">
  <p>Drop the "d5_armored_casting.tpa" file somewhere in your mod folder... I suggest in /%MOD_FOLDER%/lib/.  Then you can activate it with the following code:</p>
  <p><b>	INCLUDE ~%MOD_FOLDER%/lib/d5_armored_casting.tpa~
	LAM D5_ARMORED_CASTING</b></p>
  <p>Then simply apply "d5arca1/2/3" as you see fit.</p>
</div>
<h2>Compatibility</h2>
<div class="section">
  <p>Why I'm publishing this as a drop-in file, rather than just telling people to do it on their own, is this: if everyone uses this version, it can be done by six different mods in six different ways, and it will detect itself and get out of its own way so that it all works in concert.</p>
</div>
</body>
</html>
