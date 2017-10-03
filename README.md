<mvt:assign name="l.settings:files[1]" value="'sfnt'" />
<mvt:assign name="l.settings:files[2]" value="'prod'" />
<mvt:assign name="l.settings:files[3]" value="'ctgy'" />
<mvt:assign name="l.settings:files[4]" value="'checkout'" />
<mvt:assign name="l.settings:files[5]" value="'pages'" />

<mvt:foreach iterator="file" array="files">
	<mvt:assign name="l.settings:success" value="0" />
	<mvt:call action="'https://store.com/mm5/themes/XXX/css/minify-css.php?css_file=' $ l.settings:file" method="'GET'">
		<mvt:assign name="l.settings:success" value="s.callvalue" />
	</mvt:call>
	<mvt:if expr="l.settings:success">
		&mvt:file; -- SUCCESS <mvt:eval expr="asciichar( 10 )" />
	<mvt:else>
		&mvt:file; -- ERROR <mvt:eval expr="asciichar( 10 )" />
	</mvt:if>
</mvt:foreach>
